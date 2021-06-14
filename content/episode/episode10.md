+++
Description = "Eoin Woods has developed quite a bit of software, and created and dealt with quite a lot of technical debt. He is CTO at Endava, and co-author of two software architecture books. On the Tech Debt Burndown he joins Chris and Nick to talk about his role in the International Conference on Technical Debt and some of the research highlighted in the virtual 2021 edition of that conference, as well as his own personal experiences in the field."
Date = 2021-06-12T07:05:59-04:00
PublishDate = 2021-06-12T07:05:59-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "45275081/play.mp3" # the name of the podcast file, after the media prefix.
#Get the podcast file by going to spreaker>Podcasts>Episode>Direct Download Link and copy the numbers before
#/download.mp3. Place these numbers to replace the hashmarks so it is something like 12344567/play.mp3 
podcast_duration = "25:58"
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
guests = ["eoin"] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 1 E10: Eoin Woods"
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
**Recording date: May 25, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### "There's sometimes an assumption that people in the business of building systems all the time implicitly understand tech debt. I think they definitely don't." - Eoin Woods ####

After intros we ask Eoin about the International Conference on Technical Debt, which recently had its [4th annual event](https://2021.techdebtconf.org/). Eoin was a keynote speaker at the [first conference](https://2018.techdebtconf.org/), and has stayed involved since.

Eoin goes on to explain that the academic community have found ways to collect data on tech debt that have evaded many practitioners, which has brought fresh insights onto the problems and how they might be addressed.

Nick asks about the [Preventing Technical Debt by Technical Debt Aware Project Management](https://2021.techdebtconf.org/details/techdebt-2021-technical-papers/9/Preventing-Technical-Debt-by-Technical-Debt-Aware-Project-Management-Evaluation-of-) paper from Hamburg and whether "can it be this easy?"; and Eoin replies that in the [SEI book on Managing Technical Debt](https://resources.sei.cmu.edu/library/asset-view.cfm?assetid=546594), "it's one of the key practices".

After a spot of collective JIRA bashing, Nick asks Eoin about the [Security Debt: Characteristics, Product Life-Cycle Integrations and Items](https://2021.techdebtconf.org/details/techdebt-2021-technical-papers/7/Security-Debt-Characteristics-Product-Life-Cycle-Integrations-and-Items) paper, describing it as "fully buzzword compliant, talking about shift left and everything like that". Eoin observes that security related tech debt gets special treatment, "it's rather more urgent to fix, because you may not understand all the possible implications of it". He goes on to say that security has become more popular as a topic at conferences over the last 10 years or so.

Chris asks Eoin for one of his favourite examples of tech debt from the past, which leads to a description of an old Unix transaction processing monitor, and a giant C/C++ code base that grew around it. He talks about a colleague making good progress, but the sense that they weren't actually winning.

Eoin then talks a little about lessons from his book [Continuous Architecture in Practice](https://pgppgp.wordpress.com/), and goes on to describe how people often get stuck on a data model that's not quite working.

Chris then asks Eoin about practices he's currently using to handle tech debt, which leads to "It very much depends on the environment, I think the key thing that we try and encourage everyone to do is to make sure that you're running enough analysis on your code regularly, that you can spot trends and changes."

We conclude with a promise to link to Eoin's book on [Software Systems Architecture](https://www.viewpoints-and-perspectives.info/) that he co-authored with Nick Rozanski, so there it is.