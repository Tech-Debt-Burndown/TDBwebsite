+++
Description = "On this episode, Chris and Nick are joined by Olivier Jacques, DevOps transformation principal at DXC Technology, who discusses his article, Six Strategies to Set Time Aside to Improve. The six approaches capture some very insightful observations into technical debt burndown."
Date = 2021-05-23T06:00:00-04:00
PublishDate = 2021-05-23T06:00:00-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "44951984/play.mp3" # the name of the podcast file, after the media prefix.
#Get the podcast file by going to spreaker>Podcasts>Episode>Direct Download Link and copy the numbers before
#/download.mp3. Place these numbers to replace the hashmarks so it is something like 12344567/play.mp3 
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
guests = ["olivier"] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Episode 8: The Six Ways"
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
**Recording date: May 17, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### "Everybody wants to reduce tech debt, but nobody wants to pay for it." - Olivier ####


Nick and Chris are joined by Olivier Jacques, a Distinguished Technologist at DXC and CTO in DXC’s application services department in France. Recently, Jacques wrote [6 Strategies to Set Time Aside to Improve](https://www.olivierjacques.com/blog/devops/6-strategies-to-set-time-aside-to-improve/), an article that spells out six ways to approach technical debt reduction. 

Olivier thinks that policy debt, technical debt, security, debt, infrastructure, debt, and other debt types are something that must be paid attention to, but he was wondering why we don’t seem to have the time to address them  - we are either too busy, or we don't have the management support, or sometimes we don't even know where to start and what do we improve. So he set out to write up some strategies he feels will help. 

{{< tweet 1390075907805700097 >}}

We don't easily know where to start, but he thinks where he saw the biggest struggle was perhaps in explaining to management and leadership what it meant to reduce tech debt, and how to organize a team to make sure that ted debt is not something put on the back burner and forgotten. 

First, Olivier came up with The Six Ways, but he wants to be clear that after hearing from many readers, he isn’t saying there are *only* six ways -  we can definitely add many more. 

In setting them down, Olivier created two buckets of activity: Work (W) and Improvement (I). He models his Six Ways on the example of the agile scrum team, running in a two-week sprint cadence. And within those two weeks’ worth of sprint, the question is, within this cadence, how can we build in time for I while conducting W. 

He makes the assumption is that there is a commitment somehow somewhere, maybe by idea, the product owner or the leadership to explicitly say that they want to improve, and they they are willing to spend 25% of their capacity to do just that. Again, this is a rule of thumb; some teams may not need to spend that amount of time to reduce technical debt. And some teams may be in a state where they actually need to spend way more time in reducing tech debt. 

#### The First Way ####
A twenty-five percent improvement on top of everything else. This is not a place where you want to be, because you end up having a very extensive days, obviously, but, but at the same time, it's very often the expectation from management. There's often a sort of base-case assumption as the team is just taking care of managing tech debt on the, on their own. Some of the engineers I've been speaking to in the past few weeks feel strongly feel that it's their responsibility to manage tech debt – that this management shouldn’t be actively visible to product owners or other forms of management. 


#### The Second Way ####
This may be an anti-pattern, but the Second Way is spending 100 percent of your time improving. Olivier calls it Panic Mode. 

#### The Third Way ####

Say you’ve got a natural slump in the business cycle at your company, or just a period where it is natural to slow down; you might consider spending 100% of a sprint on burndown. 

#### The Fourth Way ####
The fourth approach is the Rolling Improvement model. In this strategy, we, we spread evenly who is going to work on improving technical debt. Olivier made a simple algorithm that basically has all engineers spending 25% of their time within a given sprint on tech debt, staggered so that most of the engineers are on their 75% of normal work while a small portion dips into and out of the 25% burndown role. 

Nick likes this one, because it lets us not feel like we are throwing our hands up in despair and saying that nothing works, which executives don't like to hear and, frankly, they’re right in saying that, but it also allows engineers to tend to the garden of things that need to be tended while folding in normal work; he thinks it's a little bit less disruptive than some of the others Ways. 

#### The Fifth Way ####
The fifth way is that everyone spends 25% of their capacity each day – two hours of every eight - on improving. All three like the idea, but Nick points out that it assumes that engineers have eight hours a day to code, which is fantasy. He mentions the large and increasing burden of meetings (citing specifically Steve Glaveski’s terrific article, [The Five Levels of Remote Work — and why you’re probably at Level 2]( https://medium.com/swlh/the-five-levels-of-remote-work-and-why-youre-probably-at-level-2-ccaf05a25b9c)) means that you never really have anything near eight hours. 

Chris mentions the current joke about “*this meeting could have been an email*”, and Olivier says that too much work in progress is really terrible for flow. He cites Joel Spolsky’s classic 2001 essay on the subject, [Human Task Switches Considered Harmful]( https://www.joelonsoftware.com/2001/02/12/human-task-switches-considered-harmful/).

Which brings us to 

#### The Sixth Way ####

One sprint of four focuses on tech debt burndown. This is Olivier and Chris’ favorite, and Olivier says he can really rally the team around this vision. They started really looking forward to this one sprint every four that is totally focused on improving and reducing technical debt. No interruption, unless a catastrophe arises, and we get management back up to, to really say, yes, this sprint, we understand you are working on the reducing technical debt.





