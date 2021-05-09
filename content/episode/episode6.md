+++
Description = "Lots of things get improved by building continuous delivery pipelines and then going back to them and iteratively making improvements. Pipelines themselves can be a place where we accrue tech debt - even at the entry point to those pipelines. So let's look at branching strategies."
Date = 2021-05-08T10:54:31-04:00
PublishDate = 2021-05-08T10:54:31-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "44711673/play.mp3" # the name of the podcast file, after the media prefix.
#Get the podcast file by going to spreaker>Podcasts>Episode>Direct Download Link and copy the numbers before
#/download.mp3. Place these numbers to replace the hashmarks so it is something like 12344567/play.mp3 
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#guests = [] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Episode 6: The Flow"
#subtitle = ""
images = ["img/TDB-Logo.jpg"]
#hosts = [] # The names of your hosts, based on the filename without extension.
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
### What Does Your Pipeline Look Like?  ###

**Recording date: May 1, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### 'People often escape from a role before decisions they have made have a chance to catch up to them.' - Chris ####

Let's talk about pipeline. Lots of things get improved by building continuous delivery pipelines and then going back to them and iteratively making improvements. But Chris thinks that pipelines themselves can be a place where we accrue tech debt, even at the entry point to those pipelines. So, Chris has been looking at branching strategies.

If you look at open source development, people agree that trunk based strategies are the way to go, so we're taking short terms branches or forks off a trunk, but coming back to it quickly. But engineers from an enterprise background have a range of versions across different customers. This quickly runs to vast differences between versions, and lots of tech debt. 

What suffers? Updates like security patches, and the engineers, who have to work across a multitude of branches as opposed to being on a constant edge of the trunk version, is pure tech debt. 

Nick mentioned that this seems to point back to engineer flow - if your engineers can't get into the groove because they've got no institutional memory and they have to constantly figure out where they are in order to fix things, they're actually creating tech debt while thy are addressing old tech debt!

It's interesting to think how we got here, but it's true that, because people move around the industry, people, Chris notes, often leave a role before decisions they have made have a chance to catch up to them. So, decision logging becomes super important. But outside the code itself, the log and commit log that people add are critical pieces of context for the next people. 

All too often, though, they say things like, "Merge to master" or the dreaded, "Fixes".

After that, the readme and changelogs that go with things should tell a story, but there's a more macro scale look at decisions people make: what were the tradeoffs that people had in mind when they made their decisions? This is absolutely critical to know. Because when we make decisions, thinking we can back out of them< we sometimes find ourselves in architectural cul de sacs. 

The conversation turns to [Type 1-Type 2 decisions](https://www.sec.gov/Archives/edgar/data/1018724/000119312516530910/d168744dex991.htm) which Jeff Bezos began to discuss back in 1997. Nick gives as an example of what's intended to be a reversible decision the log pipeline that his teams are working on. Chris Mentioned that pipeline engineering may seem to be less worthy work done, but Chris and Nick both feel that pipeline enabling work is among the most important in an organization.

In carrying on the new tradition of references related to what we're discussing, Chris comes up with two important areas of research: [James Governor](https://redmonk.com/jgovernor/author/jgovernor/)'s work on RedMonk about [Progressive Delivery](https://redmonk.com/jgovernor/2018/08/06/towards-progressive-delivery/), and Netflix's work on [Chaos Engineering](https://netflixtechblog.com/tagged/chaos-engineering).

Nick mentioned also the [SLSA: Supply-chain Levels for Software Artifacts](https://github.com/slsa-framework/slsa) proposal, which is an amazing project available now on GitHub. The SLSA (pronounced 'Salsa") project is "inspired" by how Google does things, and ultimately will have a full set of standards, a catalog of technical controls, and a process for accreditation - but for now it's a diabolically useful set of principles and definitions that are really worth a lot of time. The project says it's maintained by members of [WG Digital Identity Attestation](https://github.com/ossf/wg-digital-identity-attestation), which was formerly the [Digital Identity Attestation Working Group](https://openssf.org/blog/2021/01/27/digital-identity-attestation-roundup/), which seeks to "enable open source maintainers, contributors and end-users to understand and make decisions on the provenance or origin of the code they maintain, produce and use." 

One major point of the project is to be able to know and be certain about the provenance of code at every stage of the pipeline. Nick's colleagues are using SLSA as a great way at a very minimum of agreeing on a taxonomy and lexicon, but also as milestones on their journey. The two agreed that SLSA should be an episode in its own right, hopefully with a guest involved in its management to discuss it (hint, nudge, wink). 

The episode concludes with a pivot to a blog post by Signal's [Moxie Marlinspike](https://signal.org/blog/cellebrite-vulnerabilities/) who took on the mobile device forensics company Cellebrite. Cellebrite had earlier claimed it had "broken" Signal encryption, which was utter balderdash. In the information security community, the document quickly was called the Moxie Manifesto but it should be read as nothing short of a declaration of war against Cellebrite. Cellebrite customers (like law enforcement) are casualties of the war.

Moxie shot back with what may be mistaken for a lighthearted report but which is both ruthless and credible based on his demonstrated exploitation of a Cellebrite box: 

- Cellebrite uses very old software components as it assembles its tools, and has been lax about security patches for years;
- This is very plausible because the threat model faced by a Cellebrite box is one of someone with physical access to the box
- Cellebrite uses unlicensed components, with specific example of Apple Dynamic Link Library files; and
- Moxie claims that "Industry-standard exploit mitigation defenses are missing, and many opportunities for exploitation are present"

Chris and Nick were both very interested by the manifesto and think it will be have a long tail.

