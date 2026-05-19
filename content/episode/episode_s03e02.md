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


#### Transcript (automated)

Chris: It's the Tech Debt Burndown. Hi, I'm Chris Swan.

Nick: I'm Nick Selby.

Chris: [00:00:30] In the last episode we were talking about the slot machine and tech debt as a service, and how the advances in AI have taken the constraints away from coding but maybe not helped us as much as we need to in terms of review and making things production ready. In this episode, I wanted to explore the fact that in 2026, it feels like a lot of this stuff is working in a way that it previously didn't.

Nick: Yeah, it really is. We were just talking before we were recording. Two years ago, I think Tracy Beynon at QCon was talking about how AI is a teenage apprentice in a wood shop. You give them very specific tasks, but you have to really watch everything. Now it's changing really, really fast. Things actually work. They kind of work more often than they don't.

Chris: [00:01:00] Over the past few years, I've been frequently returning to the state of the art tools to see if they can help me with my work. What I had been finding was, yeah, they could help me do trivial stuff. They were obviously useful if you wanted to build a website that was much like the millions of websites already out there and obviously in the training data. I wasn't finding this stuff particularly useful for my work. That's changed completely in 2026.

Nick: By the way, it's March 13th, so to say "in 2026" is such a short timeline.

Chris: [00:01:30] Yeah, what, ten, 11 weeks into 2026. It feels like things have just flipped into a different state. I've gone from probing at these tools every so often to see how they're improving, to using these tools daily as part of my working life. I'm increasingly finding myself using this stuff for load bearing code, things that are right in front of our customers. One of the reasons I think I'm doing that is there's aspects of the output I'm seeing from the models that is not just faster than I would have done it myself, but probably higher quality.

Nick: Whoa. Okay. I never thought I'd hear you say that.

Chris: [00:02:30] If I'm having to migrate config, say in my case, I needed to migrate some config from systemd unit files into a YAML config file. The regex. I can conceptualize the regex. Can I spew forth correct regex? No.

Nick: No.

Chris: [00:03:00] These are things where I think as engineers, we quite often end up doing a lot of trial and error. This is not something where we're talking about ralphing like last time around. This is not something where I'm asking the coding assistant to ralph it. This is something where the coding assistant has kind of swallowed the regex dictionary and can actually spew forth correct regex first time. I still need to have tests for that, but what I'm finding is it tends to be correct. This tending to be correct thing sort of leads me into a conversation I've been having about programming languages. I'm hearing people question whether choice of programming language is even a thing we need to contemplate anymore. Why does it matter? Firstly, why can't we just prompt the coding assistant to do machine language for the instruction set architecture that we want, treat it as a compiler. We talked a little about compilers in the previous episode, but the compilers that have been made by coding assistants aren't good enough, at least at this stage. Of course, that's subject to change. The compilers are actually right now a load bearing part of why language models are more useful for coding than many of the other applications they could be put to. The model is creating some source code, but the compiler is the thing checking that it's actually correct, as well as producing a useful artifact out of the other end of it.

Chris: [00:04:30] I was talking to a former colleague about how he's using Rust for a system he's building. The set of observations that came out of that was, Rust's very strong in how the toolchain enforces correctness. One obvious implication of that is you can't feed bad Rust into the Rust toolchain and get something out at the end of it. The model is having to create good Rust, but also the model has only been trained on good Rust because all of the public examples of Rust out there are Rust that has been able to build. The general quality of Rust in the training corpus is really, really good, as opposed to, if we look at probably the other end of the spectrum, the general quality of JavaScript in the training corpus is much more variable. I think there's kind of a spectrum to be taken into consideration here. It's very similar to a spectrum we might have already thought about before coding assistants in terms of the fussiness of compilers and the strength of type systems. How much a language and its associated frameworks are going to make you write correct code.

Nick: We were talking about doing this episode and you were talking about product managers, and this feeds directly into what you just said. I'd love to get you to jump to there to play that off what you just said.

Chris: [00:06:00] One of the product managers I follow on social media was raising a point from one of his colleagues that product managers are now starting to say, why would they have a meeting to discuss a new feature when it's actually quicker and cheaper to get the coding assistant to just build the new feature. Put it out there into at least a progressive deployment environment to determine, with the normal sort of A/B tests or red, green or whatever they're doing, whether that feature is desirable. Then they've got data.

