+++
Description = "Episode 2: Ian Amit of Cimpress"
Date = 2021-04-11T16:01:03-04:00
PublishDate = 2021-04-11T09:51:03-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "44295022/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
guests = ["iamit"] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Episode 2: Ian Amit"
#subtitle = ""
images = ["img/episode/default-social.jpg"]
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



### "You can't kill all the tech debt; you can't stay completely up to date or there won't be a business."
### -*Ian*


**Recording date: February 6, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*


We had a great conversation with Ian about how he runs a rather different kind of information security operation that can be described as a group of companies reporting up to one security organization for strategy, but which each support their own individual needs day to day. 

Ian Amit spent most of his career in information security, with a lot of time on the offensive side. He spent some years as a senior manager at AWS, and in the past few years he has been Chief Security office at [Cimpress](https://cimpress.com), which runs a collection of independent businesses whose CISOs report up to Ian, who is kind of the supervisory CSO - this set up is most similar to that of GE's.  

Some of the smaller firms have no CISO, and Ian then serves as their de facto CISO, and the larger brands - most notably including [VistaPrint](https://vistaprint.com). And Technical debt is primarily Ian's responsibility - he and Nick have discussed it quite a bit over the years, and Ian was pivotal in a presentation Nick made, [Tech Debt Burndown: Kill It With Fire](https://corncon.net/2020-presentations/#nselby) which he presented at [CornCon VI: The Return of the Cyber Jedi 2021](https://corncon.net/2020.corncon.agenda.html).

Nick asked about whether there was a difference between security tech debt and technical debt. 

Ian thinks Tech Debt is Tech Debt, but that it has a lot of security repercussions. 

Accrual of tech debt gunks up the business operation and also opens up the company to additional risk. 

Chris observed that old stuff has known vulnerabilities, new stuff might have vulns but only the most sophisticated attackers are going to find the 0days, But in terms of staying atop patching, how much does it relate to testability of the environment? 

Ian says that's something he thinks about a lot - known knowns versus unknown unknowns. He tries to let the business decision guide the way - not to discount security, but prioritization matters. Tech debt by itself is not a problem, it is only one after you view it in the context of how it might affect the business.

It may be OK to carry a certain tech debt indefinitely if it isn't slowing the business. The exercise is to get the right stakeholders to really understand what they need and what our stack delivers. 

Nick was wonders whether Ian was hired with tch debt as  a guiding principle, which may mean the executives actually understood this before he got there. That's rare. And also, what is Ian doing with metrics?

Ian agreed that the executives had a lot of tech debt, lots of companies with different histories - Vista Print is more than 20 years old and Cimpress' newest firm is two years old. They realized this was critical to success and growth. So the executives wanted someone who understood how to harmonize all these varying challenges, and Ian and management realized that technical debt burndown was central to the effort. 

Ian's approach to metrics is an interactive look at what is there and how it's being burned: both at the tail end (what is there out there that might bite me), and revisit our fresh decisions to be cognizant of repercussions they may have on tech debt accrual. 

This jibes with Ian's quote at the top of the page here, and he added the other quote of his that we love: "Tech debt is not a project; technical debt is a process."

Ian says he went through the herky-jerky attempt - start fresh, groan on until you can't proceed anymore, stop everything to burn it down - so often that he realized it just has to be embedded into every sprint. 

It can't just be the security people's job to chase it down - everyone in DevOps has to embed this into their processes. 

Ian would rather talk of code quality than secure code: if our code sucks, it is also fragile and insecure. 

Chris raised that some of this is the way we deal with the Red Queen, that it's a choice between a steady pace, or occasionally stopping for a breather which means we need to run even after we rest. 

Ian agrees, and recognizes that we have to adapt to the business needs. We need to run faster than the Red Queen, to run ahead and clear the path, and sometimes to drift behind in case she changes course.

With regard to SSDLC, which requires software development, and people discuss "shift left" - forget that. How do you start the conversation about technical debt before the PRD is done, before the design doc?
How do you get business people to understand the full cost of new tools or features before you even start building? 

Ian refers to lifetime ownership of the code, and when devs understand that they are responsible for the whose lifecycle of the product they tend to make better decisions at the top that will allow them to support what they build throughout its life. 



