---
template: post
title: Scraping Live Stream Video with Python
slug: /posts/scraping-live-stream
draft: true
date: 2020-07-13T00:20:29.283Z
description: Tutorial on scraping streamed videos using python and serenium
category: Tutorial
tags:
  - tutorial
---
\> With online traffic cams, security cams, nature cams, twitch and youtube streams, scraping live streams can be a good source of data for computer vision projects and the process is a bit different from the normal scrape and parse of html

\> 1. open dev tools under network tab to see how the stream is being consumed. <pic>

\> If its a regular video and not a live stream, the video in its entirety could be whats being served and the source url can be found here. <pic>

	Some video streams and most live streams would serve the stream by continuously sending chunks of video as .ts files. These chunks are in the .mpeg format so can be downloaded and renamed to watch or use. An occassional m3u8 file contains a list of the sources of the next set of .ts chunks, this file can be used to grab the chunks in small batches instead of 1 by 1 but either way the point is to just grab the chunks from the source url like below. <code>

\> 2. To automate this we need something to initialize the stream and, in some cases, keep it alive. We can use serenium, a front end automated testing framework. 

\> First we declare the use of chrome as our puppet browser and download the appropriate driver for the installed version of chrome.

\> The below code opens the testing browser to the url of our live stream. Omit the headless option if you want to see the browser run.

\> Some streams won't start immediately, they might have some ads or might need to be started by a click. Serenium commands can trigger clicks when we want by targeting the html tags. <code> We can also just time.sleep to wait out ads.

\>  Once the stream is started we need to get the .ts file links from the browser's network activity.

\>  Serenium provides this through <code> and we can filter for the .ts links only.

\>  Lastly we iterate, download the files and concatenate them into a single .mpeg video file.
