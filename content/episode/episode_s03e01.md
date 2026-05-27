+++
Description = "Chris and Nick chat about Tech Debt as a Service"
Date = 2026-03-13T10:00:00Z
PublishDate = 2026-05-13T16:20:00Z # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "71974895/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 3 E1: Tech Debt as a Service"
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

*Download at [Apple Podcasts](https://podcasts.apple.com/podcast/the-tech-debt-burndown-podcast/id1562710899), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### Tech Debt as a Service (Welcome to the Slopocene) ####

After a long hiatus, the Tech Debt Burndown podcast has returned for its third season. We've got a bunch of episodes (some recorded quite a while ago) in the can, so more to come; along with some fresh stuff, as 2026 has been a wild ride already.

Chris Swan and Nick Selby kick off the season with a discussion of what Chris has called Tech Debt as a Service: how we’ve entered the slopocene, and how we are working with our magical AI coding assistants.

We start with a discussion of multi-agent coordination frameworks, one of which is called Ralph Wiggum, and what's become termed as 'ralphing' is basically sending the coding assistant into a loop until it has successfully met some success criteria in order to exercise the loop: It's kind of going round and round, and maybe doing lots of pretty dumb stuff, but it keeps trying, right? And you don't let it stop until it's got to where you want to go. You'll probably also define some kind of max loop criteria so you’re not just burning tokens all day long . . .

#### Transcript (automated with some gentle manual review)

Nick: It's the Tech Debt Burndown podcast. I'm Nick Selby.

Chris: And I'm Chris Swan.

Nick: We're here to talk about Ralph Wiggum. And Chris, why don't you kick us off, please?

Chris: [00:00:30] So the theme for this episode I thought was going to be essentially how we entered the slopocene and how we can get tech debt as a service from our magical AI coding assistants. I guess one of the things that we opened 2026 with was the arrival of these multi-agent coordination frameworks, one of which is called Ralph Wiggum. Yeah, I prepared some notes ahead of this. And Nick asks, what are you, Ralph Wiggum? Why are you talking about Ralph Wiggum? Isn't that just the kid off of The Simpsons? And I said, yes, that was worse.

Nick: Wasn't it the chief of police off The Simpsons? And then you had to remind me of the boy.

Chris: [00:01:00] And so what they're doing here with what's become termed as ralphing, is basically sending the coding assistant into a loop until it has successfully met some success criteria in order to exercise the loop. It's going round and round and maybe doing lots of pretty dumb stuff, but it keeps trying, right? And you don't let it stop until it's got to where you want to go. You'll probably also define some kind of max loop criteria. So it's not infinitely doing dumb stuff and chewing through tokens and running up a bill. But yeah, that's what people are doing now.

Nick: [00:01:30] Of course, my definition of ralphing is shouting groceries or vomiting. So when you just said that, I guess it all makes sense.

Chris: [00:02:00] I was looking up ralphing on the way in, the Urban Dictionary definition is vomiting stuff up. And so yeah, I feel we're getting our AI agents to vomit stuff up until we're satisfied with the vomit. And it's passing tests that it's written for itself according to its interpretation of a prompt. And it's not just Ralph Wiggum. At the same time as that was hitting the scenes, there was another similar framework called Gastown that came along from Steve Yegge. And so I think Steve's quite a famed developer and has done some amazing blog posts that have captured people's attention over the years. More recently, I've seen Steve working a lot with Gene Kim, and they've written their book together about vibe coding. If we look at what's become of Gene's DevOps event, it's now more focused on enterprise, but very much more focused on AI and AI adoption and how things like vibe coding and the use of these multi-agent frameworks is starting to take effect.

Nick: [00:03:00] So that's actually a good thing. We were talking about the book that we're writing, and we were just talking yesterday about the lead time. So now you take a look at Gene's book and even some of the stuff earlier in the season that we were just discussing. So has Gene's book already been overtaken by events?

Chris: [00:03:30] I think so, yeah. Gastown went from zero to huge in the space of days at the start of the year. And I should also tip a hat to Ruv Cohen because if I look at people using these multi-agent frameworks, as far as I could tell, it really began with Ruv and his work on this stuff. And then other people have created similar frameworks to enable that. And lots more people are now picking those things up and running along with them. I also feel there's something of a fruit machine mentality going on here. So we talk about tokens and here we are recording this at Brighton Seaside. And so we could step out and find an amusement arcade not very far away. And we could probably buy a bunch of tokens and feed them into slot machines and pull the handle and see whether we win.

Nick: Right.

Chris: And I've got a sense right now that a lot of the LinkedIn posts about this are coming from people who've stuffed their tokens in the machine, and they've pulled the handle and it's come up, bar bar bar, and it's paid out the jackpot: they got something useful. And the people not writing LinkedIn posts about this are people who put their tokens in the machine and they've pulled the handle and it's come up cherry melon bell. Yeah. Let's go again.

Nick: [00:04:30] Yes. I think that the great unwashed is basically a bunch of older Parliament-smoking women sitting in the back of the casino, just with the giant bucket of tokens and continuing to put them in to see if you win. And it's always a big surprise.

Chris: [00:05:00] The most insane thing, I think, is if you look at the economics behind this—and I think he's been doing an excellent job in recent months of exploring this—they're selling the tokens to us at pennies on the dollar, the data centers and everything that's happening behind these tokens are all being carried by SoftBank and other deep-pocketed investors right now. Or Nvidia is feeding money into the system so that people will buy its GPUs.

Nick: Right. And get hooked like any good dealer does. Yes.

Chris: And so I feel we might be in an Uber moment in that period where all of the Uber rides were subsidized.

Nick: Yes, yes.

Chris: [00:05:30] Yeah. We're then waiting for how useful is all of this going to be when we're actually having to pay full freight for the tokens?

Nick: I would like to just zoom back now. Right. Let's give the higher-level introduction to what it is that we're talking about and introduce the concept of tech debt as a service. And it's really compelling to just want to create it because you can do so much and feel so creative so quickly that before you know it, you're left with a giant pile of tech debt.

Chris: [00:06:00] One of the factors that's really captured my attention here is the notion that we should no longer be looking at the code. You come up with your plan. You dispatch your multi-agent coordination framework to implement the plan. It's doing test-driven development. So it's creating a whole bunch of tests that are going to persuade you that the plan has been implemented correctly.

Nick: Some of the best comments ever, by the way. Done. It's good.

Chris: [00:06:30] And then we get software out of the end of this process, but no human being is actually going line by line through that software and seeing that they're comfortable with that. We're taking our comfort from the test running. And I think in some ways, this is what we do all the time with continuous delivery. And progressive delivery is we're feeding change into a pipeline, and we're taking confidence and safety from our tests. And then new stuff is emerging from the pipeline. And we're doing our canary deployments or our feature flags or whatever else to ensure that it's behaving as we want it to. But this feels like much more wholesale change. We're cutting new things from clean cloth and stuffing them through the pipeline for the first time and expecting them to emerge into the world fully formed and ready to go, rather than, I think, continuous delivery and progressive delivery, even more so. We're all about tiny incremental changes where we're moving forward a tiny bit at a time, but we're always making forward progress.

Nick: [00:08:00] Yeah. And it's funny, that has actually become a cultural thing. I did a podcast with a bunch of folks for Bishop Fox a couple of weeks ago. And the question was, does this all save time? The consensus was not really, but developers are spending more of their time thinking about what they want to do and deliberately writing out the prompts so that when it gets generated... So now the code just happens in seconds. But you're right, there's a missing piece there at the end where you take a look at it and see did it actually work, or is it just passing the test that it wrote for itself?

Chris: I think there's an aspect of this: not looking at the code, which I'm willing to accept as the introduction of a new abstraction layer. One of the comments I saw from...

Nick: A nice comment that's really...

Chris: [00:08:30] ...good from one of the industry elders, was how much of us look at the bytecode that emerges from a compiler, or the machine code that emerges from a compiler? And the answer is almost none.

Nick: I know one person in my entire life who would do that because he thinks it's neat.

Chris: [00:09:00] I think there are occasions when you're having to focus on very specific performance optimization that you might actually be diving into: what has the compiler done with my source code and how is it emerging and how is it actually interacting with the instruction set architecture of the machine I'm going to run it on? Most of the time, most people are not looking at compiler output. And so if we say that we've moved up an abstraction layer, we're no longer dealing with programming languages, we're just dealing with prompts. Then the coding output of the prompt becomes like the output of the compiler. Now there is a very strict differentiation here, which is compilers are deterministic. Yes. They're going to give us the same output.

Nick: Yeah. You run it 15 or 15,000 times.

Chris: [00:09:30] Every time, whereas large language models are non-deterministic. We can't expect that repeatability that I think we're used to with compilers. And I think I'm going to dive down a little rabbit hole as well here, because one of the things that's happened in recent weeks was Claude actually was prompted to create a compiler. So this was a project that was done at Anthropic, and they got to a compiler that was able to compile the Linux kernel.

Nick: Okay.

Chris: [00:10:00] And this was something that they completed in about two weeks, and they spent about $20,000 of tokens on it. So not enormously expensive. It was all enabled by the fact that compilers have got great test suites. And can we know the things going through? Compilers have test suites. And so we can see when something is converging on being correct. The destination I'm trying to get to here is they made a functioning compiler, but it's terrible. And so all of that effort that's gone into GCC and LLVM, etc. over the years to create a high quality, performant, correct compiler was not there in the product. And so when people were performance benchmarking the code coming out at the end of this thing, it was in some cases hundreds of times slower than the equivalent code. And I think this relates back to this notion of dealing with abstraction layers. So as an industry, we've been quite comfortable with orders of magnitude differences between different programming languages. If I want something to be quite performant, I'm probably going to pick up a low-level language like C or Rust or something like that. Whereas if I'm not so bothered, then I might be using JavaScript or TypeScript or Python or something like that. Well, once again, we are confronted with this balance between engineering productivity and system productivity.

Nick: Yes.

Chris: And I think...

Nick: That's really nicely said.

Chris: ...a lot of people are going to choose, I want to get this into the market, or at least I want to test my market fit with something. And so I'm going to take engineering productivity every time. And system productivity is something we can worry about later if it succeeds in the marketplace.

Nick: Yes.

Chris: And that's tech debt as a service.

Nick: [00:12:00] That is, it's an old trope, but there's nothing as permanent as a temporary fix, right? And once you've got it working and you've got that fit, the temptation to never look at it again because it fits is... you want to get on to other things that are more important. So yeah, it just sits there and festers and moulds and compounds as time goes by.

Chris: [00:12:30] But also, I wonder to what extent you can take the prompts that got you there and say, do it again, but do it better. And to what extent you can also have an expectation that these things will have improved? Maybe in the time it takes you to establish that something's got product-market fit, you can do a V2 of the product almost with the same prompts, but with a better underlying mechanism for implementation.

Nick: [00:13:00] Our developer, Dmitri, is talking about this quite often, and he is iterating much, much more quickly and making really substantial changes to a whole bunch of different things that he does. That's about all I can say is I'm recognizing the pattern. But I haven't dived deep enough to say anything about it.

Chris: [00:13:30] I think it's worth as well touching on the impact this is having on open source. There was a project last week where the maintainer had essentially retired, and the project was still healthy and well maintained, but the new maintainers had decided to do what they considered to be a clean cloth reimplementation using LLM-based coding assistance. They had not fed in the original code themselves. They had simply said, here's the test suite, create new code that passes the tests. And when they ran it through tools that are essentially there to look at software plagiarism, it was coming in at a tiny percentage. So it was passing the squint test.

Nick: Right.

Chris: [00:14:00] On being a clean implementation. The reason that they were doing this was so that they could use a more permissive license. So the original developer had chosen a copyleft license, and they wanted to relicense it with a more permissive license. Now, of course, the thing lurking in the background here is almost certainly the LLM that they were using had been trained right with the source code for the original working implementation. So although they'd not fed that in themselves...

Nick: It was there.

Chris: [00:14:30] Was probably there. Yeah. Lurking in the weights in the background. And since that, there are now organizations starting to pop up and say to enterprises, hey, if you're bothered about the licensing of some of this open source that you might use, then we'll create for you a relicensed re-implementation of it. This potentially undermines the whole pretext of how people have been going about maintaining open source projects. And it comes on the back of open source maintainers now being inundated with slop. Yeah. We've seen curl in recent months has ended its HackerOne bug bounty because throughout 2025, they had lots and lots of sloppy, supposedly security vulnerability issues that were just sapping huge amounts of time to chase down. And almost all of them were phantoms. We're seeing many projects where they're getting contributions of low quality. That's causing even more maintainer burnout than we were already facing. And I think it was precarious already for many open source projects and their maintainers. And now it's just this tidal wave of low quality, sloppy submissions being put in there. How to deal with that? So we're seeing people seriously proposing reputation-type systems.

Nick: Oh, right.

Chris: Yeah. The thing that Stack Overflow had, it becomes gatekeeping. And I think one of the things I've always loved about open source was literally anybody could show up and get into a codebase and start making improvements.

Nick: [00:16:30] Yeah. Curl was always famous for having a significantly large raised eyebrow department to which everything was submitted well before this. But yeah, you're absolutely right. The gatekeeping was around quality. And are you following the mission of this project? It wasn't, where did this come from?

Chris: [00:17:00] Yeah, I've done a documentation PR to curl that was accepted. And I like the way that Daniel proudly announces each additional contributor as they show up. It's roughly a handful a week. And it's great that that project is continuing to attract people in addition to a very dedicated set of core maintainers. That's, I think, one of the best-run projects on the planet. They've set up a lot of infrastructure around that. And I think there's also been a lot of investment from the broader community in ensuring that success. And then when we get further down the xkcd cartoon...

Nick: Yes.

Chris: [00:17:30] Your mileage starts to vary an awful lot more. There's a whole bunch of emerging concerns around how open source survives the slopocene. Yeah. How we're going to be able to proceed with that. Yeah. Something else I'd noted here was a few days back, Amazon had an all hands where...

Nick: Yes.

Chris: [00:18:00] They were essentially saying, hey, we feel we're starting to have some AI-assisted outages. Can we stop doing that by having more senior reviewers ensure the quality of what we're doing? And I made a comment on LinkedIn that I think Amazon uniquely brought this problem upon themselves in that the whole two-pizza team thing, and you build it, you run it, and a hiring process that ensures that they never have any glue people, is all well and good during the glory days of growth, and seems to be having a stressed relationship now that the executives are playing Jenga with the org model. And who's keeping the place together? Well, it now seems that the onus is being put upon those senior engineers to ensure quality and that the constraints have moved. So the constraint is no longer, how can I make code? It's do I have enough reviewer bandwidth?

Nick: [00:19:00] How can I assure that the code that I'm getting is something that we could put in and that it'll work and be as stable as it should be?

Chris: [00:19:30] Am I maintaining my delivery pipeline carefully enough that I'm ensuring that good quality stuff is what's making it into production? Amazon certainly had an engineering culture that could get lots and lots of services out there and supported and billing people and whatever else. They've at least got a lot of that culture and systems, whereas there's plenty of other organizations where there's an ability to create the code and maybe even some artifacts out of that code, but who's taking that to production?

Nick: So I think we're out of time for this. But I think the next episode, we're going to talk a bit more about that. And also the really compressing timeline of how these things are coming out and how people are adapting to it. So, it's been the Tech Debt Burndown podcast. I'm Nick Selby.

Chris: And I'm Chris Swan. Thanks for listening.
