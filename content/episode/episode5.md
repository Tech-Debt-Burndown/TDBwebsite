+++
Description = "How do you measure technical debt? This week, Chris and Nick discuss the metrics around technical debt, and why there are so few of them."
Date = 2021-05-02T00:00:00-04:00
PublishDate = 2021-05-02T00:00:00-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "44593888/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#guests = [] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 1 E5: The Metrics"
#subtitle = ""
images = ["img/episode/img/TDB-Logo.jpg"]
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
### How Do You Measure Tech Debt? What Are The Metrics That Work? ###

**Recording date: March, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### 'I think it's really less about wasted time, and more about getting into flow state: is your tech debt preventing flow from happening?' - Chris ####

How do you measure technical debt? What are the metrics you use? 

Chris hasn't found the magic formula. Over the past few years Chris has been acutely aware of the quote from [Accelerate](https://www.amazon.com/dp/B07B9F83WM/ref=dp-kindle-redirect) about not trying to inflict metrics on people before the culture change happens, they'll game the metrics. Nick agrees, and also says he has the basic problem that coming up with the right metrics is hard. 

They agree that time is a really bad one: trying to quantify tech debt around the time you spend on it actualy doesn't work (though it's not worthless). 

Some organizations build a bit of burndown into every sprint, but Chris isn't seeing that widespread - but Nick says that after about a year, his shop *is* finding ways to do just that. 

It took a year of seeing the results of concerted bursts of burndown, and a company-wide Objective and Key Result (OKR) on Trustworthiness. One challenge he has is that it's hard to tie in the minds of senior executives information security (which is what Nick does) to availability and scalability as opposed to firewalls. But his colleagues are making great progress. 

Nick thinks the most useful thing he's done in the past year is to embed engineers, developers, SREs and security people into standups as often as possible to try and find the overlapping interests. And that has led to some success around thing together tech debt they need to code around and the performance of engineering squads. 

Chris spent a bunch of time recently looking at Chaos engineering and how to introduce it into what they do, but he's finding that if you've not already got to the stage where you can do good quality progressive engineering you're just not ready to do Chaos engineering. Similarly, Nick thinks that applies to Eng teams that find themselves working harder but not having a commensurate increase in productivity. 

What Chris sees in the bottom 50% of companies is related to a [Charity Majors](https://twitter.com/mipsytipsy/status/1270676644965957633) comment that they have the engine underwater and they have to work ever harder to see that they need to do something to drain the water that is flooding you. 

{{< tweet user="mipsytipsy" id="1270676644965957633" >}}

When technical people have to talk to non-technical people about this, people who are smart but don't see the tradeoffs in feature development, the non-tech people don't understand the tradeoffs. Not that they don't want to understand, but that they don't see it. so the quest for metrics is really about finding Indicators Of Tech Debt. 

Chris points out that time is bad as a measure because for engineers, it's really less about time and more about getting into flow state: is your tech debt preventing flow from happening?

He mentions this is related to cognitive load, and that he's been following the work of [Team Topologies](https://teamtopologies.com), whose principles [Matthew Skelton and Manuel Pais](https://teamtopologies.com/people) have been spending years with organizations starting the DevOps topologies, finding patterns and anti-patterns and how work flows betwen those teams. They feel teams need to be organized to minimize cognitive load.

It seems to be about putting boundaries around the members of teams so that they can actually apply their brain power to the problem at hand in the context of their work, and Chris thinks we can start to reason is that tech debt is adding a constant cognitive load that everyone has to deal with. 

This is a self-inflicted wound: rather than just doing a task, they have to remember oral histories of "when you're trying to make something in this environment, here are the 24 undocumented things you have to look out for or they will bite you."

Nick and Chris raise the idea that tech debt is not necessarily just "old stuff" because mainframes are just often not tech debt, because they still work. 

Tech debt is more tied to the fragility of environments.






