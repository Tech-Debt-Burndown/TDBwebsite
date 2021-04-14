+++
Description = ""
Date = 2021-04-11T10:52:27-04:00
PublishDate = 2021-04-11T13:52:27-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "44292452/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#guests = [] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Episode 1: What Is Tech Debt?"
#subtitle = ""
images = ["https://techdebtburndown.com/img/TDB-Logo.jpg"]
#hosts = [] # The names of your hosts, based on the filename without extension.
#aliases = ["/##"]
#youtube = ""
#explicit = "yes" # values are "yes" or "no"
#media_override = "episode/44292452"
#truncate = ""
#upcoming = true # set to true if you want this to be listed as upcoming, etc, etc
#categories = []
#series = []
#tags = []
+++

#### What is technical debt? Nick and Chris offer their definitions, despite agreeing there is no right answer. #### 

**Recording date: December 6, 2020**

Nick thinks it is the stuff we put off in favor of things we want to do, while Chris quotes [Ward Cunningham](https://en.wikipedia.org/wiki/Ward_Cunningham) and [Martin Fowler](https://martinfowler.com), summarizing that technical debt is  basically the quick and dirty fixes that incur interest payments, and using the concepts of tech debt to describe problems faced over time. 

A chat about "shift left" or moving earlier in the SDLC, which boils down to the human factors of tech debt accrual. 

Nick mentions a collection of moments in which decisions are made to do the scalable thing or do the fun thing. Chris points out these concepts apply to both [Waterfall](https://en.wikipedia.org/wiki/Waterfall_model "The waterfall model is a breakdown of project activities into linear sequential phases, where each phase depends on the deliverables of the previous one and corresponds to a specialisation of tasks- Wikipedia") and [Agile](https://en.wikipedia.org/wiki/Agile_software_development "Agile practices involve discovering requirements and developing solutions through the collaborative effort of self-organizing and cross-functional teams and their customers/end users - Wikipedia") approaches, and invokes [Paul Downey](https://twitter.com/psd) in his discussion of when decisions get made and how they are addressed.

When should it be addressed? Why do organizations schedule huge tech debt burndowns as opposed to building in TDB to every sprint, and Nick quotes [Phil Venables](https://www.philvenables.com/about) who tweeted that we should measure tech debt in the terms of what percentage of dev time is spent on this. 

Which leads Chris to ask about what metrics are right. How do you calibrate information about doing it quick versus doing it right? 

#### How hard are these problems? #### 

From engineering time to executive buy in, these are critical issues. We can't tell you the monetary value of not scaling a thing, and that is a huge issue. 

- Audits are asking about technical debt and related issues. The questions are getting harder. 

Chris mentions that one if the issues that arises is what kinds of tech debt do we face? One of the ones he likes to focus on is policy debt, which is a fundamental type organizations face. 

This raises the issue of *policy over time*: in FinServ, most policies were written in the days of the moat and the gate, and they don't address contemporary, cloud native architectures. 

This brings in some of the human decisions we make. 

How do we answer questions about the interplay between policy and regulation, like the "should we reset our passwords every 90 days" question. 

Chris summarizes the three different global approaches to regulation. 

- Singaporean: very prescriptive. 

- Anglo-American: Principle based, broad brush of expectations and relying on audit companies

- Swiss: More comparative: an expectation of participants in the marketplace to reach a certain standards.

Nick describes how US auditors are asking more about technical debt management, but they're not getting highly specific enough to differentiate betwen tech debt and the underlying policy debt which might drive it.

When we told auditors that our main goals in security was to get rid of tech debt and the auditor asked whether I meant 'security tech debt' or just plain old 'tech debt' - what's the difference?

Chris then discusses the [CIA triad](https://en.wikipedia.org/wiki/Information_security "Information security's primary focus is the balanced protection of the confidentiality, integrity, and availability of data (also known as the CIA triad) while maintaining a focus on efficient policy implementation, all without hampering organization productivity. - Wikipedia") and talks about how we in Information Security seem to have abdicated the 'Availability' part, then referred to a 2006 report called [Milk or Wine: Does Software Security Improve With Age](https://www.usenix.org/conference/15th-usenix-security-symposium/milk-or-wine-does-software-security-improve-age) which is very pertinent. 

The discussion moves to tests: is there a vulnerability in the code, but the bigger aspects of debt include such paralysis that they can't change anything, because they don't have the test coverage to know whether a fix here will affect something unintended there? 

*So test coverage and testability must be part of a strategy to address tech debt.* 

We in the industry are constantly talking "secure by design," "shift left," and the like, but what does this mean in practicality? So, if we are starting a software project today, what are we going to do differently now from last year?

Nick describes his firm's Squad Security Liaison program, which is designed to foster inter-disciplinary teamwork by making introductions between engineers and security people on a regular basis, to encourage interaction and collaboration. It means they know one another before problems exist, so relationships are there when something goes wrong. 


This podcast is all about learning! 