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

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### Tech Debt as a Service (Welcome to the Slopocene) ####

After a long hiatus, the Tech Debt Burndown podcast has returned for its third season. We've got a bunch of episodes (some recorded quite a while ago) in the can, so more to come; along with some fresh stuff, as 2026 has been a wild ride already.

Chris Swan and Nick Selby kick off the season with a discussion of what Chris has called Tech Debt as a Service: how we’ve entered the slopocene, and how we are working with our magical AI coding assistants. 

We start with a discussion of multi-agent coordination frameworks, one of which is called Ralph Wiggum, and what's become termed as 'ralphing' is basically sending the coding assistant into a loop until it has successfully met some success criteria in order to exercise the loop: It's kind of going round and round, and maybe doing lots of pretty dumb stuff, but it keeps trying, right? And you don't let it stop until it's got to where you want to go. You'll probably also define some kind of max loop criteria so you’re not just burning tokens all day long . . .

#### Transcript (automated with some gentle manual review)

Nick: It's the Tech Debt Burndown podcast. I'm Nick Selby.

Chris: And I'm Chris Swan.

Nick: We're here to talk about Ralph Wiggum. And Chris, why don't you kick us off, please?

Chris: So the theme for this episode I thought was going to be essentially how we entered the slopocene and how we can get tech debt as a service from our magical AI coding assistants. I guess one of the things that we kind of opened 2026 with was the arrival of these multi-agent coordination frameworks, one of which is called Ralph Wiggum. Yeah, I kind of prepared some notes ahead of [00:00:30] this. And Nick's like, what are you, Ralph Wiggum? Why are you talking about Ralph Wiggum? Isn't that just like the kid off of The Simpsons? And it's like, yes, that's that was worse.

Nick: I was even, wasn't it? The chief of police off The Simpsons? And then you had to remind me of the boy.

Chris: And so what they're doing here with with what's become termed as ralphing, is basically sending the coding assistant into a loop until it has successfully met some success criteria in order to, to exercise [00:01:00] the loop. It's kind of going round and round and maybe doing lots of pretty dumb stuff, but it keeps trying, right? And you don't let it stop until it's got to where you want to go. You'll probably also define some kind of max loop criteria. So it's not infinitely doing dumb stuff and chewing through tokens and running up a bill. But yeah, that's, that's what people are doing now.

Nick: Of course, my definition of ralphing is, is shouting groceries or, you know, vomiting. [00:01:30] So when you just said that, I guess I guess it all makes sense.

Chris: I was looking up ralphing on the way in the likes of Urban Dictionary definition is vomiting stuff up. And so yeah, I kind of feel like we're getting our AI agents to, to vomit stuff up until we're satisfied with the vomit. Um, and it's passing tests that it's written for itself according to its interpretation of a prompt. And [00:02:00] it's not just Ralph Wiggum. Kind of at the same time as that was hitting the scenes. There was another similar framework called Gastown came along from Steve Yegge. And so I think Steve's quite a famed developer and has done some amazing blog posts that have captured people's attention over the years. More recently, I've seen Steve working a lot with Gene Kim, and they've written their book together about vibe coding. If we [00:02:30] look at what's become of Gene's DevOps event, it's now kind of more focused on enterprise, but very much more focused on AI and an AI adoption and how things like vibe coding and the use of these multi-agent frameworks is starting to take effect.

Nick: So that's actually a good thing. We were talking about the book that we're writing, and we were just talking yesterday about the lead time. So now you take a look at Gene's book and, and even some of the stuff earlier in the season that we were, we were just discussing. So [00:03:00] has Gene's book already been overtaken by events?

Chris: I think so, yeah. Um, you know, Gastown went from zero to huge in the space of days. Yeah. At the start of the year. And I should also tip a hat to, to Ruv Cohen because if I look at people kind of using these multi-agent frameworks, as far as I could tell, it really began with Ruv and, and his work on this stuff. And then other people have kind of created [00:03:30] similar frameworks to enable that. And lots more people are now kind of picking those things up and running along with them. I also feel like there's something of a sort of fruit machine mentality going on here. So so we talk about tokens and you know, here we are recording this actually at Brighton Seaside. And so we could step out and find an amusement arcade not very far away. And we could probably buy a bunch of tokens and feed them into slot machines and pull the handle and [00:04:00] see, you know, whether we win.