Nick: [00:06:30] I have seen, every time somebody wants to bypass those meetings and that conversation, that's when I see things that months later nothing works. I don't mean necessarily that the features aren't doing what they're supposed to be doing, but underlying it, the problems that it creates or the problems within the production development process that have been created, and it's order of operation issues, or it's making sure that the right stakeholders were listened to so that it appears to do this right feature, but it's not taking into account certain absolute requirements from other parts of the company, like legal or security or quality. Whenever you skip those things in the process, you end up in a situation where no one can ever figure out why we used to be able to do things, and now it all sucks and everything slows down and people get upset. I'm really skeptical that you can in fact do that, what those product managers are saying. I know it's so tempting to want to do it. Tony Wheeler at Lonely Planet in like 1998 was doing this thing of, why do we need to pay translators to translate our books into Swahili and take our English books and put them into other languages? We can just use these tools to translate them. Of course, what came out was absolutely, obviously rubbish. This is more dangerous because it looks good and it sort of does the thing where the functions you're trying to get do function the way you kind of expect them to, but at a huge cost.

Chris: [00:08:00] I think there might be almost a sort of superficiality test there. I used the term load bearing earlier on. I think there's a consideration to be had there about what's load bearing and what's superficial. I was talking to Sarah Wells a day or two ago about the difference between policies and standards and guardrails.

Nick: Yeah.

Chris: [00:08:30] Where that went was, guardrails are about making people safe. If we think about guardrails in our built environment, they normally stop you running out onto the road in front of traffic. If I think about the guardrails we put into our systems environment, they're to stop people from doing obviously silly stuff that's going to cause an accident. This then brings us on to how are we putting guardrails in place for our use of coding assistants. Some of that is, we keep reusing our existing guardrails, assuming you have them. There might have already been a substantial investment in delivery pipelines and the ability to do progressive delivery and gather data from A/B testing or whatever it is we're doing that is ensuring all of this stuff is safe. If it's safe, it's probably not going to cause the kind of problems you're referring to. I don't think all organizations actually have all of those guardrails already, and so they might be tempted into unsafe practices. There's another thing here, which is how we're providing context about safety to the coding assistant. There's a lot of discussion presently about things like agents.md files and whether they should even be used or not. Research out of Zurich, I think it was in the last week or so, saying actually you might be better off without this. MCP was the hotness of the last year or so, but everybody's now talking about skills. Do we encode some of the things we would have had in our policies and standards or whatever into skills, which the agent is then going to be using as guardrails? Because, once again, non-deterministic behavior. We can't count on it to really pay attention to that stuff. It's all just part of the context mix as we stir it in.

Nick: [00:10:30] Like, five years ago when we started this podcast, one of the things we were struggling with: what is tech debt? One of the things one of us said was, it's the boring stuff you ignore because you want to get down to doing the things you want to get done. I was just reminded of that when you were saying this stuff about the safety and the guardrails, because the parts I consider to be unsafe are the unseen, undiscussed things that product and engineering are actually not talking about. It's the inputs that come from customer feedback that doesn't quite make it through a loop because often we get bad at that, we get lazy at that. Or it's that arcane human knowledge that comes from subject matter experts in places like legal where, well, you can't do that because this country or these things, this group of our customers does something. It seems to me that sort of counting on those guardrails, you said, like a lot of companies don't even have very good ones, but the ones that they have tend to be much more binary. We shouldn't do it like this, we should do it like that. There's a lot of nuance that gets lost when you don't have those people having those conversations, because an idea will come to somebody and like, oh, wow, yeah, I didn't even think of that. This wasn't even part of our whole discussion up until this moment. I'm afraid that we will lose that if we try to sort of reduce everything to a skill file.

Chris: I think some of what we're touching on here is what complexity scholars would refer to as emergent properties of complex systems. Some of this is unknowable until we try. So we're back to our ralphing. Except, except it's not the system doing the ralphing now. It's the people doing the ralphing. Yeah, let's try lots of things.

Nick: [00:12:00] The most dangerous sentence in the English language is, "why don't you just..."

Chris: The most dangerous sentence in the English language is, "we've always done it like this." But "why don't you just" is probably lined up right behind it and giving it a shove in the back.

Nick: Every time I make these sort of declarative statements, I have to remind myself that I've radically changed my outlook on some of these things because of the speed that we were talking about. You said ten weeks into this year and suddenly things are working. Obviously it's not sudden, it's been this incremental thing. Then all of a sudden we hit that point.

Chris: [00:12:30] Yeah, I feel like a breakthrough has been accomplished. I was at a Google event last week. They asked everybody to stand up and they went through a seven stage ladder of AI adoption maturity.

