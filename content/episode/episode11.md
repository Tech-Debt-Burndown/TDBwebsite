+++
Description = "Allan Friedman of the National Telecommunications and Information Administration (NTIA) has long been one of the world's leading proponents of Software Bill of Materials, or SBOM. With the President's Executive Order on Improving the Nation’s Cybersecurity, SBOM has begun to receive the wider attention it deserves, and Allan joins Chris and Nick to discuss SBOM and how it can help with tech debt burndown."
Date = 2021-06-20T07:21:05-04:00
PublishDate = 2021-06-20T00:00:01-04:00 # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "45272021/play.mp3" # the name of the podcast file, after the media prefix.
#Get the podcast file by going to spreaker>Podcasts>Episode>Direct Download Link and copy the numbers before
#/download.mp3. Place these numbers to replace the hashmarks so it is something like 12344567/play.mp3 
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
guests = ["allan"] # The names of your guests, based on the filename without extension.
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 1 E11: Allan Friedman and SBOMs"
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
**Recording date: Jun 8, 2021**

*Download at [Apple Podcasts](https://podcastsconnect.apple.com/my-podcasts/the-tech-debt-burndown-podcast/1562710899), [Google Podcasts](https://podcasts.google.com/feed/aHR0cHM6Ly93d3cuc3ByZWFrZXIuY29tL3Nob3cvNDg3MzE4MC9lcGlzb2Rlcy9mZWVk), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### "Having a list of ingredients doesn't mean that you'll eat healthy, but it's very difficult to eat healthy if you don't have that" - Allan Friedman

After introducing himself, and his role at the National Telecommunications and Information Administration ([NTIA](https://www.ntia.gov/)), Allan gives an overview of Software Bill of Materials ([SBOM](https://en.wikipedia.org/wiki/Software_bill_of_materials)) using a 'list of ingredients' analogy.

The efforts around SBOM have been underway since 2018, and there was initially pushback from the software industry, in part because organisations didn't have their open source licensing in order. As the NTIA has gone through the process of creating a consensus vision around SBOM, many of the original detractors have found that it provides a reason to clear up stuff that needed doing anyway.

Allan goes on to provide an example of how an SBOM gets used as a proxy for understanding total cost of ownership for software, and how that can be used as a negotiating lever. Vulnerability management, and understanding how most modern software is composed (largely from open source) rather than created from scratch is a central part of the utility of SBOM, so that software users can understand where weaknesses originate from.

We then go on to discuss the positioning for proprietary software, touching on the 'black box' problems that arise, particularly in environments that demand high levels of accreditation like healthcare.

Allan talks about the list of ingredients not meaning that anybody can replicate something, which reminds Chris of the UK TV show [Snackmasters](https://www.channel4.com/programmes/snackmasters/episode-guide/) where celebrity chefs struggle to reproduce popular snacks. This leads Allan into some description of the challenges dealing with a lack of a global namespace for software.

We then move to some discussion of the [12 May Executive Order on Improving the Nation’s Cybersecurity](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/), which sets the ball rolling for SBOM implementation in Federal Government:

> (f)  Within 60 days of the date of this order, the Secretary of Commerce, in coordination with the Assistant Secretary for Communications and Information and the Administrator of the National Telecommunications and Information Administration, shall publish minimum elements for an SBOM.

After talking about the difference between ingredients labels and nutritional information labels the conversation turns to how difficult it is to understand what compilers will produce from source code. This is a familiar problem for Chris, who's previously examined how compilers can produce startlingly different output for seemingly trivial and functionally identical source code [The compiler will not save you](https://blog.thestateofme.com/2013/10/12/the-compiler-will-not-save-you/).

Before we wrap up, Allan notes that there was a chicken and egg problem with SBOM and the tools to produce an SBOM, but that's largely addressed now by new companies and products emerging to fill the need; along with existing products growing additional capabilities.