Nick: Right.

Chris: And I've got a sense right now that a lot of the LinkedIn posts about this are coming from people who've stuffed their tokens in the machine, and they've pulled the handle and it's come up, bar bar bar, and it's paid out the jackpot of, you know, they got something useful. And the people not writing LinkedIn posts about this, like people who put their tokens in the machine and they've pulled the handle and it's come up kind of, you know, cherry melon bell. Yeah. Let's go again.

Nick: Yes. [00:04:30] I think that the great unwashed is basically a bunch of older parliament smoking women sitting in the, in the back of the casino, just with the with the giant bucket of tokens and just continuing to put them in to wait if see, if you win. And it's always a big surprise.

Chris: The most insane thing I think, is if you kind of look at the, the economics behind this, and I think he's been doing an excellent job in recent months of exploring this, they're selling the tokens to us at pennies on the dollar, the data centers and everything that's happening [00:05:00] behind these tokens are all being carried by SoftBank and other deep pocketed investors right now. Or Nvidia is feeding money into the system so that people will buy its GPUs.

Nick: Right. And, and get hooked like, like any good dealer does. Yes.
Chris: And so I kind of feel like we might be in a, in an Uber moment in that period where all of the Uber rides were subsidized.

Nick: Yes, yes.

Chris: Yeah. We're then waiting for how useful is all of this going to be when, [00:05:30] when we're actually having to pay full freight for the tokens?

Nick: I would like to just zoom back now. Right. Let's give the higher level introduction to what it is that we're actually talking about and introduce the the concept of tech debt as a service. And it's really compelling to, to just want to create it because you can do so much and feel so creative so quickly that before you know it, you're, you're left with a giant pile of tech debt.

Chris: One of the, the factors that's really captured my attention here is the notion that we should no longer be looking at the code. [00:06:00] You come up with your plan. You dispatch your multi-agent coordination framework to to implement the plan. It's doing test driven development. So it's creating a whole bunch of tests that are going to persuade you that the plan has been implemented correctly.

Nick: Some of the best comments ever, by the way. Done. It's good.

Chris: And then we get software out of the end of this process, but no human being is actually going [00:06:30] line by line through that software and seeing that they're comfortable with that. We're taking our comfort from the test running. And I think in some ways, this is kind of what we do all the time with continuous delivery. And progressive delivery is we're feeding change into a pipeline, and we're taking confidence and safety from our tests. And then new stuff is emerging from from the pipeline. And, you know, we're doing our canary deployments or our or feature flags or [00:07:00] whatever else to ensure that it's behaving as we want it to. But this feels like much more wholesale change. We're cutting new things from clean cloth and stuffing them through the pipeline for the first time and expecting them to emerge into the world fully formed and and ready to go, rather than, I think, continuous delivery and progressive delivery, even more so. We're all about tiny incremental changes where we're moving forward a tiny bit at a time, but we're [00:07:30] always making forward progress.

Nick: Yeah. And it's funny, that has actually become a cultural thing. I did a, I did a podcast with a bunch of folks for Bishop Fox a couple of weeks ago. And, you know, the question was, does this all save time? The consensus was not really, but developers are spending more of their time thinking about what they want to do and deliberately writing out the prompts so that when it gets generated. Right. So now the code just happens in seconds. But you're right, there's a there's a missing piece there at the end where you take [00:08:00] a look at it and see did it actually work, or is it just passing the test that it wrote for itself?

Chris: I think there's an aspect of this. Not looking at the code, which I'm kind of willing to accept as the introduction of a new abstraction layer. One of the comments I saw from.

Nick: A nice comment that's really.

Chris: Good from an from one of the industry elders, was how much of us look at the bytecode that emerges from a compiler, or the machine code that emerges from a compiler. And the answer is almost [00:08:30] right.

Nick: I know one person in my entire life who would do that because he thinks it's neat.

