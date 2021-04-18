+++
Description = "We've been hearing about Supply Chain vulnerabilities quite a bit lately, from Solar Winds to CodeCov. How do these relate to technical debt? Ah, that's a complicated questions, because each of its components are discussing complex things. In this episode, Chris and Nick try to hash it out and sort through what's important."
Date = 2021-04-18T00:00:00-05:00
PublishDate = 2021-04-18T00:01:00-00:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "44372957/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#guests = [] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Supply Chain Vulnerability & Tech Debt"
#subtitle = ""
images = ["img/episode/default-social.jpg"]
hosts = ["cswan", "nselby"] # The names of your hosts, based on the filename without extension.
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

### Where do you start looking for tech debt? ###

**Recording date: April 17, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

This is a common question, and Chris and Nick discovered that they do it differently. 

Chris describes how he views tech debt from the perspective of his continuous integration and continuous delivery pipeline: “How quickly can I release, and what’s getting in my way?” He discussed that recently, [Charity Majors](https://twitter.com/mipsytipsy) has been discussing the importance of a quick feedback cycle for developers:
{{< tweet 1382619734781272066 >}}

Basically, this comes down to, ‘you’ve got 15 minutes to build’ in order to be good at this, and this brings us to the [Theory of Constraints](https://en.wikipedia.org/wiki/Theory_of_constraints "The theory of constraints (TOC) is a management paradigm that views any manageable system as being limited in achieving more of its goals by a very small number of constraints. - Wikipedia") thing: what things are blocking me from getting to that 15-minute build time, and how do I get rid of them? 

Nick says he comes at this from a more traditional infosec approach, basically, how do I get in, how do I move around? Chris points out that this reveals two prevalent schools of thought in the industry when it comes to building software: “How do I make this work?” and, “How do I break this?”

How do we make it work leads to “How do I make this resilient”

Both of these approaches seem to meet up at resilience, which brings us to the broader conversion about software dependencies and dependencies management, which itself is based on the fact that today,

#### "software is mostly assembled as opposed to being constructed fresh from a clean sheet of paper." --Chris ####


As we go about that process, we need to get open source, and buy tools, and many are pretty janky - and the janky tool is the one that gets you. 

Chris thinks there is better tooling coming, and Nick is far more skeptical of that. 

This gets into the fact that libraries get poorly maintained or abandoned and can in fact be taken over by malevolent actors, and now a trusted source is pushing malware.  

Everyone understands that but to what extent do you have proper insight to what you’re assembling? 

Supply chain breaches are top of the pops. But what are supply chain breaches? 

#### What’s going on? ####

Supply chain attacks happen when people get into these dependencies, which are then incorporated, or they get into the build chain to insert software that shouldn’t be there. 

They can also be broader than just development operations, attacking necessary business tools that the company uses as a whole. 

Probably the earliest great example of this that we remember is the [RSA SecureID breach of 2011](https://www.wired.com/2011/08/how-rsa-got-hacked/). Chris remembers that the term Advanced Persistent Threat was particularly bogus, because it isn't the threat, it's the attacker that is sophisticated and advanced (Nick throws in a plug for an article he and [Scott Crawford](https://451research.com/analyst-team/analyst/Scott+Crawford) wrote in January, 2010 called, '[It's The Adversaries That Are Advanced and Persistent](https://threatpost.com/its-iadversariesi-who-are-advanced-and-persistent-012610/73426/)')

But there’s been a change in dynamics in the past few years - where it felt like the entire SecureID breach targeted Lockheed Martin, now it feels like “stage the attack first and then choose your targets" rather than choose your target and then stage your attack.

If we are a contemporary software company or even a business, and we’ve done the right thing by outsourcing the stuff that isn’t our core competency, we find that there’s lots of stuff that isn’t everyone’s core competency - email servers, ticketing systems, remote helpdesk. 

So even though we all use a much more diverse set of universal tools, each tool in its category is just as much a single point-of-failure as was SecureID - we all use the same instant messenger, the same ticketing system, the same what-have-you, so targeting can be conducted on an industry vertical-level by attacking a tool that horizontally attacks the whole industry. 

How do we protect ourselves against these third party risks?

Spreadsheets. 

Chris talks about the Hyperscalers like cloud and the starting point of the [Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/) in which security and compliance are the shared responsibility between the hyperscaler and the customer.

We’re now at a point where we rely on the Hyperscalers like AWS for security. 

Nick points out, though, that AWS has a different idea about what “secure” means from its customers - them being secure is just not the same as us being secure, and Chris rightly points out that this is the other side of the shares security model. But the point of handover is sometimes unclear to the customer. 

Many things that should be done are best practices are not enabled by Amazon by default, and this is a huge issue, which Chris points out is completely right and behind the idea that we read the dunderheaded thing of the week every week in [Corey Quinn](https://twitter.com/QuinnyPig)’s [Last Week In AWS](https://www.lastweekinaws.com/) newsletter.

But if you want the audit trail, you need to flip the bit that starts the taxi meter to fill your other S3 bucket with logs. 

#### Adversaries Have OKR’s, Too ####

In looking at attacks, it’s important to realize that attackers will always seek the path of least resistance as they target you - and often these days the path of least resistance is the tool. Chris mentions another Economics of Information Security Paper, [Where Do All The Attacks Go?](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/WhereDoAllTheAttacksGo.pdf  "Where Do All The Attacks Go, by Dinei Florencio and Cormac Herley, Microsoft Research: If security is so awful, why isn't everyone attacked every day? Economics.") in which the question is asked, 'If security is so awful, why isn't everyone attacked every day?' and the answer of course is that even attacker groups have bosses to please and budgets to live up to. Targeting is hard. 

#### Threat Model Your Supply Chain Tools ####

So the idea to use supply chain attacks being in the news is to use them to justify the time it takes to consider something: given a supply chain attack against our CI/CD tool, what permissions would it have, and how can you follow those permissions throughout your CI/CD pipeline.

All too often we bring in these external tools to cover up what we're not good at, which would be fine if they were better than they actually are. Threat modeling through a theoretical supply chain breach can help you identify new forms of tech debt. 




