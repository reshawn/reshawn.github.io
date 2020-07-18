---
template: post
title: Scraping Live Stream Video with Python
slug: /posts/scraping-live-stream
draft: false
date: 2020-07-13T00:20:29.283Z
description: Tutorial on scraping live stream videos using python and serenium
category: Tutorial
tags:
  - tutorial
---
Scraping live streams can be a good source of data for computer vision projects. There's an endless variety of public online streams including traffic, security, nature and entertainment but not all live streams provide on-demand archives. Hence scraping the stream itself can be useful.

In this tutorial we use selenium to initialize and drive a headless live stream and download the stream's video chunks by grabbing the source urls from the network logs.

![](/media/eagle_livestream.JPG "Screenshot of Decorah Eagles Livestream by Explore.org")

_Screenshot of Decorah Eagles Livestream by Explore.org_

## What to Scrape

Live streams are fed and consumed in chunks of video, to access these chunks manually:

In a chrome tab with a running live stream, open Dev Tools > Network tab > XHR. The stream of .ts (transport stream) files being fetched are the raw video stream data and can be downloaded and played, they are the same as .mpeg files. These files are what we want to automatically download and put together.

There'll be an occasional .m3u8 file containing a list of the sources of the next set of .ts chunks. This can be used to grab the chunks in small batches instead of one by one but either way the point is to just grab the chunks from the source urls.

![](/media/devtoolstsscreenshot.jpg)

> Note: For non-live video streams a full .mp4 file of the video might be served and the source url could be found here, but for some sites and online players, a similar stream of .ts files is used.

## Initializing Stream: Selenium

To automate the downloads we need something to initialize the stream and, in some cases, keep it alive. We can use [selenium](https://selenium-python.readthedocs.io/), an automated front-end testing framework. The install is straight forward and the docs cover it well, the only thing that's needed other than a pip install is a driver for the browser you want selenium to use, which is explained with hyperlinks to the downloads in [the doc](https://selenium-python.readthedocs.io/installation.html#drivers). Note that the version of the driver used needs to match the version of the browser currently installed.

```
from selenium import webdriver
driver = webdriver.Chrome()
driver.get('https://twitch.tv')
```

The above opens the automated browser to the provided link but we can add arguments through options to change the window size, or make it headless.

```
from selenium import webdriver
options = webdriver.ChromeOptions();
options.add_argument('headless');driver = webdriver.Chrome(options=options)
driver.get('https://twitch.tv')
```

We also need to define our logging preferences as ALL so we can get the video chunk URLs from them.

```
from selenium import webdriver
from selenium.webdriver.common.desired_capabilities import DesiredCapabilities
caps = DesiredCapabilities.CHROME
caps['goog:loggingPrefs'] = {'performance': 'ALL'}
options = webdriver.ChromeOptions();
options.add_argument("--window-size=1920,1080");
driver = webdriver.Chrome(desired_capabilities=caps,options=options)
driver.get('https://twitch.com')
```

Some streams won't start immediately, they might have some ads or might need to be started by a click. Selenium commands can trigger clicks when we want by targeting the html tags, css, xpath, text, etc. See docs [here](https://selenium-python.readthedocs.io/locating-elements.html)  more.

```
driver.find_element_by_id("play-button").Click();
```

Regular python time.sleep() can also be useful for waiting on elements to exist or waiting out ads but this part really depends on the target stream site itself.

## Grabbing Video Chunks

Once the stream is started we need the .ts file links from the network logs.

```
def process_browser_log_entry(entry):
    response = json.loads(entry['message'])['message']
    return responsewhile True:
    browser_log = driver.get_log('performance') 
    events = [process_browser_log_entry(entry) for entry in browser_log]
    events = [event for event in events if 'Network.response' in event['method']]
```

In the above we load the logs as json objects and limit the logged events kept in the array to only Network Responses since that's all we care about.

From here, all we need to do is  iterate through the events, checking the response urls for any that end in .ts, fetch the data from that link and then write to a file.

```
for e in events:
    if e['params']['response']['url'].endswith('.ts'):
        url=e['params']['response']['url']
        r1 = requests.get(url, stream=True)
        if(r1.status_code == 200):
            with open('testvod.mpeg','ab') as f:
                for chunk in r1.iter_content(chunk_size=1024):
                    f.write(chunk)
        else:
            print("Received unexpected status code {}".format(r1.status_code)) 
```

To combine all the files all we needed to do was append all of the fetched .ts data to one file.

The stream will be continuously downloaded to the resulting .mpeg file for as long the browser instance is running. If you ran it in headless mode you can close all running instances with 

```
driver.quit()
```