Nick: And making people sit after everyone.

Chris: [00:13:00] I was one of the first people to sit down, actually, because I'm still babysitting the tools quite closely. First stage on the ladder was, are you still feeding stuff into a chatbot and pasting the output into your well matured coding practice? Then it went on to, are you working with an agentic system that's doing this stuff autonomously for you, but you're supervising it to the extent that you're reviewing every change before it gets committed? This stepped its way through to people doing the multi-agent framework stuff where they're kind of literally setting it off while they sleep and it's burning tokens overnight. Maybe they wake up to some gloriously working code and an empty token balance.

Nick: But on most days.

Chris: [00:14:00] It essentially boiled down to, have you been able to establish a trust relationship with the agentic system that you can let it off the leash and do its thing? I think there's a flip side to that coin, which is, is what you're working on consequential enough that you need to establish that trust? Or are you trying out lots of ideas and it really doesn't matter?

Nick: [00:14:30] Speaking from the security ghetto, I'm going to say that that last one is almost always wrong, and that we are terrible judges of what is consequential and what will be consequential in six months. But I take the point. I really do take the point. Actually, maybe you and I had had a conversation, it was probably a year ago, about, if agents are writing the code or if AI is writing the code, then humans have to write the tests. We talked a bit about testing in the last episode, and like ralphing, where it's writing the test. Do you see any change in that, that you can actually have it write the own tests? Or do you still feel better? Is that affected by the trust relationship, or is this just a constant still, because it was a constant when we talked about it?

Chris: Certainly the practices that most people are talking about encompass test driven development in a way that probably hasn't been widespread in general development practice. The extent to which the tests are being eyeballed is, I think, highly variable.

Chris: [00:15:00] I do see reports of agents cheating because they do that. But I think also people are coming up with ways to refine that process, at least to their satisfaction. If I kind of back up to why I was sitting down early in this process, it's kind of because the things I'm concerned with, I do actually still care a lot about the quality and the detail. I've not yet let go of that.

Nick: [00:15:30] We talked about this yesterday at lunch. It was a good point.

Chris: [00:16:00] Should the agentic system need to worry about my notions of code smells and whatever else? Maybe not. Maybe that's too fussy and maybe that's too expensive in terms of engineer supervision versus that energy could be expressed elsewhere. We're seeing an argument surface that coding's free. There's no moat now around product. So we need to focus every effort on the bottlenecks that live elsewhere. One of the primary bottlenecks is go to market. How do I even find customers that are going to care about the thing I've just dreamt up? It brings us somewhat back to those fundamentals of tech debt, because we might be doing something very expedient to find product market fit and find a customer that cares for that product market fit. I had one other little note here, which was about how we use the tools. Something I found a few times in recent adventures is, if I ask the platform, and this could be just a prompt in a chat, it could even be a prompt going into a coding assistant, to do something for me, it might do a pretty terrible job of that.

Chris: [00:17:00] I'll give a concrete example. I had to reconstruct a changelog from a git commit history a couple of weeks back. I asked for that to be done and it just did a terrible job of it. The resulting markdown file was incomplete. It was all over the place in terms of formatting. Thoroughly unsuitable. So instead I asked for a Python script to do the job for me. Not only was the Python script that was produced very good, I was using Gemini, so it was a very Googley kind of Python script, in compliance with their coding standards and with lots of good comments and very thorough in how it was making use of the present idioms, but also produced an absolutely perfect changelog from the git commit history. According to what I was trying to accomplish, it needed a couple of iterations to refine it to the point that it was exactly what I wanted. It kept on doing that iterative improvement, and it took minutes to get to the finished article and crank the handle and get the changelog out at the end of it.

Nick: [00:18:00] Are you still surprised when that happens? Because I am, every time. Every time I get something, it's like, that's quite good actually. Oh, I want to change this. Then you go through and then you're there and it's just like, that was why we talk about this stuff.

Chris: [00:18:30] Well, I think this use of tool thing is something that is going to iterate upon itself. Right now, we sometimes ask the LLM to do something and it does a bad job, but if we ask it to use a tool to do it, it does a better job. I think what we're seeing with the coding assistants and agentic practices is we're essentially embedding that tool usage, and even in some cases tool discovery, into that iterative process. From that comes improvement.

Nick: We can leave it there. That was really cool. It's been the Tech Debt Burndown podcast. I'm Nick Selby.

Chris: And I'm Chris Swan. Thanks for listening.