Chris: I think this this occasions when you're having to focus on very specific performance optimization that you might actually be diving into. What has the compiler done with my source code and how is it emerging and how is it actually interacting with the instruction set architecture of the machine? I'm going to run it on most of the time. Most people are not looking at compiler output. And so if we kind of say that [00:09:00] we've moved up an abstraction layer, we're no longer dealing with programming languages, we're just dealing with prompts. Then the coding output of the prompt becomes a like the output of the compiler. Now there is a very sort of strict differentiation here, which is compilers are deterministic. Yes. They're going to give us the same output.

Nick: Yeah. You run it 15 or 15,000 times.

Chris: Every time, whereas large language models are non-deterministic. [00:09:30] We can't expect that repeatability that I think we're used to with compilers. And I think I'm going to dive down a little rabbit hole as well here, because one of the things that's happened in in recent weeks was Claude actually was prompted to create a compiler. So this was a project that was done at anthropic, and they got to a compiler that was able to compile the Linux kernel.

Nick: Okay.

Chris: And this was something that they completed in about two weeks, and they spent about [00:10:00] $20,000 of tokens on it. So not enormously expensive. It was all enabled by the fact that, you know, compilers have got great test suites. And, you know, can we know the things going through? Compilers have test suites. And so we can see when something is converging on on being correct. The destination I'm trying to get to here is they made a functioning compiler, but it's terrible. And so [00:10:30] all of that effort that's gone into, you know, GCC and LLVM, etc. over the years to create a high quality, performant, correct compiler was not there in the product. And so when people were performance benchmarking the code coming out of at the end of this thing, it was in some cases hundreds of times slower than the equivalent code. And, and I think this is well, kind of relates [00:11:00] back to this notion of dealing with abstraction layers. So as an industry, we've been quite comfortable with orders of magnitude differences between different programming languages. If I want something to be quite performant, I'm probably going to pick up a low level language like C or rust or something like that. Whereas if I'm not so bothered, then I might be using JavaScript or TypeScript or Python or something like that. Well, once again, kind of confronted [00:11:30] with this balance between engineering productivity and system productivity.

Nick: Yes.

Chris: And I think.

Nick: That's really nicely said.

Chris: A lot of people are going to choose, I want to get this into the market, or at least I want to test my market fit with something. And so I'm going to take engineering productivity every time. And system productivity is something we can worry about later if it succeeds in the marketplace.

Nick: Yes.

Chris: And that's tech debt as a service.

Nick: That is, you know, it's an old trope, but there's [00:12:00] nothing as permanent as a temporary fix, right? And once you've got it working and you've got that fit, the temptation to never look at it again because it fits is, you know, you want to get on to other, other things that are more important. So yeah, it just sits there and festers and moulds and compounds as as time goes by.

Chris: But also, I wonder, you know, to what extent you can take the prompts that got you there and say, do it again, but do it better. And to what extent you can also have an [00:12:30] expectation that these things will have improved, maybe in the time it takes you to establish that something's got product market fit, you can do a V2 of the product almost with the same prompts, but with a better underlying mechanism for implementation.

Nick: Our developer, Dmitri, is talking about this quite often, and he is iterating much, much more quickly and making really substantial changes to a whole bunch of different things that he does. That's about all I can say is I'm [00:13:00] recognizing the pattern. But I haven't dived deep enough to actually say anything about it.

Chris: I think it's worth as well. Touching on impact. This is having on on open source. There was a project last week where the maintainer had essentially retired, and the project was still healthy and well maintained, but the new maintainers had decided to do what they considered to be a clean cloth reimplementation using LLM [00:13:30] based coding assistance. They had not kind of fed in the original code themselves. They had simply said, here's the test suite, create new code that passes the tests. And when they ran it through tools that are essentially there to, to look at software plagiarism, it was coming in at a tiny percentage. So it was kind of passing the squint test.

Nick: Right.

Chris: On. On being a [00:14:00] clean implementation. The reason that they were doing this was so that they could use a more permissive license. So the original developer had chosen a copyleft license, and they wanted to relicense it with with a more permissive license. Now, of course, the thing lurking in the background here is almost certainly the LLM that they were using had been trained right with the source code for the original working implementation. So although they'd not fed that in themselves.

