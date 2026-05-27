+++
Description = "Chris and Nick talk to Matthew Skelton"
Date = 2024-11-04T13:00:00Z
PublishDate = 2026-05-27T12:00:00Z # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "71986200/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
guests = ["matthew"] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 3 E3: Matthew Skelton"
#subtitle = ""
images = ["img/TDB-Logo.jpg"]
hosts = ["cswan","nselby"] # The names of your hosts, based on the filename without extension.
#aliases = ["/##"]
#youtube = ""
explicit = "no" # values are "yes" or "no"
#media_override # if you want to use a specific URL for the audio file
#truncate = ""
#upcoming = true # set to true if you want this to be listed as upcoming, etc, etc
#categories = []
#series = []
#tags = []
+++
**Recording date: Nov 4, 2024**

*Download at [Apple Podcasts](https://podcasts.apple.com/podcast/the-tech-debt-burndown-podcast/id1562710899), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### Matthew Skelton

Team Topologies co-author Matthew Skelton joins Chris and Nick to discuss the relationship between tech debt and cognitive load. Matthew explains that every organization has a finite "cognitive load budget," and technical debt acts as a constant drain on this capacity, creating friction that slows down development and increases operational risk. By framing tech debt in terms of human cognition and team boundaries, the discussion highlights how healthy software evolution depends on keeping systems understandable and manageable for the people who build and run them.

The discussion also explores practical tools and frameworks for visualizing and communicating these sociotechnical concepts to non-technical stakeholders. The episode concludes with a (prescient) forward-looking warning about AI generated tech debt. While generative AI promises increased engineering productivity, it risks creating a tidal wave of tech debt. That could potentially be orders of magnitude greater than what humans produce, if the resulting code is not properly understood or maintained.

NB This episode was recorded prior to the release of the [Second edition of Team Topologies](https://teamtopologies.com/book).

#### Show notes (links)

[Team Topologies](https://teamtopologies.com/)

[CodeScene](https://codescene.com/)

[Conflux Proemion case study](https://confluxhq.com/all-success-stories/proemion-optimizes-team-and-system-boundaries-for-flow)

[Architecture Decision Records (ADRs)](https://adr.github.io/)

[Site Reliability Engineering (SRE)](https://en.wikipedia.org/wiki/Site_reliability_engineering)

[Core Domain Charts](https://github.com/ddd-crew/core-domain-charts)


#### Transcript (automated)

Nick: This is the Tech Debt Burn Down podcast. I'm Nick Selby.

Chris: And I'm Chris Swan.

Nick: And we're here today with Matthew Skelton. And Matthew, do you think you could introduce yourself and say what you do for a living?

Matthew: [00:00:30] It's great to be here. So I'm Matthew Skelton. I'm best known as being the co-author of the book Team Topologies, which came out in 2019. My background is in technology, I started off writing software for brain scanning machines, and then I've increasingly got involved in larger and larger systems. And now with my company, Conflux, works with organizations all around the world, typically large enterprises, and we're trying to help them to make those organizations more effective and more humane, particularly when we're building and running software systems. But we're starting to work on areas outside of IT as well.

Nick: This came about because Chris and I were having a chat last week, and Chris mentioned... Well, why don't you go ahead and mention what you mentioned, Chris, 'cause it was really [chuckles] a really good point.

Chris: [00:01:00] So we were talking about tech debt because, of course, that's in the title of the podcast. One of the ways I think we can frame this, one of the lenses we can pick up to look at it is cognitive load. The central theme of Team Topologies is essentially that an organization has a limited capacity of cognitive load. We could almost think of it as a cognitive load budget. We can look at tech debt and its demands upon the organization in terms of the continuous maintenance and the paper cuts to moving forward, and think about that as something that's a drain upon that cognitive load budget, which we might want to try and manage at the same time as we're thinking about using the guidance from Team Topologies to better optimize how that cognitive load is being utilized. And that's why we invited  Matthew here.

Matthew: [00:02:00] So it's good to be here, and I really appreciate it. So for a little bit of context for your listeners, I did a master's degree in neuroscience, so brain science, back in 2000. Now, that's a long time ago. Compared to now, it's nearly, what's that, twenty-four years ago. That was at the University of Oxford. I've got a little bit of context in things relating to cognition, but that was a long time ago, and it was a master's degree, so it's not massively in-depth. So I'm not coming at this just from the perspective of pop psychology or anything like that. Yeah, I was in the pathology lab working with cells or mostly destroying cell cultures actually, because that's what happens when you work in the pathology lab and working on some stuff to do with dyslexia. I'm not claiming to be an expert in cognition or brain science, but I'm not completely an outsider either, just reading the kind of airport books on pop psychology. And that was part of the reason why I was confident to include the idea of team cognitive load in the Team Topologies book. It's one of the central principles inside Team Topologies. It is how we think about what we in the book called the cognitive load on the team as a whole.

Matthew: [00:03:00] Whether we've got that terminology quite correct or not is up for debate, but the central intent I absolutely stand by. So the specific version of cognitive load that we ended up talking about in the Team Topologies book was the one that was promoted by the Australian psychologist John Sweller. He introduced the term in 1988. That particular version of cognitive load theory is sort of debated. There's different interpretations of it. Perhaps it's not the best one, but fundamentally, the intention that we had was this: given the nature of modern business, public sector services and systems and products that are digitally enhanced, they're digitally enabled, i.e. there's some software behind them. Given the nature of those things, they're effectively continuous these days. Think about SaaS, so software as a service. Think about government services, paying your taxes. What about your pension? What about the web application that you use to manage your pensions or the back-end systems that are there to manage your pension pot? That needs to continue for a fair old while, and you want those services to be evolvable for ten, twenty, fifty, seventy years. So there's a need for kind of continuous evolution of these software systems, which is different from what happened in the past because in the past, going into 80s or 90s, even early 2000s, you'd have a new version of a piece of software.

Matthew: [00:04:00] It would get built, it would get burnt onto a CD-ROM or seventy thousand floppy disks, and it would get shipped, and that would be the end of it, effectively. And yes, there'd be a new version coming three or five years later, but there wasn't really a sense of a need for continuous evolution of that thing. The reality now is we absolutely need to think about all the factors that play into the continuous and healthy and sustainable evolution of the modern software systems. That includes AI, it includes agentic and generative AI, whatever pops out of that space, and it's all changing all the time. The same principles apply. We need to make sure that the software that backs these services and products is continuously evolvable, continuously understandable by human beings. That's where this idea of team cognitive load comes from, because if we're building and running these services, which is what we should be doing, because that's the best set of incentives, you can't have one team building and another team running these things. That just sets up the wrong kind of incentives. That's what DevOps came along to try and solve. If we need to be building and running these services on a continuous basis, then we need to acknowledge the fact that a group of people, whatever they're working on, has a limited amount of cognitive capacity, keeping things in their heads.

Matthew: [00:05:00] They're learning new technology. They're learning new regulations. They're learning new concepts. They're learning all the time. They're having to keep this stuff in their head and then trying to represent it in software. That's all coding is, that's all software is, a representation of organizational intent. If we want them to focus mostly on their core mission, we need to be thinking about where the cognitive load is going, effectively, where that cognitive overload or mental overload is actually being used. It's with that context. If you are doing something which is truly one-off, for example, tidying up after a children's Halloween party, there's hopefully no ongoing need to do that tidying up after a Halloween party on an ongoing basis. We just do it. We don't need to really worry about the cognitive load. If, however, we're building something like some sort of pension software or something which has a kind of continuous ongoing nature, we need to be mindful of where that cognitive load is going so that we can evolve this thing in a sustainable way.

Chris: So as we were

Nick: Preparing. You talked about the Ward Cunningham definition and an ideal view of technical debt. Can you give us some words on how often you come across that ideal?

Matthew: [00:06:00] It's a good question. We tend to get called in to help with organizations where there are problems, so we tend to only see the situations where there are problems. But the kind of organization that has few or little problem with technical debt will be the organization that pays enough attention to refactoring, to dealing with the aspects of the software that are kind of grating, annoying to engineers. Those are often good signals for things that are awkward. Or potentially an organization that uses a tool that helps them identify where the risks are and where the technical debt sits. There are various tools out there, but the one that I'm most excited by at the moment is actually one called CodeScene. The organization is going to be doing well in this space, is one that's going to be using a variety of signals to identify where the technical debt is that needs to be addressed and going ahead and addressing it. Most organizations typically don't deal with the increasing friction that comes with that increase in technical debt. It's effectively friction. A given type of feature or new user journey or new thing gets more and more expensive to add because they're not dealing with the existing stuff. It's fundamentally a business problem. It doesn't just get more expensive, it gets more risky because they're not dealing with the risk that's associated with the technical debt as well. Risk and friction, and wonder why things go slowly and wonder why things are expensive.

Nick: I mean, I absolutely love it. You've just encapsulated a lot of my life.

Matthew: Sorry. [laughs]

Nick: [00:07:30] No, it's, it's great. I mean, as I was mentioning earlier, my firm usually comes in when something terrible has happened, and it's usually a security incident or a data breach or something where everything's stopped and, and I've often tried to explain this dynamic of like a  year ago you were likely treading water, and some point between then and now you started taking water over the side. And, and at this point, you're sinking. You're not even able to keep up with what you used to do. Just, it's not about improvement, it's about just flailing to stay alive. You're talking about friction there, and the increase in friction is really important. And I guess my main question for you is that when I come in, it's typical that the teams I'm dealing with, they've got that sort of hollow-eyed look of people who've just; they've been in the engine room, and they know that there's something really terribly wrong, and it's all they can do to focus on just meeting the increasing requirements on them. Requirements from the business, but there's also the requirements of managing this pile of whatever the workload is that they've normally had to do. They don't have, it feels to them, they don't have any extra cognitive space to think about changing what their conditions are. Often what I'll hear is, "Oh yeah, I've had a plan to address that, but I just don't have the time." Chris once showed me the, cartoon of the caveman with the square wheels trying to push, and they're like, "No, I don't have time to swap it out with those round ones." It's a really big battle to say, "Look, the way forward here is to blow it up and, and kind of see where the issues are that we can make improvements to." How can you apply some of the practices that you're, you're going to be talking about and that you have mentioned to, to those kinds of people? Like what are, what are some of the ways when it feels just overwhelming even to think about what I have to do today, let alone making it easier?

Matthew: [00:09:00] Great question. One of the things I've been most excited about in the last, say, six months is our partnership with CodeScene. I would argue the foremost tool in the space of addressing technical debt and code-based health, particularly 'cause it takes a sociotechnical approach to looking at these things. In other words, it doesn't just look at code as a technical thing, it looks at the relationship between code and people. And my company is partnering with them. When we were writing the Team Topologies book, Manuel and I were influenced by the work of Adam Tornhill, who is a CTO and co-founder of CodeScene. He's been working in this space for ten years or something with some open source, I think, and some closed source tools to help look at the relationship between code health and team boundaries and so on. We've just published a case study on the Conflux website about a company called Proemion, based in Europe, who used a combination of insights from us, from some talks I gave and some consulting that we did together with CodeScene to help them actually prioritize what they focus on in terms of technical debt, and crucially, to be able to talk about those problems to people who are not technologists. And actually, time and time again, one of the things that we hear from people that we talk to who use CodeScene is it inspires non-technologists to really understand and start prioritizing work to address technical debt or whatever you want to call it. It was like, "Wow, this is amazing. Now I understand what you technologists are talking about when you say tech debt.

Matthew: [00:10:30] This is about risk. This is about speed, the time to market, and so on. Ah, I get it now. Right. Let's address it." We need to get to the point where we're having conversations with non-technologists about the importance and value of addressing, say, technical debt and code-based health in general, to be honest. And that could be about changing the boundaries of responsibility. It could be changing about how the coupling happens, but it can also be about addressing change hotspots in the code. Because as many of your listeners will know, bugs and errors tend to creep in the areas where the code is changed most frequently. And so you can actually do bug prediction. You're just looking at which areas of code change most often. Well, there's probably going to be a ninety percent chance that a bug is going to happen in this area of the code. It seems like magic, but it's not. It's just inference based on observed patterns. But actually getting non-technologists to buy into this way of thinking using some techniques, persuasion, talks, tools like CodeScene, whatever, feels to me like an absolute essential thing to do. It can't just be about engineers going, "Oh, this is really difficult to work with." That's part of it. That's one of the signals we use. But we need to translate that into business outcomes, whether it's risk or time to value or other things.

Nick: [00:11:30] I've yet to come across an engineering team that's able to articulate in business terms the cost or opportunity cost of technical debt or not maintaining code properly. It's just not a skill that they have. So that's useful to hear. There are contra indicators here, and I'd be really interested in Matthew's experiences with these. When I see organizations that are very intentional about decision-making processes and recording the outcomes of decision-making process in things like an architecture decision record, ADRs, those are places where conversations are happening about

Chris: [00:12:00] Okay, we can do this really quick and dirty thing now, or we can maybe invest more time and effort in doing something a bit more structural now. These are our choices. Which are we going to pick? And what are the trade-offs, and do we understand what future implications might be of path A versus path B? Sometimes intentionally taken on tech debt. There might at least be an understanding of how we got here. We can go back to the decision record and understand how we got here. We can revisit those criteria and decide that things have changed around us. Maybe technology's improved. Maybe we can buy services cheaper. All manner of things that'll make us go back and say, "Yeah, that was the right thing to do at that point in time," but we can reevaluate now and move forward on different bases.

Matthew: [00:13:00] Hundred percent. And there's two things that I'd want to add to that or that relate to that for me immediately. One is the SRE approach that Google have been talking about for a long time, and the second thing is a technique called Core Domain Charts. The first one, Google SRE, if you think about what they codified there with SRE, the product manager or product owner, the person responsible for decisions about that particular product is on the hook for product decisions that result in lower reliability or lower availability, which I think is absolutely essential. It's a very opinionated encoding of that way of working, and it's not for every organization. But the intent behind it is absolutely sound. You've got your error budget. Maybe the error budget's like a mirror of the cognitive load budget. I've just had that thought. That's interesting. You've got your error budget. As a product owner, you can choose to eat into that error budget by doing some stuff which is going to reduce the reliability a little bit. Great. If that's going to achieve a business outcome, go for it. You can choose to make your service less reliable if that's the right thing to do. You can drop the number of nines. You can go from four nines to three nines or down to two nines or two and a half. If that's the right thing for the business outcome, great. Just state it.

Matthew: [00:14:30] Just make it clear. So then you might, in a similar way, take on some technical debt and say, "Well, because effectively we've got a debt budget." Take on some technical debt, make it harder to make that change in the future. Make it explicit to say, "I want to get this feature out the door and to deal with the increased friction and delay that we'll incur as a product team in the future." If you're responsible for that and that aligns with your P&L and everything else, just make it explicit and run with it. But make it explicit, and crucially, the financial results of that have to align with that decision-maker. We need to make it clear to them what the decision that they're making. And so in organizations that are very sales-led or marketing-led and you've got a completely separate budget between sales and IT, those things are not aligned. So you get these behaviors where you just pile on more and more features, and then things get slower and slower, and then business gets more and more agitated. So part of that is actually about aligning the financial and flow metrics incentives properly inside the organization to make it clear what decisions people are really making if they say, "Well, we'll prioritize this feature now." They might still prioritize that feature. It's more important to get this feature out now. We'll increase the friction around feature delivery or changes over the next three months. That's a business decision now. Okay, cool. We'll get behind it.

Nick: [00:15:30] Provided that you have the metrics to count on the technology side and not just the finance side. This is a big thing that many people forget [chuckles] when they're in a sales-driven organization. The numbers get really squishy when they go over to can you deliver these things, and when can you deliver these things? Unless the CTO is incredibly deliberate about how he's setting expectations and against what he will be measured. You can get into some really serious trouble because you're not speaking the same language. You're not even close to speaking the same language.

Matthew: [00:16:00] So just rewinding a tiny bit. The whole SRE approach at least can inform how we think about technical debt. In the case of SRE, it's about reliability. That's what we're really measuring, net uptime. In the case of technical debt, we're measuring the friction and the increased cost around working with this code in order to get something equivalent out the door. Last year it cost ten bananas. This year it's actually costing us fifteen bananas to do this thing because we haven't addressed the underlying technical debt. Is that what you want as a business? Well, no, we don't want that. We want it to be cheaper. Okay. Well, you're going to have to do these things then if you want that metric to be a thing.

Chris: [00:16:30] I was going to say, at risk of going down a rabbit hole, how are you feeling about the confession recently from some of the co-authors of the SRE handbook that they had fibbed a little in describing their work at Google and laid out an idealized view of how they wish things were as opposed to how they'd actually been doing it at the time?

Matthew: [00:17:00] I did see that. It doesn't surprise. It's also nice that they were being honest, but I don't think it takes away from the underlying message for me around SRE. I've been talking about SRE for ages, and there's some stuff about SRE in the Team Topologies book as well. I did actually do a little bit of work with someone from Google, exploring exactly how it works inside Google at the time. I think this was 2018. But the underlying dynamic is absolutely sound, making sure that we're fully connected through to the operational and business implications of our decisions about technology. I think that that's an absolutely sound thing to try and do.

Chris: [00:17:30] I think at the time I saw some risk that there was going to be a shock, horror, politician lies reaction to that, of the SRE authors fibbed a little, so it's all bunk. We can just safely ignore the whole lot. I think, as you say, they had good intentions, that they were describing an ideal that even they themselves perhaps weren't realizing, but that they wished to articulate that ideal-

Matthew: Mm-hmm

Chris: ... rather than simply describe what was going on in, as all organizations are, a messy, complex mix of people and politics and technology and everything else going on.


Matthew: [00:18:00] I have spoken to a couple of the authors. I suspect there's very good intention behind it, and I don't think it reflects on them badly that it might not have all been quite as polished as the book led you to believe.

Nick: Bringing you back, though. You were going to play SRE. You were saying you can go the SRE route or...

Matthew: [00:18:30] There's another lens we can use to think about cognitive load because you set up the question in terms of we made some decisions a while back. It was the right decision at the time. We built this thing. Turns out it shouldn't be the thing that we're building now. We should do something different. We should just use something as a service. There's an API for that now or there's an Amazon or Google Cloud service for doing that thing. Example, some work I did recently with one of our customers. They're a global organization. They deal with a lot of user-generated content for product reviews and that kind of thing. Ten years ago, part of the system they built was a globally distributed database. I think it's using Cassandra or something like that. Anyway, it's the right thing to build at the time because there's nothing available in the cloud providers. Absolutely the right thing to build. In the purest Ward Cunningham sense of the word, that is technical debt, because now we wouldn't choose to build that thing ourselves. We wouldn't choose to build and maintain our own globally distributed data store ourselves. You just get it from a cloud provider. It's all done for you. We don't have to worry about it.

Matthew: [00:19:30] So in that particular case, our cognitive load is higher because we're having to think about all of this underlying plumbing that the cloud providers are doing way better and at better scale. It'd be nice to offload all of that cognitive load to the cloud providers and just consume it as a service. It's taking away valuable cognitive load budget from our people working inside the organization. We had conversations exactly like this. We were workshopping it, and one of the tools that we used in those workshops was an approach called Core Domain Charts. If you search for Core Domain Charts, you'll find the stuff there on GitHub. It's all Creative Commons, open source. People from the domain-driven design community were heavily involved in defining it, particularly Nick Tune. And we've used this loads of times with customers. Very straightforward, very simple. It helps us think about the things that are core to our business from a DDD perspective, the things that are supporting that core area, and the things that are actually generic, and particularly anything that we're currently building ourselves that is in the generic area. In other words, anything that we're building ourselves that actually is available as a service from a cloud provider or another provider somewhere else, clearly we shouldn't really be building anymore.

Matthew: [00:20:30] It's a nice technique that helps us to think through where that purest sense of technical debt currently sits in the organization. That globally distributed Cassandra database was sitting in the generic area, so immediately they could see, "Ah, yeah, that makes a lot of sense. We shouldn't be building that ourselves anymore. Ideally, what's our plan for not building it ourselves?" The Core Domain Charts approach allows you to map things out in time as well. So yes, if you rewind ten years, that globally distributed database was a really important supporting technology. They had to have it. And so that's where it started. But then over time, there's an arrow that points towards generic, because over time, that capability became available from the outside. It's a generic thing as a service. So that particular technique around Core Domain Charts really helps technologists and non-technologists to have a really informed conversation about where we need to focus our cognitive load budget ultimately, to focus our mission and efforts generally across the organization. Really simple, but really nice conversation and exploration approach, particularly if it's facilitated well, that helps people to get to that way of thinking really quickly.

Chris: So that sounds very similar to cases where we've seen Wardley maps being used.

Matthew: Mm.

Chris: [00:21:30] And we had Chris Daniel on the show a little while back talking about how he's been facilitating some of those conversations that way. Frustratingly, we tried to have Simon join us, but the internet wasn't working from his swamp.

Nick: [laughs] He got stuck in the waiting room.

Matthew: He lives somewhere in the middle of nowhere, right?

Nick: Yeah, he mentioned

Matthew: [00:22:00] ... he's got a couple of tin cans and a copper wire for his internet. [laughs] So Wardley mapping, yes, absolutely. The reason why we go to Core Domain Charts first is because Wardley mapping is quite a lot to get your head around for people who are not familiar with it. Whereas Core Domain Charts allows people to go in straight away without all of the background thinking and evolution and so on. Absolutely love Wardley maps, and that's the right place to get to eventually. But Core Domain Charts was a different lens, and it's an easier starting point for some of the people that we've come across who are not technologists and don't necessarily think about things in that kind of evolution.

Chris: It sounds like you're saying, "Don't make people think too hard when they're already tapped out on their cognitive load because of all the-"

Matthew: Exactly.

Chris: "... tech debt they've accrued." [laughs]

Nick: [00:22:30] And that was my question a little bit earlier. Getting into CodeScene, this is important, but that thing about not making people think too much when they're already cognitively overloaded is my main problem that I'm coming up against, which is how can you make this stuff easier and how can you explain the trade-offs that they need to make, the perceived trade-offs? Stop doing this bad thing that you're doing because it's making it worse for you to keep on doing it, and if you just breathe, we can find a better way to do it.

Matthew: Mm-hmm.

Nick: I haven't really found an elegant way to get all the different parties aligned on that. And I think that that's one of the biggest areas of friction that I have in fixing this issue.

Matthew: [00:23:00] I think with a lot of things, it's shared language and visualization. One of the major reasons why the Team Topologies book has become so popular, I think we sold 170,000 copies worldwide, which is amazing.

Nick: Very nice.

Matthew: [00:23:30] One of the reasons there is the strong, clear language that we deliberately defined in Team Topologies, together with the diagramming style, which is also very strong, visual, and colorful. Again, deliberately, because we wanted to use that as a way to anchor some conversations. Tools like CodeScene provide a lot of visualization and opinionated presentation of information, which helps. And that's part of the reason that tool in particular is really good. There are amazing diagrams showing temporal coupling. This piece of code over here always changes at the same time as this piece of code in two completely separate version control repositories. We've detected it, and so you've got a problem here because you're not aware that these two things actually need to change. And visualizations of those couplings become a very powerful way to talk about the problem. A picture paints a thousand words. The visualizations can be really important to help cut through and anchor what we're talking about. It's early days to some extent. I think it's fair to say Team Topologies was the first book that went mainstream that really connected the social and technical aspects of software delivery at scale, the sociotechnical aspect.

Matthew: [00:24:30] There are other books that we've referred to, absolutely. They were shoulders of giants, but I guess it's the first breakthrough book that's really looking at the sociotechnical aspects. And so that was only 2019. CodeScene has come to prominence in the last three or four years. Also takes a very sociotechnical view. It's still relatively new in our industry to be taking this sociotechnical view. People have done it for decades, but in terms of groundswell awareness, sociotechnical angles are still relatively new. So I think it's going to take a while for that stuff to permeate through. A lot of stuff in the domain-driven design community, a lot of stuff coming out of DevOps and Cloud and SRE, thinking about sociotechnical aspects. We'll have to repeat it all again for generative AI and agentic AI, because that's very technology led. Lots of tech bros are trying to pump all the new innovation things, which is just not very much connected to the sociotechnical aspects at the moment.

Chris: But is that because our successive hype waves are normally promising silver bullets?

Matthew: Yes.

Chris: [00:25:30] They're going to just have the solution and it's going to be easy rather than having to grapple with the messy complexity of the situations we find ourselves.

Matthew: Of course, that's a whole separate topic, but the amount of technical debt that generative AI could bring in—you must have done a topic on this. If not, then I'd love to hear it. It could be a hundred or a thousand times the order of magnitude of the tech debt generated by humans, because you might have agentic AI generating all manner of new services and code that humans don't even understand. It's getting deployed out there and running, and then we go, "What's this service? Who knows about this service? What's it doing?"

Chris: What's this line on the cloud bill?

Matthew: [00:26:00] Exactly. [laughs]

Nick: We're going to have to leave it there because we're at time, but Matthew Skelton, thanks very much for joining us.

Matthew: Thank you.

Nick: We really appreciate it.

Matthew: Thank you very much.

Nick: This has been the Tech Debt Burn Down podcast. I'm Nick Selby.

Chris: And I'm Chris Swan. Thanks for listening

