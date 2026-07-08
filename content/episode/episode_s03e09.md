+++
Description = "Chris and Nick on Testing and Policy Debt"
Date = 2024-10-04T13:00:00Z
PublishDate = 2026-07-08T12:00:00Z # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "72050209/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 3 E9: Testing and Policy Debt"
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
**Recording date: 4 Oct 2024**

*Download at [Apple Podcasts](https://podcasts.apple.com/podcast/the-tech-debt-burndown-podcast/id1562710899), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### Testing and Policy Debt

Chris and Nick talk about how organizational growth introduces process inefficiencies and inter-departmental friction, which can be diagnosed and addressed using value stream mapping. They emphasize that automating systems successfully relies on robust exception handling rather than just building for the "happy path," sharing a banking case study where classifying and systematically resolving exception classes (via a system dubbed "X-Man") drastically improved efficiency. This macro-systems view is compared to code testing, where they advocate for a structured test hierarchy. They highlight the high cost of slow end-to-end tests and stress the importance of maintaining a fast, ten-minute feedback loop dominated by cheap, local unit and functional tests to prevent developer context from being lost.

They also preview the concept of "policy debt," illustrating it through recent updates to NIST's password guidelines. They discuss how legacy organizations often remain trapped under outdated and cumbersome rules—such as mandatory 90-day password rotation, because they lack the institutional memory or documentation to explain why these policies were created in the first place. Nick shares a past success using modern guidelines to negotiate policy changes with a regulator, contrasting it with larger, older organizations that struggle to unpick legacy commitments. The episode concludes with a historical anecdote about Chester Carlson’s invention of the Xerox machine and the creation of "key operators" to manage paper and toner, highlighting that scaling friction and operational adaptations are universal challenges for any growing technology.

#### Show notes (links)

[Value Stream Mapping](https://en.wikipedia.org/wiki/Value-stream_mapping)

Steven Sinofsky: [Automating Processes with Software is HARD](https://hardcoresoftware.learningbyshipping.com/p/222-automating-processes-with-software)

[Dealing with Policy Debt](https://blog.thestateofme.com/2025/06/06/dealing-with-policy-debt/) blog post by Chris


#### Transcript (automated)

Nick Selby: This is the Tech Debt Burndown podcast. I'm Nick Selby, and we've been having one of these existential conversations before we started recording around how you ship, what you ship, and what that process looks like.

Chris Swan: [00:00:30] And I'm Chris Swan, and that was brought on by a discussion of how organizations start out feeling like they can ship stuff really fast and then a few years later, come to a position where it feels like they can't ship anything?

Nick Selby: Yes. And not only can they not ship anything, but they don't know why. And they don't know who they should be pointing at, and so they end up pointing at each other.

Chris Swan: [00:01:00] Yeah. And I think that can often come from the growth of the organization and the growth of fiefdoms within the organization. So it's very easy at the start where it's just the sales and technical co-founders, and one of them's got a great idea and can go out and take it to market and the other knows how to make it happen. And of course, they then hire people. And in the early days, the people they've hired are kind of Swiss army knives tackling every kind of problem and just getting things done. And then at some point, you find yourself with departments and an HR organization and wondering where it all went wrong.

Nick Selby: [00:02:00] And at some point, there's this sort of realization that you've moved into the part where you're a big small company, and then at some point you become a small, big company. If you're doing things right, at each of those transition points, there's probably going to be some serious dysfunction introduced to the things that used to work, that no longer work because the scale at which you're doing things is no longer what it was. And unless you've been really careful the whole time, the processes you have in place were the ones to support what you were doing and not necessarily future proofed.

Chris Swan: [00:03:00] Quite. And I think these are actually solved problems. So we can look at organizations—and I don't these days wish to be an Amazon booster, I sold my stock—but the whole two pizza team thing and 'it's always day one' has survived there to incredible scope. And if I think there's anything that causes woes in an organization of that age and that size, and I could look across at some others here, it's an inability to organically grow leaders, which results in hiring people at a senior level from outside, which results in pollution of the culture. Absolutely. You import somebody else's broken culture rather than preserving your own notionally good culture.

Nick Selby: Or sometimes worse, you get somebody from a culture that you aspired to and they come in and it just doesn't mesh with the one that you actually have.

Chris Swan: [00:04:00] And these things can look different from afar. So I think we often form opinions about organizations from their brand and our experience of the product. And what you don't see is how the sausage is being made, and that could indeed be a very ugly process that you wouldn't want to involve yourself in. If you're choosing an executive based on the brand without looking too carefully at what they were actually doing and what they are going to end up actually doing in your organization, I think that's what can lead to friction and ruined expectations. But bringing it back to this question of tech debt, I think it's very easy for departments to start blaming each other. So if we listen to Gene Kim and a lot of the people he talks to, very often when they're getting into value stream mapping exercises, it's been preceded by a lot of inter-departmental finger pointing of 'it's their fault.' 'We would be just great if it wasn't for those bozos getting in our way all of the time.' And what they almost always find when they do the value stream map is it's often not that simple, but quite often there is actually a relatively straightforward proximate cause of why both parts of the organization are unable to mesh with each other. And so that mapping exercise gives them both insight that 'oh, that thing is actually the blocker.' It's not the mainframe, it's not the mainframe people. It's the way that we've decided to work together.

Nick Selby: Yeah.

Chris Swan: Is adapted to what we actually want to do.

Nick Selby: [00:06:30] And it's the first thing you think of. It's not the first thing I think of until I talk to you, and then you think of it too, and I do it. But the value stream mapping exercise feels like it gives me a little bit of tingling in the occipital, because it makes me feel like I did when I was a CISO, where everything I said is nice to have, not must have, but it's a must have. The value stream mapping exercise brings forward all of these kinds of things. And so if you find yourself in this situation where things are just slowing down and becoming more and more cumbersome and things are becoming more contentious, and there's the kind of internecine rivalry that you're talking about and inter-departmental rivalries, that's where you have to start, because it's that indication that there's dysfunction in communication between silos because people aren't seeing the big picture. Everybody's focusing on their own thing. It's so common, and yet so uncommon that people in that situation say, 'Hey, why don't we all sit and talk together and map this out?' which is, of course, what they have to do.

Chris Swan: [00:07:30] I think another piece of this as well is Steve Sinofsky has a newsletter edition out in the last few days about how difficult it is to automate things. If we cast our eyes over time, none of this has ever been easy, but a point he draws out is that good processes, good automation of processes, is defined by good exception handling, not by whether you can go down the happy path.

Nick Selby: [00:08:00] Yes. I think it should go without saying, but I want to say it because it often doesn't, that to get to that place, you actually have to understand the process that's going on to such an extent that you can automate the good parts and not just automate bad manual processes. You need to be able to explain what it is you're doing to such a degree that you can automate it efficiently and make the resulting thing you've automated really good. That's another thing that isn't obvious until you've done it wrong.

Chris Swan: [00:09:00] Yeah, and the best example I can recall of this was one of the banks I was at, and they had growth and needed to scale to cope with that growth. That ultimately involved a platform migration, so they had to get a chunk of stuff off the mainframe and onto this newfangled, at the time, enterprise Java stuff. They built straight-through processing, which was the catchword at the time. Obviously, there was a happy path there where somebody did a trade and everything just flowed through the system, all of the data was correct, all of the reference data matched up, and all of the settlements took place. All good. Initially, of course, a great deal of stuff did not flow through that happy path, and a lot of that actually turned out to be reference data mismatches. But that's okay. They built a system alongside the straight-through process for exception management, and they imaginatively called that thing X-Man. What they managed to do there was not just deal with instances of exceptions, but group exceptions into a class and identify the underlying cause that was causing that class of exception, and then winkle it out and deal with it. And of course, this is just a perfect example of learning and continuous improvement. As time wore on, the exception rate dropped precipitously because the root causes of whole classes of exceptions and the underlying mismatches in reference data or whatever it happened to be had all been fixed. They were then in a situation where the exceptions were really exceptions. It was just onesies and twosies a day of, 'Okay, this is a customer that hasn't done anything for ages, and so one of their trades hasn't been through the system and, turns out, their data needs fixing as well.' But that then becomes a kind of background radiation of the cost of doing business rather than everything being fundamentally broken.

Nick Selby: That.

Chris Swan: [00:11:30] Feels like such a straightforward and easily repeatable pattern, and yet.

Nick Selby: Yeah.

Chris Swan: And yet I feel like we very often get stuck at we built the happy path and we're just not going to deal with everything.

Nick Selby: [00:12:00] It's so amazing that you say this. We're going through something right now where there's this thing that was reliant on a bunch of things coming together, and then end-to-end testing and converting that into unit tests, boundary tests, and contract tests, and replacing the end-to-end tests with all these other things. And there's this state of panic where everybody's like, 'Well, it's not going to work, it's going to be really hard, and how will we know if it will really work?' We'll know it really works when these tests pass. Literally, the conversation that you just had was the conversation that we've been having internally, and they've gone in a very short time from a real fear of the unknown—or much worse, that you're going to break something that currently works and doesn't need to be fixed—to starting to see the possibilities. And by the way, that attitude came from not having the resources to fix a bunch of problems because we have other problems we need to fix. So when you talk about changing something that's working into something that potentially might not work, it gets everybody really itchy. As they gain trust in the different tests, and they start to realize the possibilities that have opened up because of this change in the way they're thinking, it's just a really wonderful thing to watch. As you just said, going from a bunch of things that happen all the time to onesie, because you now understand all the steps.

Chris Swan: [00:13:30] And I think thinking about this in terms of testing for our code is like the micro version of the macro conversation we've just been having about systems, but I think the same arguments apply. Once we get into a discussion of testing, the happy path is the obvious thing, and it's kind of easy to light up that test. But when we're doing proper testing, we're doing all of that coverage for the diversions off the happy path, which can be expected. I don't want to get into a conversation about 100% coverage or nonsense like that, because I think Kent Beck summed this up most perfectly: nobody reads the whole of a newspaper.

Nick Selby: Yeah. It's great.

Chris Swan: [00:14:30] And so trying to get 100% coverage is like trying to read the whole of a newspaper; it's probably pointless. However, having coverage that you're confident in is what matters here, but also getting that feedback quickly enough. I think this is where the test hierarchy is very important to pay attention to. You were just mentioning end-to-end tests, and I feel like often end-to-end tests are the easiest tests to create, but the hardest tests to live with because they're very slow and expensive to run.

Nick Selby: Yes.

Chris Swan: [00:15:00] So if I think about three tiers of testing that I'm using in everyday stuff: unit tests, functional tests, and end-to-end tests. And my metric for this is there's essentially an order of magnitude cost between each. So if I'm doing something with a functional test rather than a unit test, that's costing me ten times as much. And if I'm doing stuff with an end-to-end test rather than a unit test, that's...

Nick Selby: So.

Chris Swan: True. 100 times as...

Nick Selby: Much. So true.

Chris Swan: [00:16:00] And we try very hard in the work I'm doing every day to cleave to a ten-minute test feedback time. I know that Dave Farley talks about this a lot in his work around continuous delivery. And so, as acolytes of continuous delivery or progressive delivery or whatever we're using to denominate this these days, getting that within ten minutes is seriously important because I think if you don't get that feedback quickly enough, the context of what you were doing and why it has caused the tests to fail starts to be paged out and people have moved on to different things. With all of that in mind, we try to get as much as possible into the unit tests because they're quick, they're local, and you can have almost instant feedback. And then functional tests may also be runnable locally against some kind of demo environment and various mocks and stubs. The end-to-end tests are the expensive ones, and that's normally where you've raised the PR and you're asking your colleagues for review, and they too are waiting up to ten minutes for whether this actually looks like it's behaving itself for the parameters we understand to be well-behaved—which includes all of the bad things we've seen go wrong in the past, the so-called regression tests. Getting that feedback quickly enough is essential, but also having confidence that the feedback is meaningful is the most important of all, because you could have that end-to-end test for the happy path and have it light up and still have loads wrong.

Nick Selby: [00:18:00] And that made me think, as you were saying, that this is related to what we started talking about before we started recording: the finger-pointing and the areas where you're waiting for somebody else to do something and you're not quite sure what's going to happen. That is where we've referred to process debt and policy debt. It's back to value stream mapping. An old friend who works at a former employer of mine reached out because he's writing something about tech debt. As I was reading through, everything he's saying treats technical debt as a technical or engineering issue, and there's nothing in here about culture, organization, process, or policy—and that is doomed to failure. I don't know if it's even thirds; I actually think, as you said, this is solved. One of the most commonly uttered things that I end up saying to executives is that we're not creating anything new, we're just doing it properly. We are working on this; this is not bleeding edge, this is just the way modern software gets done. The bigger challenge is getting to the point where you can run it, because we need an executive-level acceptance of the fact that we have to change the way we're doing things and change expectations from what they were—which were unrealistic to begin with, or I wouldn't be here. That's the first thing. And getting to the point where you can solve that internecine warfare, the quibbles about how we do what to allow things to move gracefully through the process—that's actually the much, much harder part than finding the ways to fix it. It's really true: if you want to see instant collaboration, get a bunch of engineers from different departments to speak about engineering solutions to problems they recognize. As long as you can agree on the derivation of the metrics and the provenance of the problem, at that point, even people who don't like each other are actually all having the same conversation. But if you talk to executives who are not technical about the way to get things to move, that's going to take a long time, and you should pack a lunch.

Chris Swan: [00:20:30] So your provenance of the problem thing touches on a sort of flash of insight I had the other day about policy debt, and I think we should do a whole episode on policy debt. Let's just kind of preview it here.

Nick Selby: Cheesy.

Chris Swan: And so, NIST released some new guidance on passwords in the last week or so.

Nick Selby: Oh, that's right. I did see your post on this. I knew I'd heard you talking about policy debt recently. Yeah, I'm very interested in this.

Chris Swan: [00:21:00] And so we've seen this show before because NIST and NCSC and other organizations, back in something like 2018 or whatever, introduced revised guidance on password policies. And nothing happened because every organization has got an existing policy, including rotating your password every 90 days or whatever. And this is the insight: they don't know why they did that. Was it because NIST told them to, and now they've changed their minds? Or because they promised that to somebody else, or somebody else told them to and they still need to do that? Nobody kept the references.

Nick Selby: They do it like that because that's the way they do it. And there's no cultural reference or remembrance or institutional knowledge of why it started, but that is the way we do it.

Chris Swan: [00:22:00] And so from here on forward, it is crucial that we actually reference why, because that allows us to go back and say, 'Can I change this?'

Nick Selby: [00:22:30] Wow. So first of all, let me push back just a little bit, because I think it was in 2017 that they did it. But in 2018, you and I had a conversation, and I was in the process of negotiating something with the New York Department of Financial Services because they were insisting on two really dumb things: the first was that they rotate passwords, and the second was around passphrases, not passwords, to make them a little bit easier to remember. This was sort of before the ubiquity of 1Password and LastPass and things like that. I actually took the ammunition that you and some of your colleagues gave me at the time and wrote a really, really well-reasoned, succinct justification pointing at those updates to the guidelines about only rotating on evidence of compromise. And it worked. We actually were able to change our policies based on that conversation. So you're right. Nobody does that; it's just most people.

Chris Swan: [00:23:30] But that was a relatively youthful organization that didn't have decades or more of history behind this stuff.

Nick Selby: Oh, you're saying it was one thing to convince the regulator, and quite another to change the internal culture around why they do it. Because it was so young—it was only a five-year-old company, and I was the CISO—I could just decree that this happened. Most people don't have that luxury. That's absolutely true.

Chris Swan: [00:24:00] Well, and I think it's a question of unpicking. So if we make the change, does that actually undermine a commitment we've made to some other customer or to some other regulator?

Nick Selby: Yeah.

Chris Swan: Do we actually have freedom to maneuver here, or are we trapped in aspic in what we said we were going to do then?

Nick Selby: [00:24:30] We have to do something about policy debt; we definitely do. Even on the password thing, I remember having arguments with the CEO when I wanted to go to a 16-character minimum. After all the fighting I had around it, I had to make a matrix showing how long it took to crack 12, 13, 14, and 15 characters, and I think I lost. He just said, 'No, you can't do it,' because he didn't want to.

Chris Swan: Well, I think we should leave it there and promise to come back with another episode on policy.

Nick Selby: [00:25:00] I think we should. I just wanted to mention one thing because you reminded me of something as you started talking. Other than your company, of course, it's rare that things aren't jacked up. And often it's kind of nice to notice that everything's on fire all the time everywhere else as well, and all the detritus that's left in the wake of those growth patterns as you go from a startup into a medium company and then a successful company. I've been reading a lot of early company stories and inventors, and it's really amazing how often that is the case. What you said about brand—the brand representing something versus what they're actually doing behind the scenes—there's a wonderful book called Copies in Seconds about Chester Carlson, the guy who invented the Xerox machine, the photocopier. What is absolutely brilliant to me is their biggest problems. I remember this from my early days working in an office: every now and then a light would come on and say, 'Call key operator.' What the hell is a key operator? What had happened was they had done all this planning about how many copies people would make and what the throughput of their machines was supposed to be. I think they were saying that for offices, it was going to be like 50 or 100 copies a week. It had never occurred to them that anybody would ever make a copy of a copy. And suddenly, when people had the opportunity in an office to make copies of copies, people started copying absolutely everything. They were running so many things through it that Xerox couldn't hire enough people to go around and do the maintenance. What they did find was that most of the maintenance they had was basically changing the paper, refilling the toner, and really simple things. So they made it so you had to appoint a key operator if you were a customer—the person on whom everybody can depend to do those basic things—and they put them through a training course. This is such a great testament to how jacked up everything is all the time. Even with technology that, as he pointed out in the book, if you buy a laser printer today and bring it home, is the same technology that was in the Xerox machine 80 years ago.

Chris Swan: [00:27:30] And now I have to ask: did that operator have a key that enabled them to unlock the machine to get in?

Nick Selby: [00:28:00] Oh, you know what? Actually, I think I did work in some places where—especially when they had the really big, fancy ones with multiple collation functions—they did lock up the paper supply, because at point you're putting 12 reams of paper in there. My gosh, that could cost a lot. So there was actually a key. But they just meant that this was the key person in the organization who can make things happen. Anyway, we will come back with an episode on policy. So this has been the Tech Debt Burndown podcast. I'm Nick Selby.

Chris Swan: And I'm Chris Swan.

Nick Selby: So yeah.

Chris Swan: Thanks for listening.
