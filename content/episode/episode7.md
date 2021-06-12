+++
Description = "Chris and Nick welcome Kenn White, from MongoDB, to discuss Mongo's enabling teams and how they cut through the BS to help engineers stay in the flow and be happier. Then they welcome Bill Pelletier, to talk about some of the unique challenges faced by medical device and Software as a Medical Device makers."
Date = 2021-05-15T12:22:13-04:00
PublishDate = 2021-05-15T12:22:13-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "44843787/play.mp3" # the name of the podcast file, after the media prefix.
#Get the podcast file by going to spreaker>Podcasts>Episode>Direct Download Link and copy the numbers before
#/download.mp3. Place these numbers to replace the hashmarks so it is something like 12344567/play.mp3 
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
guests = ["kenn","billp"] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 1 E7: Enabling and Regulating"
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
### What Do Enabling-Teams Look Like, and Can We Avoid Tech Debt in the Medical Device Industry?  ###

**Recording date: May 3 and 8, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### 'There were monkeys that were nesting in the satellite dish.' - Kenn ####


In a private Twitter chat, Nick and Kenn White, who leads applied encryption engineering in [MongoDB](https://www.mongodb.com/), were discussing tech debt burndown, and Kenn mentioned that Mongo maintains an entire team to remove distractions and handle barriers to engineer happiness. So this episode, Kenn joins Chris and Nick to talk about that, because Chris had been mentioning enabling teams in the past couple of episodes. 

Mongo recognized that when something takes one person two or three or four hours of frustration, that's real money when you're talking about three or four or 500 engineers. The Developer Productivity Team at Mongo set out to assure that everyone has on day one a fully functioning and configured Linux laptop, with all the tools, libraries, permissions, etc., that they will need on day one. This includes wikis and internal resources.

That "get out of the engineers' way" approach is what Chris has been describing, and this is a real life example. Kenn mentioned 10,000 to 20,000 hours of testing on every build, so it's expensive if a build fails. The way Mongo has approached this supports that kind of environment. This extends down to "I can't make Ruby 3.6 work on this particular Linux flavor" and the enabling team will tackle those kinds of problems. 

But when we sought answers on metrics, they seem to elude Mongo as much as anyone else, saying that metrics are divorced from real productivity; Kenn boils doing what works down to what makes engineers happy. That's not a bad metric. He says that the trick for his teams has been post mortems on every major project to find the tar pits and management pains in the butt, the lack of approvals (he puts a lot of emphasis on getting expense reports reimbursed quickly, which is another one we like), etc., and those lessons are iteratively applied. 

The group began to follow a thread that had begun pre-show, about Kenn's early jobs re-factoring cardiac monitoring software, but went off on a tangent that, while interesting (to us), was off topic. Which is where the quote about monkeys nesting in the satellite dishes, above, came out (it was a story about on-the-ground realities in an African networking project).

But Chris and Nick were very interested in medical device manufacturing issues: if you're in an industry that is heavily regulated to the extent that you can't make changes to anything once launched, and at the same time, the industry makes machines that can spend decades in the doctors' offices. How do you avoid tech debt if it is almost mandated by the law?

To answer this, we brought in Bill Pelletier, who has tons of experience in exactly this area.

Bill sets out a recent history of medical device manufacturing from custom hardware and waterfall processes through Software as a Medical Device and today's builds. Once you peel back the fancy, shiny cover from a computerized tomography (CT) scanner, you are going to find commercial off the shelf, hardware, nothing special about it, and in many cases it is running off-the-shelf software operating systems, which is fine right up to the moment you put a network jack on it. 

That gets us into the meat of the problem: testing systems for these devices are designed for these big monolithic, all-encompassing, "test everything" processes which just doesn't make economic sense in the new paradigm. Enter, over the past five or six years, the Software as a Medical Device. No longer constrained to this older hardware model, we were one step closer to more readily available software updates, using agile methodologies - but the testing regimes are still a huge barrier. This has led to the rise in recent years for calls for better software bills of materials, and pushes to require manufacturers to identify every software component with a standard taxonomy so that users can know immediately what's inside. 

THe discussion turns to the realities of this struggle to balance security and software concerns with those of patient safety that, ironically, is often better maintained sticking with the known state - as in many critical environments, the bias is toward saying with the known good because the cost of being wrong is so high.  

