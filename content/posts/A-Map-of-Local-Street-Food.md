---
title: A Map of Local Street Food
# The Food Map Project
# A Journey from farm to fork
date: "2019-07-21T12:01:32.169Z"
template: "post"
draft: false
slug: "/posts/a-map-of-local-street-food"
category: "Portfolio Blog"
tags:
  - "Food"
  - "Hybrid App"
description: "Building a map of doubles vendors with my friends."
---

> Portfolio Blog is a series of posts about projects that were meaningful to me.
> Rather than just "Project A does B using C" like a normal portfolio, the focus would be the inspiration behind ideas, what was fun, what I did wrong and the main lessons learnt. Hopefully reflecting on them in this way will make the lessons clearer.	 
> Really looking forward to reliving the memories while writing these.
<span style="font-style:normal" role="img" aria-label="sheep">😊</span>


*TLDR: Here's the [github](https://github.com/NirvanKS/DoublesRun) and [app](https://play.google.com/store/apps/details?id=com.compass.doublesrun)* 

## The Idea
Final year project for undergrad was group based, I was in a group with two friends and we needed to come up with a project idea. We were switching in and out of ideas writing proposals for each, but they were rejected just as quickly. The structure was that our group of 3 had two supervisors (One a more experienced lecturer and one a technical advisor more familiar with modern tech) and idea proposals were given to them but needed approval from the head of department. The ideas the HoD wanted were more business-like and revenue focused, reflecting our internship experience while we were more focused on ideas we thought were interesting and fun, so they got rejected (In hindsight some of them were pretty bad anyway though <span role="img" aria-label="sheep">😅</span> ). The supervisors themselves agreed with our approach, if students got to build what **they** were really interested in, they'd try harder and it wouldn't feel like a chore. Of course sustainability is important and shouldn't be ignored but I don't think it should've been the absolute core of an idea in this scenario.
<figure>
	<blockquote>
		<p>Reality can be more discouraging than it needs to be sometimes. So maybe a little naivety can make a big difference.</p>
		<footer>
			<cite>— My favourite lecturer.</cite>
		</footer>
	</blockquote>
</figure>

So we kept at it until eventually a groupmate said *"what about a map of [doubles](https://en.wikipedia.org/wiki/Doubles_(food)) vendors?"* and we all liked it, unlike our other ideas it had this very strong local feel to it. After more research we liked it even more because we saw it was an idea that was done before but could be done much better. We saw some big challenges we could have in generating revenue but we thought "*doubles is the most popular street food, the idea grabbed attention because of that so even if we can't make money we can get our names out there*" and as soon to be new grads, that had value to us. Also by starting off on doubles, the niche that gets attention, there was potential to expand to larger markets if it goes well. As for getting the idea approved, our supervisors liked it, they saw our enthusiasm and helped us get it by the HoD.  

I felt like our logic was sound and the idea was fun, looking back I still think that. Sure we were naive, we didn't understand just how much had already been done and failed in this space locally, we didn't understand the extent of sustainability problems and we didn't think about how this might be the last time we get to devote a large amount of time to a passion project as a group of friends before entering the working world, but we had drive and a plan for a map. <br/>
I'm glad we didn't choose an idea that made someone else happy.

![](/media/DoublesRunSplash.png)

## Building It
We named it ***Doubles Run*,** after the term "*Food run*" that's used to describe the act of leaving somewhere to quickly pick up food for/with friends. When the project was barely under-way my good friend, [isquishi](https://www.instagram.com/isquishi/) made a flat vector drawing of doubles for us to use as a map marker and icon as well. 

The choice of tech was easy, we went with Ionic and Python because we were most comfortable with those at the time and they were a fine fit for what we wanted to do. A hybrid app felt the most suitable for covering a lot of platforms easily even with its sacrifices in mind. Today react native is my go-to and picking it up at the time would've been great but sticking to comfort was the safer choice.

Balancing course loads and part time jobs with the project work was rough but we were committed and regularly spent a lot of time in a call on discord working on it together. Even if it were completely seperate tasks, we might've been in a call with music playing. Sometimes solitude is better and to each their own but I really enjoyed this. It was easy to bounce ideas back and forth, the old talk was relaxing. I wasn't overwhelmed or worried or anxious about the task at hand because I didn't feel alone. I think these calls are what made us closer as a group and we made a lot of progress on the project because of that.

