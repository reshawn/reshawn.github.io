---
title: A Journey From Farm to Fork
# The Food Map Project
# A Journey from farm to fork
date: "2019-09-13T12:52:32.169Z"
template: "post"
draft: false
slug: "/posts/a-journey-from-farm-to-fork"
category: "Portfolio Blog"
tags:
  - "Traceability"
  - "Decentralized App"
  - "Blockchain"
description: "Building a decentralized app for trustworthy tracing of local produce and groceries from farm to fork."
---



*TLDR: Here's the [github](https://github.com/Darien117/BreadTrail) and [article](https://ictupdate.cta.int/en/article/breadtrail-from-farm-to-fork-sid0d09597e5-ff83-4e8c-a35c-ef2cee477dbe)*

## Inspiration
During my final semester of undergrad, the computing department hosted a weekend long hackathon in conjuction with the agriculture department. The theme was 'Hack Against Hunger', revolving around ideas that could contribute to reducing world hunger. It was open to anyone up to a certain age (I think 30 or 40 but I can't remember exactly), the winner would go to the WSIS Hack Against Hunger in Switzerland. It was just one weekend and sounded like fun so my usual group of friends and I gathered and joined.

Since entry wasn't limited to undergrads there were a lot of post grads and past students participating as well. Some of them were even assistant lecturers that taught us, including one in particular who we really looked up to. We were far from confident and ultimately decided it might make more sense to do a project following the theme but using something we were interested in learning rather than stick to the requirement of using certain data in our ideas. The fact that we had an interest in blockchain and decentralized apps made this appealing. This way we would learn what we wanted to, building a decentralized app, with the motivation and pressure to complete coming from the hackathon, even if it meant losing by default.

But maybe we were just trying to avoid competing against the others. Against those teaching assistants who we looked up to, we, or at least I, considered loss inevitable and that was the wrong attitude to hold.
If I was willing to learn how to build a decentralized app in a weekend I could've been willing to learn some data science in a weekend, the difference wasn't the perceived difficulty or fear of unknown, it was a fear of trying to compete and failing. 

*How could we truly lose if we chose an idea that couldn't win?* was the mentality here. I consider this my biggest mistake with regards to this project, my lack of confidence. Of course its easy to look back on it now, at the time however, understanding my own emotions wasn't so simple. So I don't regret what happened here, it was a lesson in self-confidence.

We committed to blockchain and wanted to focus on ideas that could benefit small farmers. Eventually we came across some articles on the use of blockchain in supply chain management and the importance of farm to fork trace-ability. It wasn't a unique idea but we had only found 1 or 2 results of it being done at the time. The idea itself also seemed pretty case by case since supply chains are so unique. Therefore we thought applying it to Trinidad and the Caribbean would be a good idea, focusing on bringing benefits to the small farmer as much as the bigger companies.

After a lot of back and forth and wondering if blockchain was worth it here or just a hype-train, the idea was farm to fork trace-ability. We wanted to help small farmers gain visibility and trust by allowing customers to see the path of the produce they're buying via a decentralized app they could trust. We called it Bread Trail.
![](/media/BreadTrailSplash.png)

## Building it
Even though decentralized apps were fairly new at the time there was still an active community and friendly tools shaped around it. We used solidity and ethereum (with ropsten testnet) since it stood out as the blockchain as a platform option. With more time now we would consider hyperledger fabric or some other private blockchain that's better suited to the use-case of a closed supply chain.

We had some Ionic boilerplate code from previous projects so we went with that for the front-end and to avoid having every user need an ethereum wallet, we used the infura API (doing this added to the argument that a public blockchain isn't necessary but we didn't stress over it).

Naturally, we didn't sleep that weekend and worked almost non-stop for the 48 hours, we faced a lot of problems and misunderstandings in writing the solidity contract and decentralized code but in the end we got it all to work. To be completely honest I really don't remember most of the problems we faced in doing this stuff. What I do remember clearly is how triumphant we felt when we were able to read and write to the testnet from our app. One of us jokingly said "*in a way we spent all weekend just trying to read and write data to a fancy database huh?*" and some pained laughter followed.

As for the competition, we didn't feel like we presented as well as we could've since we spent so much time on the app itself, but the judges still liked our idea and thought it was unique at the event. They also expressed their disappointment in how we didn't incorporate the use of data strongly enough, so we didn't crack top 3 but amongst ourselves we considered that to mean an unofficial 4th :D . 

One senior lecturer from our department especially liked the idea since she did a lot of work in agriculture technology and heard about blockchain's potential benefits in the space. She was proud that her undergrads took enough of an interest to try it.

Not long after the event, a technology in agriculture magazine, [ICT Update]( https://ictupdate.cta.int/en), sent out a call for blockchain articles and that same lecturer thought of us, offering to help us write a submission. With the help of our favourite mentor-like lecturer and her, we wrote the article which got accepted and published ([here](https://ictupdate.cta.int/en)).

It didn't really stop there either, a host/organizer for another local hackathon type competition read the article and reached out because he remembered my name from the years I previously participated. He encouraged us to enter again as he thought the idea was a great fit to their theme, "*Innovating the Coconut Industry*". So we did, we went through the different phases of the competition, building out a different version of Bread Trail that satisfied its criteria and in the end we won this one.

![](/media/TCJ.jpg)

Part of winning meant Bread Trail got selected, along with another group, to present at the Caribbean Week of Agriculture in Barbados. This was part of an initiative by the main sponsoring group, a regional agriculture research institute. Unfortunately only one of us could go, that person happened to be me. I felt rather disappointed that we couldn't all go and it definitely felt wrong to present our work without them but in the end all I could do was try to make the most of it. 

To summarize, the half a week in Barbados for the conference was great, I met a lot of interesting people and learnt a great deal about a field I previously paid little mind to, like how much potential coconuts have in the Caribbean and how important they are to Caribbean identity. 
What stood out most from that time period however was meeting a Guyanese large scale farmer. We stayed at the same hotel so spent a lot of time talking. I could probably write a post in itself about his interesting stories and everything I learnt from those conversations. 


A couple months later someone from IBM was having a seminar on blockchain at a local post grad business school and they were looking for uses cases to be part of the seminar. Through recommendation they asked my friends and I to present Bread Trail so we went along. This might sound overly negative but the presentation really didn't go well. There was a big miscommunication at the time that meant a teammate wasn't there and his part was left for me to improvise. People still complimented and wished us well at the end though, after all we were so young and awkward they hadn't really expected much. We also ran into someone I met from hackathons that started his own company and was interested in helping us with the business side of things on Bread Trail. 

![](/media/ibm.jpeg)

Prior to this we had sorta just kept Bread Trail as a casual project we work on when need be, neither committing to it nor dropping it. At this point we needed a more solid decision before responding. 
It was the push we needed to get together and discuss how we feel about the project, and the general agreement was that we don't really enjoy it anymore, the idea was meant to be for a fun weekend to learn some stuff. With everything else that kept happening it just felt like a waste to not do more and we ended up pressuring ourselves to work on something we no longer cared about. Once we realized this, our decision was easy.

We then explained things to the person that offered help and thanked him for doing so, having met him several times before he seemed like a really nice guy so we really were grateful.

## Challenges
Presentations were a consistent source of challenges throughout our time on Bread Trail. We were used to presenting projects with much more visual output, here we were just presenting data and had to keep explaining a lot of concepts just to get to the point of the idea. This is where our weaker presentation skills showed because a lot of the concepts we didn't fully grasp or couldn't remember it all to explain. So staying within time frames and speaking coherently as a team was more of a challenge than usual.

Other than that, aside from technical challenges the biggest hurdle was deciding whether or not to continue. From the get-go we had the support of a senior lecturer that liked our idea. Events and chances to do more kept coming our way because of her initial help. We just wanted to learn something new and have a good weekend. We didn't pick the idea planning to have any level of commitment but it felt like a waste for us to not make the most of it and we didn't want to let her down.

## Lessons
### Presenting
Our presentations probably weren't that awful. I'm certainly (but more so hopefully <span style="font-style:normal" role="img" aria-label="sheep">😂</span>) just remembering them to be worse than they actually were but nonetheless I wasn't happy with my contributions to them. I realized with some projects, being able to confidently present as if talking to friends just doesn't come as naturally to me as others. So I learnt I need to recognize when this is the case and spend more time preparing, by getting comfortable with what I have to say and the key things I want people to learn or feel from what I say, rather than just memorizing a speech or winging it.

### Stick to the point
As we got further along, benefiting small farmers and reducing world hunger became less and less of a goal. Staying true to this was an important aspect we missed, had we focused on that more, and spoke to more farmers than business people, maybe the purpose of helping others would've stood out more in the project and retained our interest/excitement. I'm sure our lecturer could've helped us figure out a way forward that focused on this as well, but we got distracted by the external interest we received and by our own split decision. Now that I think about it, my previous Doubles Run post had a similar lesson as well. Remembering why I started something and keeping it in mind as important seems to be more difficult than I thought. I'm sure it'll happen again too, but I hope I'll remember writing this down and be able to improve.

## Final Thoughts
I'm glad bread trail didn't just slowly fizzle out of our lives, it ended as a group decision that we carefully considered together. As usual, there were a number of things that could've been done better, individually and as a team. Those mistakes bothered me a lot for some time but eventually I was glad to have made and learn from them early on.

When I started writing this I didn't think much of my time on Bread Trail compared to other projects like Doubles Run, I just thought I should write on it since we were at so many events because of it. After reliving the memories to put them in words I realize now I had just forgotten how meaningful these times were, and I'm happy with my decision to write on it.


Groupmates: [Nirvan](https://github.com/nirvanKS) and [Darien](https://twitter.com/DarienJardine)



