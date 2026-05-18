+++
Description = "Chris and Nick chat about AI coding assistants"
Date = 2026-03-13T10:30:00Z
PublishDate = 2026-05-20T16:20:00Z # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "71975036/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 3 E2: AI Coding Assistants"
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
**Recording date: Mar 13, 2026**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### AI coding assistants

Chris and Nick chat about how AI Coding Assistants have suddenly become very good, maybe even good enough to write 'load bearing' code. So the constraints the existed around producing code have potentially disappeared; but other constraints live on, and we're still finding out what this means for product management.

Some time is spent on whether languages and frameworks still matter, and it seems they do. But also guardrails matter, and if you already have good guardrails built in to a progressive delivery system you're likely better placed to (safely) take advantage of new tools.

#### Show notes (links)

Tracy Bannon, QCon London 2024 - [Applying AI to the SDLC: New Ideas and Gotchas! - Leveraging AI to Improve Software Engineering](https://www.infoq.com/presentations/ai-sdlc/)


#### Transcript (automated with some gentle manual review)

Chris: It's the Tech Dhat Burndown. Hi, I'm Chris Swan

Nick: I'm Nick Selby.

Chris: So in the last episode we were talking about the slot machine and tech debt as a service and how the advances in AI have taken the constraints away from coding, but maybe not helped us as much as we need to in terms of review and making things production ready. But in this episode, I wanted to explore the fact that in 2026, it feels like a lot of this stuff is working in a way that it previously didn't. [00:00:30]

Nick: Yeah, it really is. We were just talking before we were recording two years ago. I think Tracy Bannon at QCon was talking about how AI is a teenage apprentice in a wood shop. You give them very specific tasks, but you have to really watch everything. And now it's changing really, really fast where things actually work. They kind of work more often than they don't.

Chris: Yeah. Over the past few years, I've been frequently returning to the state of the art tools to see if they can help me with my work, right? What I had [00:01:00] been finding was, yeah, they could help me do trivial stuff. They were obviously useful for if you wanted to build a website that was, you know, much like the millions of websites that are out there already. And obviously in the training data. Yeah. I wasn't finding this stuff particularly useful for my work. Right. That's changed completely in 2026.

Nick: By the way, it's March 13th, so to say, you know, in 2026, it's such a such a short timeline.

Chris: Yeah, like what, ten, 11 [00:01:30] weeks into 2026. And it feels like things have just flipped into, into a different state. And so, you know, I've gone from probing at these tools every so often to see how they're improving to using these tools daily. Yeah. As, as part of my working life, I'm increasingly finding myself using this stuff for, for load bearing code, you know, things that are right in front of our customers. Right? One of [00:02:00] the reasons I think I'm doing that is there's aspects of the output that I'm seeing from the models that is not just faster than I would have done it myself, but probably higher quality.

Nick: Whoa. Okay. I never thought I'd hear you say that.

Chris: Things like if I'm having to migrate config, say in my case, I needed to be able to migrate some config from systemd unit files into a Yaml config file. The regex. To do that, I can sure, [00:02:30] I can conceptualize the regex. Yeah. Can I spew forth correct regex? No.

Nick: No.

Chris: And so these are things where I think as engineers, we quite often end up doing a lot of trial and error. Yeah. And this is not something where we're talking about ralphing last time around. This is not something where I'm asking the coding assistant to Ralph it. This is something where the coding assistant has kind of swallowed the regex dictionary. Right? And can actually spew [00:03:00] forth correct regex first time. I still need to to have tests for that, but what I'm finding is it tends to be correct. And I think this, this tending to be correct thing sort of leads me into a conversation I've been having about programming languages. I'm hearing people question whether choice of programming language is, is even a thing that we need to contemplate anymore. Like, why does it matter? Firstly, why can't we just prompt the [00:03:30] coding assistant to do machine language for the instruction set architecture that we want, you know, treat it as a compiler. And, um, we talked a little about compilers in the previous episode, but the compilers that have been made by coding assistants aren't good enough, at least at this stage. And of course that's subject to change. The compilers are actually right now a load bearing part of why language models are more useful for [00:04:00] coding than many of the other applications that they could be put to. The model is is creating some source code, but the compiler is the thing that is checking that it's actually correct, as well as producing a useful artifact out of the other end of it.

Chris: I was talking to a former colleague about how he's using rust for a system that he's building. The set of observations that came out of that was, you know, Rust's very strong in how the toolchain enforces correctness. One obvious implication [00:04:30] of that is you can't feed, you know, bad rust into rust toolchain and get something out at the end of it. So the the model is having to create good rust, but also the model has only been trained on good rust because all of the public examples of rust that are out there are rust that has been able to build. The general quality of rust in the training corpus is really, really good as [00:05:00] opposed to, you know, if we look at probably the other end of the spectrum, the general quality of JavaScript in the training corpus is much more variable. Yes. I think there's there's kind of a spectrum to be taken into consideration here. It's very similar to a spectrum that we might have already thought about, you know, before coding assistance in terms of the fussiness of compilers and the strength of type systems. Yeah. How much, uh, a language and its associated frameworks are going to make [00:05:30] you write correct code.

Nick: We were talking about doing this episode and you were talking about like product managers, and this feeds directly into what you just said. And I'd love to, I'd love to actually get you to jump to there to play that off what you just said.
Chris: So one of the product managers I follow on social media was raising a point from one of his colleagues that product managers are now starting to say, why would they have a meeting to discuss a new feature when it's actually quicker and cheaper to [00:06:00] get the coding assistant to just build the new feature. Yeah, put it out there into at least a progressive deployment environment to, to determine with that normal sort of, you know, A/B tests or red, green or whatever they're doing, you know, whether that feature is desirable and then they've got data.

Nick: Yeah. I have seen every time somebody wants to bypass those meetings and that conversation, that's when I see things that months later [00:06:30] when nothing works. And I don't mean necessarily that that the features aren't doing what they're supposed to be doing, but underlying it, like the, the problems that that it creates or the problems within the production development process that have been created and it's order of operation issues, or it's making sure that the right stakeholders were listened to so that like it does, it appears to do this right feature, but it's not taking into account certain absolute requirements from other parts of the company, like legal right or security or quality. Whenever [00:07:00] you skip those things in the process, you end up in a situation where no one can ever figure out why. We used to be able to do things, and now it all sucks and everything slows down and people get upset. And I'm really skeptical that you can, in fact, do that. What the what those product managers are saying. I know it's so tempting to want to do it. Tony Wheeler at Lonely Planet in like 1998 was doing this thing of like, why do we need to pay translators to translate our books into Swahili [00:07:30] and, you know, like, take our, take our English books and put them into other languages. And we can just use these tools to translate them. And of course, what came out was absolutely, obviously rubbish. This is more dangerous because it looks good and it sort of it does the thing where the functions that you're trying to get do function the way you kind of expect them to, but at a huge cost.

Chris: So I think there might be almost a sort of superficiality test there. So I used the term load bearing. Yeah. [00:08:00] Earlier on. And, and I think there's a there's a consideration to be had there about what's load bearing and what's superficial. Sure. I was talking to Sarah Wells a day or two ago about the difference between policies and standards and, and guardrails.

Nick: Yeah.

Chris: Where that went was guardrails are about making people safe. If we think about guardrails in our built environment, right? [00:08:30] They're normally they stop you running out onto the road in front of traffic. If I think about the guardrails that we put into our systems environment, they're to stop people from doing obviously silly stuff that's going to cause an accident. Yeah. This then brings us on to how are we putting guardrails in place for our use of coding assistant? Some of that is we keep reusing our existing guardrails, assuming that you have them. Yes. And so there might have already been a [00:09:00] substantial investment in delivery pipelines and the ability to do progressive delivery and gather data from A/B testing or whatever it is that we're doing that is ensuring that actually all of this stuff is safe. And if it's safe, it's probably not going to cause the kind of problems that you're referring to. Now, I don't think all organizations actually have all of those guardrails already. And so they might be tempted into unsafe practices. But then there's another thing [00:09:30] here, which is how we're providing context about safety to the coding assistant. There's a lot of discussion presently about things like agent.md files and whether they should even be used or not. Research out of Zurich, I think it was in the last week or so saying, actually, you might be better off without this. MCP was the hotness of the last year or so, but everybody's now talking about skills. Mhm. Do we encode some of the things that we would have had in [00:10:00] our policies and standards or whatever, into skills which the agent is, then going to be using as guardrails because, you know, once again, non-deterministic behavior. Yeah. We can't count on it to really pay attention to that stuff. It's all just part of the context mix as we stir it in.

Nick: Like five years ago when we started this podcast, one of things we were struggling with what is tech debt? And one of the things one of us said was, it's the boring stuff that you ignore because [00:10:30] you want to get down to doing the things that you want to get done. I was just reminded of that when you were saying this stuff about the safety and the guardrails, because the parts that I consider to be unsafe are the unseen, undiscussed things that product and engineering are actually not talking about. It's the it's the inputs that come from customer feedback that doesn't quite make it through a loop because often we get bad at that. We get lazy at that. Or it's the that arcane human knowledge that comes from subject matter experts in places like legal where, [00:11:00] you know, well, you can't do that because this country or these things, this group of our customers does something. And it seems to me that sort of counting on those guardrails, you said, like a lot of companies don't even have very good ones, but the ones that they have tend to be much more binary. Like, we shouldn't do it like this. We should do it like that. And there's a lot of nuance that gets lost when, when you don't have those people having those conversations because an idea will come to somebody and like, oh, wow. Yeah, I didn't even think of that. This wasn't even part of our whole discussion up until this moment. [00:11:30] And I'm afraid that we will lose that if we try to sort of reduce everything to a skill file.

Chris: I think some of what we're touching on here is what complexity, um, scholars would refer to as emergent properties of complex systems. Some of this is unknowable until we try. Yeah. And so we're back to our ralphing. Yeah. Except except it's not the system doing the Ralphing. Now it's the people doing the Ralghing. Of. Yeah, let's try lots of things.

Nick: Or the most dangerous sentence in the English language is why don't you just write [00:12:00] like.

Chris: The most dangerous sentences in the English language is we've always done it like this. But but why don't you just is probably lined up right behind it and giving it a shove in the back. Yeah.

Nick: Every time I make these sort of declarative statements, I have to remind myself that I've radically changed my outlook on some of these things because of the speed that we were talking about. You said ten weeks into this year and suddenly things are working right. And obviously it's not sudden. It's been this incremental thing. And then all of a sudden we hit that point.

Chris: Yeah, [00:12:30] I feel like a breakthrough has been accomplished. And yeah, I was at a Google event last week. They asked everybody to stand up and they went through a seven stage ladder of AI adoption, maturity.

Nick: And making people sit after everyone. Yeah.

Chris: And I was one of the first people to sit down, actually, because I'm still babysitting the tools quite closely. And so sort of, you know, first stage on the ladder was are you still, you know, feeding stuff into a chatbot and pasting the output into your well matured, [00:13:00] um, you know, coding practice. And then it went on to, you know, are you working with an agentic system that's doing this stuff, you know, autonomously for you, but you're supervising it to the extent that you're reviewing every change before it gets committed. This stepped its way through to, you know, people doing the multi-agent framework stuff where they're kind of literally setting it off while they sleep and it's, you know, burning tokens overnight, right? And, [00:13:30] you know, maybe they wake up to some, some gloriously working code and an empty token balance.

Nick: But on most days.

Chris: Yes, it essentially boiled down to have you been able to establish a trust relationship with, with the agentic system that you can let it off the leash and do its thing. And I think there's a flip side to that coin, which is, is what you're working on consequential enough that you need to establish that trust? [00:14:00] Or are you trying out lots of lots of ideas and it really doesn't matter.

Nick: Speaking from the security ghetto, I'm going to say that that last one is almost always wrong and that we are terrible judges of what is consequential and what will be consequential in six months. But I take the point. I really do take the point. And actually, maybe you and I had had a conversation, it was probably a year ago about if agents are writing the code or if AI is writing the code, then humans have to write the tests. And we talked we talked a bit about testing in the last. And like Rolfing, where it's writing [00:14:30] the test. Right. But do you see any change in that that you can actually have it write the own tests, or do you still feel better? And is that affected by the trust relationship, or is this just a constant still, because it was a constant when we talked about it?

Chris: And certainly the practices that most people are talking about encompass test driven development in a way that probably hasn't been widespread in general development practice. The extent to which the tests are being eyeballed is, I think, highly variable. And I, and.

Nick: I.

Chris: And I do [00:15:00] see reports of agents cheating because they do that. But I think also people are coming up with ways to refine that process, at least to, to their satisfaction. You know, if I kind of back up to why I was sitting down early in this process, it's kind of because the things I'm concerned with, I do actually still care a lot about the quality and the detail. So I've not yet let go of that.

Nick: We talked about this yesterday [00:15:30] at lunch. Yeah. It was it was a good point.

Chris: Should the agentic system needs to worry about my notions of code, smells and whatever else and maybe not. Maybe that's too fussy and maybe that's too expensive in terms of engineer supervision versus, you know, that energy could be expressed elsewhere. So we're seeing an argument surface that coding's free. There's no moat now around product. And so we need to focus every [00:16:00] effort on the bottlenecks that live elsewhere. And one of the primary bottlenecks is go to market. Like, how do I, how do I even find customers that are going to care about the thing that I've just dreamt up? It brings us somewhat back to those fundamentals of tech debt, because we might be doing something very expedient to find product market fit and find a customer that cares for that product market fit. But I had one other little note here, which was about how we use the tools. Something I found [00:16:30] a few times in recent adventures is if I ask the platform and this could be just a prompt in a chat, it could even be a prompt going into a coding assistant to do something for me. It might do a pretty terrible job of that.

Chris: So I'll give a concrete example. I had to reconstruct a change log from a git commit history a couple of weeks back. I asked for that to be done and it just did a terrible job of it. So [00:17:00] the the resulting markdown file was incomplete. It was all over the place in terms of formatting. Thoroughly unsuitable. Yeah. So instead I asked for a Python script to do the job for me. Not only was the Python script that was produced a beautiful. Very good. I was using Gemini, so it was a very Googley kind of Python script. So in compliance with their coding standards and lots of good comments and very sort of thorough in how it was making use of [00:17:30] the present idioms, but also produced an absolutely perfect changelog from, from the git commit history. According to what I was was trying to accomplish, it needed a couple of iterations to, to refine it to the point that it was exactly what I wanted it kept on doing that, that iterative improvement, and it took minutes to get to the finished article and crank the handle and get the changelog out at the end of it.

Nick: Are you still surprised when that happens? Because I am every time, every [00:18:00] time I get something, it's like, that's quite good actually. Oh, I want to change this. And then you go through and then you're there and it's just like, that was why we talk about this stuff.

Chris: Well, I think this use of tool thing is something that is going to iterate upon itself. Right now. We sometimes ask the LLM to do something and it does a bad job, but if we ask it to use a tool to do it, it does a better job. And I think what we're seeing with the coding assistants and agentic practices is we're [00:18:30] essentially embedding that tool usage. And even in some cases, tool discovery into that iterative process. From that comes improvement.

Nick: We can leave it there. That was really cool. Oh, it's been the Tech Debt Burndown podcast. I'm Nick Selby.

Chris: And I'm Chris Swan. Thanks for listening.