We spent about four months working on Doubles Run as a final project. We used Google Maps as the base, setting it to Trinidad, allowing people to add vendors by hitting a button, taking a picture and writing a name. We thought having people be physically there to add a vendor would mean higher accuracy and less garbage data. Other users could then rate and review any vendors on the map, they could rate each key aspect of the food itself too (the thickness of the barra, spiciness of the pepper sauce, consistency of the channa). As per the suggestion of our great technical advisor, [Inzamam](https://github.com/InzamamRahaman), we used these reviews to recommend new vendors to users. A collaborative filtering model would look at vendors you liked, find users that liked similar vendors and recommend those they liked that you haven't tried yet. 

By the time submission and presentation came around we hit our goal and some. The presentation itself, I think we did really well, we were comfortable, explaining features and reasoning while telling jokes and laughing along. After months of hard work it felt like telling friends the story of an idea and showing them the result, rather than presenting our culmination of a degree's teaching to lecturers. I felt satisfied and proud of not just my groupmates but my classmates for their projects too, and the excitement they showed presenting them. That presentation day wasn't perfect by any means but it's definitely a fond memory.

![Screenshots](/media/DoublesRunSS.png)
*Screenshots*

We didn't stop there though, after getting our A+ we kept working on it for the rest of the year. Adding more features like full offline mode using cached data, stored map tiles on leaflet for an offline map since Google Maps didn't allow offline or saving tiles, a night mode switch (because we had our priorities straight) and more. 

We planned a makeshift marketing campaign that included a backlog of art, photography and posters for social media and talking to doubles vendors about a "Rate me on Doubles Run" sticker on their cart/box. We even got a few friends together and started making food run themed skits, we never released them but they were certainly a lot of fun to make!

![Screenshots](/media/DoublesRunSkit.png)
*Making the marketing skits*

I romanticized the building period by leaving out the countless bugs, hair pulling frustration, dependency issues, hosting problems due to the collaborative filtering model, optimization problems with the offline data, arguing over whether or not the name "*Doubles Run*" made people think of a game like "*Temple Run*", learning how to design splash screens and logos, and the list goes on and on. I mean I'd love to talk about those as well but it would be too much and I think the positive highlight memories are more important here anyway. I can talk about challenges without bringing up all those fine details.


## Challenges
When we released the beta version of the app, we had the intention of getting feedback and help to populate data. We planned routes for trips to gather vendor data as well. 
This is where we realized our biggest mistake, people liked the idea, but they weren't really interested in helping us gather data and doing it on our own was tougher than we thought. We were worrying about stuff like the geolocation accuracy, reducing apk size, handling the cold start of the collaborative filtering model, but these features meant nothing without data for people to view. It sounds silly as I think back on it, for us to build this "*Home for doubles lovers*" and forget that at its core it was a map of vendors and we had no vendors. 

Its not that we were completely oblivious to this, its just that we got so caught up in building a great platform we underestimated the difficulty of gathering data in the first place and didn't give it the priority we should have. Doubles Run began as our final project so we needed those extra features for our grade but once that was over we should've prioritized data much higher than we did.

As we were going through this problem, time became tighter, we all got full time jobs and continued to post grad on evenings. We still wanted to keep working on Doubles Run and other projects but needed to be smarter about how time was spent on them. So when we met a business manager with a lot of experience in tech, we went to him for advice and to hear what he thought about our sustainability and data situations. 

He explained how bigger companies poured tons of money into similar ideas and why they failed. He explained that unless we found a way to make deals with vendors themselves or add value to someone else then there'd be no chance to generate revenue short of becoming very popular, but even then it'd be a daunting task to stay popular. Lastly he encouraged us to pursue another project we were working on at the time because there was more business potential to it. There was more to the conversation but those three things are what I remember most clearly. We left feeling pretty dejected and unsure of what to do next. It was strange, he said things that we already somewhat knew, but hearing them from someone like him in such a blunt way shook us a lot more than I thought it would. 


Lastly, one of our groupmates expressed that he wasn't interested in continuing to work on the project. This wasn't a big surprise because we knew his interest was fading. We understood how he felt and there were no hard feelings whatsoever, but I still wish I talked to him sooner when I noticed his interest started to fade.

Those data trips were already logistically difficult to pull off, now with all this? We felt more discouraged than ever before.


## Lessons Learnt
#### Big picture focus
Some big problems start to look a lot smaller when you focus on the entire plan instead. Our worries about improving the user experience were valid but in the big picture they weren't the highest priority.
#### For fun is okay
The person we met was a good businessman and his advice was from that perspective. It was good advice and he answered our questions well, he took our work and ideas seriously regardless of our inexperience at the time, and I'm grateful for that. But we were asking the wrong questions because money wasn't why we started this. We started Doubles Run because it would be fun to make and fun to use. We forgot that reasoning as well as why we wanted to do this over the other project. For fun! And that's okay too.
#### Friendship > Progress 
Working closely with others for long periods of time can be tricky but friendship matters more than the project and its conflicts. Working with friends is what makes it more enjoyable in the first place and you learn a lot more than when working alone. I learnt a lot about my own bad habits because I had trusted groupmates who pointed them out in very mindful and constructive ways. I felt less overwhelmed and anxious with the work to be done because I knew I wasn't alone and had others to rely on. <br>
Even if the project fails, the memories and deepened friendships last, so project conflicts shouldn't be allowed to damage that.

## Future
Since then we've all continued on to other projects, seperately and as a group here and there.
As for Doubles Run itself, we plan to start working on a simpler version using Flutter, keeping important stuff like reviews but putting the appropriate amount of focus on data. 
We each have other projects and hobbies we prioritize over it but whenever we can we'll work on it for fun. <span role="img" aria-label="sheep">😄</span>


Groupmates: [Nirvan](https://github.com/nirvanKS) and [Darien](https://twitter.com/DarienJardine)