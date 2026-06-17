+++
Description = "Chris and Nick on AI Tech Debt"
Date = 2025-10-31T13:00:00Z
PublishDate = 2026-06-17T12:00:00Z # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "71986204/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 3 E6: AI Tech Debt"
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
**Recording date: 31 Oct 2025**

*Download at [Apple Podcasts](https://podcasts.apple.com/podcast/the-tech-debt-burndown-podcast/id1562710899), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### AI Tech Debt

Nick and Chris talk about the security, data privacy, and operational challenges of enterprise AI adoption, highlighting how executive pressure driven by "Fortune front page FOMO" often leads to hasty deployments. Drawing from a presentation by ARM's Richard Grisenthwaite on trustable AI, they emphasize that the majority of AI security relies on foundational security practices that organizations should already have in place. They explore the critical concept of the "blast radius" and the "cost of wrong," illustrating how tools like ChatGPT Enterprise and Model Context Protocol (MCP) agents can inadvertently grant models excessive, godlike access to sensitive workspaces and shared drives, bypassing principles of least privilege. They draw parallels to historical trials with the Google Search Appliance and early web service API sprawl, showing how unchecked connectivity creates massive security liabilities if data flows and roles are not rigorously mapped and monitored.

To mitigate these risks, the hosts propose a tiered compute model that prioritizes local LLMs and private data centers for processing and classifying unstructured data, keeping the vast majority of workloads off frontier lab servers. They also discuss auditing enterprise ChatGPT compliance APIs to manage retention and risk. Shifting to software engineering, Nick and Chris reflect on DevOps Research and Assessment (DORA) findings, warning against "development team phrenology" and noting that while AI coding assistants boost individual productivity, they can degrade overall team efficiency by generating complex, "sloppy pull requests" that lack proper test coverage. Ultimately, they view these AI tools not as magical solutions to legacy systems, such as aging CICS COBOL code, but as evolving utilities that require structured platform engineering and automated testing to prevent accumulating even more technical debt.

#### Show notes (links)

[AI innovation begins with trust: Richard Grisenthwaite (ARM)](https://www.youtube.com/watch?v=JP1J9pXCvmg)

[How FOMO Is Turning AI Into a Cybersecurity Nightmare (Inc.)](https://www.inc.com/nick-selby/how-fomo-is-turning-ai-into-a-cybersecurity-nightmare/91261473)

[44CON](https://44con.com/)


#### Transcript (automated)

Nick Selby: It's the Tech Debt Burndown podcast. I'm Nick Selby.

Chris Swan: I'm Chris Swan.

Nick Selby: We are here to talk about tech debt and AI. I can hear the groaning, but stick with us.

Chris Swan: [00:00:30] So I was at a thing yesterday, Nick. It was Richard Grisenthwaite, who is a chief architect at ARM, and he was talking about trustable AI. And of course, he eventually landed up at the things they're doing in the hardware with trusted runtimes and secure elements. But along the way, he had a very strong point that 90 to 95% of the security you need to do for AI is the security you should be doing already.

Nick Selby: [00:01:00] Yeah, 100%. Really, you and I, Chris, have been talking, and lots of our colleagues have been saying the question every organization has to ask, if you boil it all down, is: what is the cost of wrong? What happens if this thing goes pear-shaped all of a sudden, and the connector or the tool or the software you put in goes berserk? Maybe it's a cybersecurity thing, like what happened with drift. They get hacked, and then they're using the tool you've installed to gain access to the things you don't want. In which case, your question is: what is the cost of wrong? What do they get if that happens? Or it's an AI mistake where the AI itself goes a little bananas and starts grabbing things you didn't expect it to grab. The real question is: what is in scope? What systems and data are you granting permission to the AI when you install it? That brings us to what you just said. In order to do that, I basically need to understand a data flow diagram of where things are going in my organization, which is easy if you're doing things well. It's really difficult if, for example, over the past four years you've had organic sprawl tied to non-controlled tech debt and process debt. Things are just getting installed, and you're not 100% sure what the data flows are.

Chris Swan: [00:02:30] I think a nightmare scenario emerges here: in one part of your organization, you're doing an enterprise-wide AI deployment because that's what the executive suite wants, and giving it godlike powers over all of the data that can be reached, because how can it do its job without that? And in another tiny niche, someone says, "Wouldn't it be helpful to our customers if we gave them an MCP agent?" Yes, and those things are actually connected. So people can ask questions through what should have been a protected API, but is now a large language model interface, and potentially tap into that godlike access you've just granted to the AI overlord.

Nick Selby: [00:03:00] Totally. By the way, the human part of this—the pressure on CEOs to adopt and integrate AI tools is really huge. It's very pressing from investors and boards of directors who are looking at competitors and saying, "They've used AI and they're increasing their competitiveness, and therefore we have to," when none of them actually knows what they're doing with it. They don't have a use case.

Chris Swan: I call this Fortune front page FOMO.

Nick Selby: [00:03:30] Yes. That's the headline of an article I'm writing about this right now. It's exactly what's happening. The AI "everything" impulse is very real and it's very difficult for executives to resist. The question I asked is: what's the cost of being wrong? What is this thing connected to? And what happens if something goes bad? Can we understand our damage? Of course, the next thing you're going to say is: how do I minimize the data I share with the AI software? I'm quoting Wendy Nather because she says if you say AI, immediately everyone is ensorcelled and enchanted, and they stop listening and using their critical thinking skills. If we just say software, what connections is your software asking for or demanding? Here's an example: we were looking at a tool that does revenue projections. To do that, it asks, "Let me get into Salesforce and take a look at all the revenues you're currently getting, and then deal flow and pipeline." Now we're into Google Workspace and Microsoft 365, so I need to have access to the emails. I also need full access to the Zoom or Google Meet calls that I'm going to record. I want to hear them to understand customer intent. By the time you're done looking at what they want, it's basically everything. You have to understand what each of these processes is in order to make decisions and say, "I'm not going to grant this software that right." Here is a perfect example: why do you need access in your tool to the emails when you're connecting to Salesforce and Salesforce is already connected to our email? Salesforce is already automatically adding the emails between the prospect and our salespeople to the Salesforce record. Is there a distinct, unique advantage we get by letting you also record the emails? Maybe they're better at it, who knows? But you have to answer the question. I'm not telling you what the answers are. I'm just saying, ask the question because the vendor is going to ask for admin access to everything. That's really what they want. Again, it's harder if you don't know what your data flows are and you don't understand your own environment. Here's what we learned this week helping a customer with ChatGPT Enterprise. They actually did a pretty good job rolling that out, and they immediately came up with a use case where they wanted to connect ChatGPT directly to their Google Workspace. The use case is, "Hey ChatGPT, go in and tell me, of all the documents that are sitting in my drive right now, what are the top three most important things and summarize what I have to do." I think it's stupid, but people like that. So immediately, in looking at the threat model and the risks, we talked to the executives and said it's probably not good to give it access to all the shared drives because the chance of really sensitive stuff being in there is high. Interdepartmental stuff is much higher. But if it's a "My Drive," then you could do it. We looked and saw that there's a self-service option so each user could opt in to the My Drive. That's how we got here. The executives said they don't want to give it shared access, but they do want to give it opt-in My Drive access. That sounds great, except you can't because of the way ChatGPT is working. What we discovered—and it wasn't me, it was one of their IT guys—is that even in the self-service option, what they're saying is the account can opt in with self-service. If you click yes, you're not saying yes to my drive, no to my shared, and yes to my Gmail, but no to whatever else. You are saying ChatGPT can have anything I'm entitled to touch inside the Google Workspace, on or off. That's not okay because you're getting shared stuff in there. The alternative is an administrator-managed opt-in, which opts in the entire organization for absolutely everything. Immediately, there's this giant sucking sound as OpenAI takes absolutely everything in your Google Workspace and tags it. Now they say, "Don't worry, we can give you role-based access control. Just tell us what users should not be able to see, and we won't let them see it, even though we have it."

Chris Swan: Least privilege, anybody?

Nick Selby: [00:08:00] What they're saying is, "Listen, we understand that we have architected our machine for most privilege, but we're happy to give you least privilege." There's comprehensive documentation on role-based access control (RBAC) in the OpenAI ChatGPT Workspace. The problem is, how many times this week have you heard of ChatGPT in particular, or any AI in general, exceeding the explicit limitations of access the user has given it, often catastrophically? Your only recourse is to yell at it and say, "Didn't I tell you not to do that?" At which point it says, "Oh, you're absolutely right. Would you like me to make a PowerPoint or a document about why what I just did was really bad?"

Chris Swan: If there are no financial penalties associated with that, then the incentives are misaligned, aren't they?

Nick Selby: [00:09:00] Hugh Rogers pointed out a meme from the past couple of weeks where the robot surgeon takes out the wrong liver or the wrong kidney, and then says, "Oh, you're absolutely right. Would you like me to take out the other one?" Tying this back to tech debt—because this is actually a concern with this other customer—do we know the boundaries and the bright lines we're drawing organizationally with all these different tools? I don't know of anyone who's just getting one integration. Then you just said the terrifying phrase, MCP. You weren't there at 44CON. Somebody said that the S in MCP stands for security, and it's totally true.

Chris Swan: [00:09:30] Someone yesterday was telling me that I was a Luddite and wrong when I was drawing comparisons to what was happening with web services and enterprise search 20-odd years ago. And yet I keep seeing the patterns repeating. 20-odd years ago, we did a trial of the Google Search Appliance.

Nick Selby: Yes.

Chris Swan: [00:10:00] It was amazing. All of the things that were impossible to find on the intranet—because we still called it that—were suddenly at our fingertips.

Nick Selby: Oh.

Chris Swan: We finished the trial and then gave the appliance back because it could only work with godlike access to everything. It also needed to phone home to Google; it couldn't just be sitting in our data center doing its job. Eventually, the risk people said, "On balance, no."

Nick Selby: [00:10:30] Do you remember Nick Patience at 451? He was doing search stuff back then, and we had a conversation about the Google Appliance. What I'm most fascinated by is that you were able to find things at your fingertips. Nick was saying at the time—I'll take responsibility through the sands of time if any mistakes here are mine—but what he was saying was it has godlike powers of discovery and it demands godlike powers of connectivity. Where it fell down was that the Google search algorithm, which is basically that which is popular is best, didn't actually lend itself to an enterprise use case. Often, the most important document you're looking for is the one that isn't linked to by a lot of things, like merger or going-public documents, so there are not a lot of links within other documents to get to it. It was both grabbing too much and sending it all to Google, and not giving you good results. But you're saying the opposite.

Chris Swan: [00:11:30] Firstly, it wasn't grabbing it all and sending it to Google; the model was on-prem processing, otherwise we would have never even racked it. But it did need to phone home for updates; there was an umbilical cord back to HQ to keep the algorithms fresh. There was some concern that it could have been exploited, especially since this was before the initial Chinese attack on Google's infrastructure. If someone got into Google's infrastructure, could they pull stuff across the umbilical cord that we never wanted anyone else to see? The search was really good.

Nick Selby: Oh, wow. Okay.

Chris Swan: It was really good at not showing you stuff you weren't allowed to see.

Nick Selby: Interesting. Okay.

Chris Swan: [00:12:30] We were able to overlay that role-based access model, so it would know a document existed, but if you weren't permissioned to see it, it would respect that from the underlying ACLs.

Nick Selby: It respected your ACLs and your RBAC. That's what OpenAI doesn't do.

Chris Swan: [00:13:00] That was a really neat thing about it. I couldn't just go spelunking for the executive compensation spreadsheet, because I wasn't supposed to see it. Where this potentially fell down was if the executive compensation spreadsheet was set on a SharePoint somewhere, using security by obscurity, and was actually open to everyone—you just had to know where it was.

Nick Selby: Right.

Chris Swan: [00:13:30] Actually, that was one of the things giving people the heebie-jeebies: we have all this power, but have we properly constrained it in our run-of-the-mill permissioning? Previously, you couldn't find anything on the intranet, so it hadn't been a problem. This was making stuff findable in a way that it hadn't been before. The MCP thing also keeps reminding me of the web services thing. I remember 20-odd years ago thinking that web services meant every piece of infrastructure software was going to have a web services API, and we were going to have an explosion of these APIs.

Nick Selby: [00:14:00] Yes.

Chris Swan: How on earth were we going to deal with all of that?

Nick Selby: Mhm.

Chris Swan: [00:14:30] Now, on reflection, every piece of infrastructure software has an API. How does anything work without it?

Nick Selby: Right.

Chris Swan: [00:15:00] That hasn't given us a massive challenge in managing that API surface area, because it has become a natural part of how things work around our organization. Think about the systems that have those APIs, like Kubernetes—it all fell into that world, and we've ended up with platform teams whose role is to ensure that it is properly controlled and managed.

Nick Selby: [00:15:30] If you're lucky. Again, this brings us back to the tech debt stuff. If you're not keeping up with it, it sneaks up on you very quickly, and the aggregate effect of not tending your garden properly is massive. What we've been talking about are three main areas: first, enumerating the risks and doing threat modeling of what you're connecting to, which requires that you understand those data flows. What is it going to be touching, and how bad would it be? The second thing is blast radius reduction. What can you change with the permissions you're giving these tools? We also need to monitor it to be sure. We use Obsidian Security; it is a SIEM for SaaS. It monitors the logs and activity APIs in your SaaS clouds. If you connect Obsidian to your Google Workspace so that you see what's happening there, like high-volume downloads or a network change in the middle of a session. If something is obviously wrong, and you connect the other side to ChatGPT, you start to get triangulated alerts. We've seen data loss prevention (DLP) tools fail. Even when properly tuned to notify us if someone downloads gigabytes of data from Salesforce, they can miss it. You have to test all of these things you're using as compensating controls to reduce the blast radius. The last thing is instrumentation and alerting. If all that other stuff fails, how will you know before you get a phone call from CISA or the FBI, or someone sells your data online and sends a ransom request.

Chris Swan: [00:17:00] This is another thing: I hear people talking as if anomaly detection suddenly came out of the cupboard yesterday. People were selling me silver bullets with "anomaly detection" carved on them 20-odd years ago. Did it work then? Yes, in demos. Did it work in production? Not all the time.

Nick Selby: [00:17:30] Network Behavior Anomaly Detection (NBAD) was hopeless at a lot of things. It could detect a worm—it could always detect a worm—but the thing it was really good at, which every CTO loved when they saw it, was mapping where all your hosts were. It was the first time you could get a map of your hosts. It was really good at detecting hosts; it just wasn't good at detecting anomalies.

Chris Swan: That leads us into the tired old conversation about NIDS versus NIPS.

Nick Selby: Yes.

Chris Swan: [00:18:00] The problem is you hit an unacceptable false positive rate. Then you turn up the squelch to get that under control, which leads to an unacceptable false negative rate. You miss the anomalies that should be flagged because you were trying to reduce false positives. Now you're dealing with false negatives, and the product isn't doing what you bought it for.

Nick Selby: Mhm.

Chris Swan: [00:18:30] The whole venture has been a massive waste of time. Arguably, after 20-odd years of improvement, this technology has been refined to a point where false positive rates are in a region where it becomes dependable and acceptable. You're not getting false negatives as a consequence, and you can have a trustworthy, anomaly-based tool. It is still all statistics. The other problem is that attackers can understand the underlying heuristic mechanisms and design their attacks to sneak past the anomaly detection.

Nick Selby: [00:19:30] I was having a conversation yesterday that you just reminded me of. Dave Aitel said that Snort is the best IDS. I asked why, and he said, "Because IDS doesn't work at all, you need it for your audits, and Snort is free." I thought, "Okay, that's actually really good." To jump back to AI and tech debt, one of our consultants was working with a customer in the defense industrial base in aviation. They wanted to connect their ERP system—which contains spare parts data, some of which is for military purposes—to an AI tool to generate large proposals. The risk is that aggregating this data could result in a classified or sensitive dataset. The tool could compile a proposal for all 458,000 parts in a way no human could. But the challenge was that nobody knew how the ERP system worked because it had expanded organically over the years, and no one knew what was in it. Yet they wanted to hook up this AI tool that they didn't quite understand. It pulls data out through an MCP, takes it somewhere, and does something with it, without anyone knowing where. Our consultant's approach was cool: he ran a local LLM on his machines, connected it, and asked it to analyze what was in the ERP system. I thought that was a clever solution.

Chris Swan: [00:21:30] This is one of the ways organizations can deal with data migration concerns in practice. If you can run the tool on your laptop or desktop, that is the right place to do it. If it needs more compute and you have a data center, you can put a few racks of GPUs there to provide an enterprise capability. You end up with a tiered model: as local as possible.

Nick Selby: Yeah.

Chris Swan: [00:22:00] 90% of your workload probably happens on your laptop, 9% in the data center, and a tiny residual fraction goes to frontier model-based services. Because it's a much lower volume, you can be more surgical about policies around what is allowed, which also opens the door for automated classification. You touched upon a foundational problem: in most cases, we are looking at vast quantities of unstructured data and don't know what we should care about. There is also the classic data aggregation problem. When Chelsea Manning copied a whole bunch of secret cables onto a CD, each individual cable was classified secret, but in aggregate they created something that fit the description for top secret. That is why a set of documents in aggregate might be treated as having a higher classification level than individual documents. This has been a problem since the switch from paper to IT. As soon as you had a hard disk or a CD full of data, you were immediately in an aggregation problem. A document might be level two, but a whole CD's worth should probably be at level three or four. We are now using these tools to reason about how documents should be classified, and LLMs are excellent at that.

Nick Selby: Yes.

Chris Swan: [00:24:00] That is not a job where we want to be sending everything over the wire and using expensive tokens. It's a job we want to do as close to the data as possible and locally, so it's not going to a third party and exposing us to their risks.

Nick Selby: [00:24:30] There are so many good points there. One thing I want to point out—we may open source this, but right now it's too ugly—is that we've made a tool to help people audit their OpenAI ChatGPT Enterprise accounts using the compliance API. This compliance API is terrifying. I got it running here, and it can show everything the CEO uploaded into ChatGPT over the past six months, what this group did, or what everyone did. We wanted to force ChatGPT not to retain things. You can use this tool to delete everything uploaded since the last request. While they tell you there is a 30-day retention period, with an enterprise account you can keep deleting things to reduce retention risk. If you have an enterprise account, it is a really cool tool.

Chris Swan: Even that makes me scratch my head, because my understanding is OpenAI is subject to retention requirements.

Nick Selby: [00:25:30] They are, but that seems to be mainly for public-facing accounts. If you have an enterprise account, it's a private instance that is yours. What they have been asked to hold in other cases is their response, which could contain your information, especially if you ask it to rewrite a memo. The specter of OpenAI holding your data for training is also easily avoided with the enterprise account; they won't use it for training. I was wondering if you knew of tools to help understand how engineering teams are functioning—not just by looking at how many commits they make, but using AI to figure out how effectively and how often they are working.

Chris Swan: Development team phrenology.

Nick Selby: Exactly. I'm not suggesting we use that, but—

Chris Swan: [00:26:30] I'm not familiar with any of that because it immediately crosses an ethical boundary for me.

Nick Selby: Yes.

Chris Swan: If we look at the established research about making highly productive teams,

Nick Selby: Mhm.

Chris Swan: [00:27:00] It's not about trying to measure individual productivity. Even measurements of team productivity are somewhat wishy-washy. I had the pleasure of meeting one of the researchers from DORA a couple of weeks back. DORA is no longer an acronym; the "DevOps" has gone.

Nick Selby: Right.

Chris Swan: [00:27:30] They have moved from a world of DevOps to the post-DevOps world of AI. This year they've been focusing on research showing that AI coding assistants give individuals the sense that they are improving productivity, but give teams the sense that they are making things worse. I've seen this up close recently, where we are getting what I call sloppy PRs. It is easy for someone to think, "I don't know how to do that, but the coding assistant will help me do it." They make it work, submit it to their colleagues for review, and the colleagues reviewing it ask why something that should be in just a few files is changing code across 300 different places.

Nick Selby: [00:28:30] Unwittingly, you're answering my next question. You and I have talked about how we do tech debt surveys. The last one we did took two weeks; we got back 16 textbooks' worth of responses and had to go through it all manually. I'm wondering if you know of any AI tools designed to look for evidence of tech debt, beyond just vulnerable code or infrastructure vulnerabilities. How would they even start, and have you heard of anyone doing this?

Chris Swan: Not within that bounded context, though that sounds like a startup idea.

Nick Selby: Somebody already got funding for it.

Chris Swan: [00:29:00] Coding assistants are being pitched to help understand your codebase in a way you might not be able to, perhaps because the people who wrote that CICS COBOL retired. That's a common issue in the industry. It's not necessarily couched in the language of tech debt, but it is about gaining understanding. The practical issue is that a lot of that older code doesn't have tests.

Nick Selby: Yeah.

Chris Swan: [00:29:30] It's not just understanding what it is supposed to do; you also don't have any way of verifying that changes won't break existing behaviors. One of the promises is that we can construct tests for existing behaviors, but that is still a bit hand-wavy. All of this technology will get better. I sometimes find myself cast as a skeptic, but I know these tools are already useful and will improve with successive iterations. We are in a bubble, but on the other side of it, there is clear utility we will exploit. People are talking about whether we have exhausted what we can do with LLMs. Once we have trained frontier models on everything we can scrape, that might be the limit. We may not be able to go further with that approach. AI research has other realms we haven't systematized yet. We have industrialized our ability to do the underlying vector math, so can we apply that in other areas? There is still a lot to be hopeful for.

Nick Selby: We're going to leave it there. This has been the Tech Debt Burndown podcast. I'm Nick Selby.

Chris Swan: And I'm Chris Swan.

Nick Selby: [00:31:30] Thanks for joining.