Nick: It was there.

Chris: Was [00:14:30] probably there. Yeah. Kind of lurking in the weights in the background. And since that, there's actually now, uh, organizations starting to pop up and say to enterprises, hey, if you're bothered about the licensing of some of this open source that you might use, then we'll create for you a relicensed re-implementation of it. This potentially undermines [00:15:00] the whole sort of pretext of how people have been going about maintaining open source projects. And it kind of comes on the back of open source maintainers are now inundated with slop. Yeah. We've seen curl in recent months has ended its hacker one bug bounty because throughout 2025, they had lots and lots of, of sloppy, supposedly security vulnerability issues [00:15:30] that were just sapping huge amounts of time to chase down. And almost all of them were were phantoms. We're seeing many projects where they're getting contributions of low quality. That's causing even more maintainer burnout than we were already facing. And I think it was precarious already for for many open source projects and their maintainers. And now it's just this kind of tidal wave of low quality, sloppy, [00:16:00] uh, submissions are being put in there. How to deal with that? So we're seeing people seriously proposing, you know, reputation type of systems.

Nick: Oh, right.

Chris: Yeah. The kind of thing that Stack Overflow had, it becomes gatekeeping. And, you know, I think one of the things I've always loved about open source was literally anybody could show up and, and get into a code base and, you know, start, start making improvements.

Nick: Yeah. Curl was always famous [00:16:30] for having a significantly large raised eyebrow department to which everything was submitted well before this. But yeah, you're absolutely right. Like the gatekeeping was around quality. And are you following the mission of this project? Not it wasn't it wasn't like, where did this come from?

Chris: Yeah, I've done a, you know, documentation, PR to curl that was accepted. And I like the way that Daniel kind of proudly announces each additional contributor as they show up. It's roughly a handful a week. [00:17:00] And, you know, it's great that that project is continuing to attract people in addition to a very dedicated set of core maintainers. That's, I think, one of the best run projects on the planet. They've set up a lot of infrastructure around that. And I think there's also been a lot of investment from the broader community in ensuring that success. And then when we kind of, you know, get further down the xkcd cartoon.

Nick: Yes.

Chris: Your mileage [00:17:30] starts to to vary an awful lot more. There's a, there's a whole bunch of emerging concerns around how open source survives the slopocene. Yeah. How we're going to be able to proceed with that. Yeah. Something else I'd kind of noted here was a few days back, Amazon had an all hands where.

Nick: Yes.

Chris: They were essentially, hey, we feel like we're starting to have some AI assisted outages. Um, [00:18:00] can can we stop doing that by having more senior reviewers ensure the quality of what we're doing? And I made a comment on LinkedIn that I think Amazon uniquely brought this problem upon themselves in that the whole two pizza team thing, and you build it, you run it, and a hiring process that ensures that they never have any glue people, right? Is all well and good during the glory days of growth, and seems to be having a stressed relationship [00:18:30] now that the executives are playing Jenga with the org model and you know who's keeping the the place together, well, it now seems that the onus is being put upon those senior engineers to ensure quality and that the constraints have moved. So the constraint is no longer, how can I make code? It's do I have enough reviewer bandwidth?

Nick: How can I assure that the code that I'm getting is something that we could put in and, and that [00:19:00] it'll that it'll work and be as stable as it should be?

Chris: Am I maintaining my delivery pipeline carefully enough that I'm ensuring that good quality stuff is what's making it into production? Amazon certainly had an engineering culture that could get lots and lots and lots of services out there and supported and billing people and whatever else. They've at least got a lot of that kind of culture and systems, whereas there's plenty of other organizations [00:19:30] where, you know, there's an ability to create the code and maybe even some artifacts out of that code, but who's taking that to production?

Nick: So I think we're out of time for this. But I think the next episode, we're going to talk a bit more about that. And also the, the kind of really compressing timeline of, of how these things are coming out and how people are adapting to it. So, you know, it's been the tech Debt Burndown podcast. I'm Nick Selby.

Chris: And I'm Chris Swan. Thanks for listening.
