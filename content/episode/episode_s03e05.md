+++
Description = "Chris and Nick on Cloud vs On Premises"
Date = 2024-11-15T13:00:00Z
PublishDate = 2026-06-10T12:00:00Z # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "71986203/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 3 E5: Cloud vs On Premises"
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
**Recording date: Nov, 2024**

*Download at [Apple Podcasts](https://podcasts.apple.com/podcast/the-tech-debt-burndown-podcast/id1562710899), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### Cloud vs On Premises

Chris and Nick dive into the widespread misunderstandings and economic realities of choosing between cloud and on-premises infrastructure. They discuss how cloud service providers have driven organizations to perform "lift-and-shift" migrations that replicate messy data center environments in the cloud. Rather than achieving the promised cost savings and agility, these organizations inherit the same technical debt while facing skyrocketing bills and unexpected administrative costs in areas like logging, compliance, and observability. They also highlight that while the cloud is invaluable for early-stage startups and rapid feature deployment, it can quickly become cost-prohibitive without proper optimization, architecture, and governance.

To combat these challenges, Chris and Nick outline the growing trend of cloud repatriation, drawing an analogy to managing an energy grid with a steady "base load" and spiky peak loads. They suggest that organizations are increasingly finding it more economical to run their predictable base loads on-premises, leveraging hyperconverged infrastructure or modern private cloud platforms like Oxide. The public cloud can then be better matched to  highly variable workloads. They also explore how Kubernetes has served as a key driver for this workload portability, and note the unique exception of modern AI workloads, where hyperscalers dominate the supply chain for high-end GPUs like, forcing companies to stay in the cloud to access cutting-edge hardware.

#### Show notes (links)

[Enshittification](https://en.wikipedia.org/wiki/Enshittification)

[Oxide](https://oxide.computer/)

[Gomboc](https://www.gomboc.ai/)


#### Transcript (automated)

Nick Selby: It's the Tech Debt Burndown podcast. I'm Nick Selby.

Chris Swan: And I'm Chris Swan.

Nick Selby: [00:00:30] Chris and I have been talking for some time. The first conversation that actually led to this podcast was when we both realized that we were working on exactly the same kind of thing, where we came into an organization and had to look at a massive tech debt and start to address it. That inevitably led to the conversation about the cloud being misunderstood, with executives believing that because they've got their AWS password and signed up for it, their agility should be here any minute now. This idea that a cloud account of some flavor is an automatic step up or step down, depending on who you're talking to. Maybe about a week ago, we saw a tweet that has since been deleted saying, 'I've known for years that the cloud was much more expensive and much less secure and much more troublesome and much less flexible than data centers and on-prem.' We thought we would talk a little bit about what are the expectations that people have when they are dealing with cloud, and how does tech debt feed into that? Did I capture that right, Chris?

Chris Swan: [00:01:30] I think so. And I pick up immediately on the cloud being misunderstood. The cloud has been misunderstood because it has been deliberately misrepresented by the cloud service providers. If people only use the cloud for what it is meant for, that would not have driven the surge in revenue that's taken place over the last decade and a half or whatever it's been. They had their reasons. But I think we can have a conversation now to start cutting through that and understanding the respective trade-offs between cloud and on-prem, and also where people are starting with this stuff.

Nick Selby: [00:02:00] Yeah, I agree with you. A lot of it was just in how the cloud was marketing itself. In the beginning we saw lots of arguments about what's safer. 'No, I'm not going to do that,' said Fortune 500 CEOs, 'that seems too risky.' And all the pundits were saying, 'No, you've got to keep control of things.' Over time, it reversed. By 2013, 2014, it was, 'Oh, this is safe because it's in the cloud.' 'We don't want to manage that on-prem because we don't have the resources,' which is a really successful marketing campaign, if you think about it. To your point about using the cloud for what it's meant for, I would think that with the skyrocketing revenues overall in cloud service providers, a healthy percentage of their top-line revenues comes from people who actually don't understand what they're doing. They're using default settings or they're doing a lift and shift, and recreating their data center environment in the cloud as opposed to taking advantage of cloud-native architectures, capacity, and capability in order to get what they need in a different way. They just figure, 'We'll fire our data center, cancel all those leases, and put it up in the cloud, and everything will be cheaper.' And it's not.

Chris Swan: [00:03:30] Absolutely not. First of all, I should probably state my view on the purpose of the cloud. I think the purpose of the cloud is very simple: to be able to move fast, with the ability to get services on demand. As a startup, you can literally show up with a credit card. You can subscribe to some free credits even at the beginning and get started on something, and to be able to immediately deliver is enormously valuable. You just mentioned lift and shift, and that's almost the opposite of that. That's all predicated on a much more complex calculus of the costs associated with running traditional infrastructure on-premises. For a time, the cloud was tracking Moore's Law in getting cheaper and cheaper. You could imagine an intersect point where you say, 'I'm spending a bundle running data centers and it's undifferentiated heavy lifting. Why don't I just hand that all off to somebody else who'll take care of it for me?' People had already been doing this for a very long time before the cloud came along, because we had outsourced service providers. I used to work for CSC, which was one of the good old names. There was EDS and whatever else, and they did massive contracts with companies to take over the running of their data centers. That very often got the label of 'your mess for less.'

Nick Selby: [00:05:00] Yeah.

Chris Swan: [00:05:30] One of the things I've seen happen in the past decade is that a lot of that infrastructure outsourcing has moved from a relationship with an IT services provider to a relationship with a cloud services provider. They've swallowed up a lot of that business and cloudified it. But has there been any value added? I would say that's probably questionable. We're now at a point where cloud has basically been around for the best part of two decades, and we can look at that first decade as the growing up period. There were lots of issues around security, scalability, data location, and other things people cared about that got taken care of in that first decade. Another thing that marked out that first decade was that everything kept getting cheaper.

Nick Selby: Yes.

Chris Swan: [00:06:30] If we think about the initial launch of EC2, it was a pretty rubbish VM, but it was instantly available and only $0.10 an hour. That was actually quite pricey for what it was at the time, but it was also compelling because if you were just getting started, $0.10 an hour was an easy entry price, and that $0.10 came down really rapidly. The equivalent or even better capability was an order of magnitude cheaper. We could extrapolate that cloud was going to keep getting cheaper, but what we've learned in the second decade is that it hasn't.

Nick Selby: Yeah.

Chris Swan: [00:07:00] Arguably this is now following Cory Doctorow's enshittification cycle. First of all, there's a surplus of value delivered to the customer. That was very visibly happening in that first decade, and now everything is being taken back to the provider.

Nick Selby: [00:07:30] But if we stick on the cost for a second, in 2013, I set up a company where we had to make investments of about $1.1 million to get what we needed. This February, we set up another company with about the same number of employees and about the same mission. Including MacBook Pros for everyone, it was about $55,000 to get started. There are really compelling cost arguments that can still be made without devolving into the old conversation about CapEx and OpEx. But you're absolutely right: it's less now about the cost to get in, and more about what you do once you're there. People get in and get really excited, but then they see those costs zooming up at a jaunty clip. The natural executive conclusion is, 'Wow, the cloud really is expensive and terrible.' They're not wrong, but they could have a completely different experience had they been managing what they had a little bit differently.

Chris Swan: [00:08:30] I remember early on doing some calculations of cloud versus on-prem for the organization I was working for at the time, and we had a pretty massive data center footprint. What did we learn from that? IT infrastructure is expensive, but we were running it at substantially less than what the cloud could offer for similar capacity. I think some of that along the way has fallen prey to arguments that there are hidden costs you didn't take into account.

Nick Selby: Yes.

Chris Swan: [00:09:00] Or they promised discounts. Those discounts were supposed to make sure that the cloud is going to be cheaper than your on-prem. What we then see of late is that there has definitely been cloud repatriation happening.

Nick Selby: Yes.

Chris Swan: [00:09:30] Organizations are realizing those cloud bills are much more than they bargained for and saying, 'Let's take some of this back.' I think some of that has actually been done in a pretty thoughtful way as well. If we do an energy equivalent here, most organizations are going to have what we could refer to as a base load.

Nick Selby: Yeah.

Chris Swan: [00:10:00] In energy, you might want that base load to be nuclear or something like that, and then there are going to be spiky loads on top of that. Organizations are looking at it and saying they can run that base load for less on-prem, especially if they invest in cloudy-ish modern infrastructure. Whether that's hyperconverged infrastructure with VMware, or something like Oxide and their rack-scale cloud units, there are plenty of good options now to have an infrastructure-as-a-service-like experience within the context of a private data center. Once you've got that base load in, you can look at the peaky bits and say that's the stuff that belongs in the cloud, because it fits the on-demand model.

Nick Selby: [00:11:00] On the other hand, the reason you and I decided to do this episode was because of two comments we heard. One was this idea of the base load. I talked to a CFO whose cost to do the same general thing in the cloud was 14 times higher than in his data center per unit, and it really was. But his financial operations lead said he could cut that in half tomorrow by rebalancing workloads. People just run servers at 3% capacity and others at 97% capacity, and they haven't optimized to make sure costs come down. There is a sense that the core is the core, but it isn't, not with the way you set this up, commit to it, architect, and plan for it as a business. I get the feeling people are still planning based on marketing: just put it in the cloud and it will be fine. Which is music to the ears of Amazon, GCP, and Azure. That was the first comment. The other comment was about margins. People say, 'Look at the margins we get,' but they're not comparing apples to apples. They point to data center margins being extremely high, but they weren't doing any of the fancy AI workloads that they did in the cloud. They couldn't, because none of those data centers have GPUs or the kind of hardware they would need. So it isn't an apples-to-apples comparison.

Chris Swan: [00:12:30] Yeah. And that sparks a couple of thoughts. Especially when it comes to GPUs, the picture for the last couple of years has been the hyperscalers making enormous investments in building out capacity. Being first in line allowed them to get delivery. There are certain classes of GPU where, in practice, it doesn't matter what your budget is, you can't get them. If you want Blackwell or whatever is the latest and greatest, you essentially have to go to a hyperscaler, because no amount of money will buy them for your own data center. Even if you could buy them for your own data center, you then run into traditional racking, stacking, caring, and feeding, which can be a pricey endeavor.

Nick Selby: Yes.

Chris Swan: [00:13:30] I think the GPUs are also interesting because we're no longer in the business of trying to lash these systems together yourselves. They come prepackaged as a rack-scale deliverable. With all of the interconnect and everything else figured out, optimized, and not having to be designed and implemented on a case-by-case basis, that has leveled the playing field. But I also think this argument that came in the tweet—that on-prem is always going to beat cloud on economics—is absolutely untrue at the entry level. There is a very high bar of needing to 'be this tall to ride.' I live this every day. For the last few years, we have not gotten to the stage yet where we could buy even a single rack-scale unit and drop it into a colocation facility.

Nick Selby: Do we save a lot of money there?

Chris Swan: [00:14:30] Your cloud bill needs to be in the order of millions a year. Before this becomes a relevant conversation. That implies a certain scale of organization.

Nick Selby: [00:15:00] It does. But the funny thing is that even when your cloud bill is in the millions of dollars a year, there are so many tools out there. Wiz is so popular, and there are other things like Gomboc. I mentioned Gomboc because we had Ian on in the first season of this podcast. That's his company now. He spent time at AWS and realized that doing the architecture, usage, and configuration is the biggest challenge to getting the cost savings and the value you want. The fact that these industries exist means people aren't doing the hard thinking; they're still looking for the easy button. Anyway, that's my theory.

Chris Swan: [00:15:30] You touch upon an argument I've heard. Organizations have displaced their 'undifferentiated heavy lifting' with 'undifferentiated heavy clouding.' The admin aspects of this don't just happen for free. There might be hidden costs in running your own infrastructure, but there are also hidden costs in adopting cloud services. Cloud services don't just run themselves, appear from nowhere, and conform to best practice guides for architecture. There are many things that need to be arranged around logging, observability, auditability, and compliance that need to be designed, rolled out, and operated on a day-to-day basis. That is often where the eye-wateringly expensive, premium services from cloud providers come into play. People start saying, 'Whoa, how much? I thought we were on the hook for X, and it turns out we are actually spending 4X.' What are we doing with all of these logs, how much are we retaining, and how much are they charging us for that?

Nick Selby: [00:17:00] We have some time left to talk about the difference between a blind lift and shift, and planning for efficiency. You've had your fast-cheap-good argument here. Just because it isn't cheap, but it is fast and good, doesn't mean it's not cheaper. There are ways to make it cheaper than it would be otherwise. But then you open up that bill one morning and see that you probably shouldn't have done what you did last month, retroactively.

Chris Swan: [00:18:00] I've heard this argument from people like Adrian Cockcroft in the context of his time at Netflix. They thoroughly understood that the purpose of the cloud was to enable the organization to move fast. They were pivoted around that notion of how engineering should work. They realized that if they had been going slower, there would have been costs accrued to going slower. On that basis, it turns out the cloud is not just better and faster, but also overall cheaper. That's a sound argument for that organization at that point in time. But it doesn't necessarily extrapolate to all other organizations, especially given that very few have accomplished the leverage with their cloud service provider that Netflix was able to do, because Netflix was so early, visible, and influential in that debate.

Nick Selby: Macy's will always pay less per square foot than your mom-and-pop shop in the local shopping mall, just because they're the anchor tenant and they're there to bring other people in. That's a different set of economics they're dealing with.

Chris Swan: [00:19:00] Absolutely. With this better, faster, cheaper trade-off, A lot of cloud was sold on the basis of being cheaper rather than faster, and I'm putting 'better' out there now as assumed. You mentioned earlier cloud-native architectures. It's funny how that term has come to represent two similar but entirely different things. In the red corner, we have actual cloud services like EC2 or Lambda. In the blue corner, we have Kubernetes. So we've ended up with a bunch of people running Kubernetes in the cloud, but also a bunch of people running Kubernetes on-premises. That has enabled people to take on workload optimization and capacity balancing. They've moved to using a platform and got themselves a platform engineering team, and they're maybe even doing some team topologies work. Kubernetes is one of those things that has made workloads somewhat portable from a public cloud environment to on-premises. It enabled this private cloud thing to come true in a way that hadn't happened so comprehensively with the more VM-based approach to infrastructure as a service, whether public or private.

Nick Selby: So what happened to the stuff that didn't make it onto Kubernetes?

Chris Swan: [00:21:00] Well, that brings us back to the 'your mess for less' type of thing, which was going on before the cloud and has been scooped up by the clouds. I think that's partly why we're here on the Tech Debt Burndown: the problem with your mess for less is it's still a mess, and there are all sorts of horrors lurking there. Typically, not much has been achieved from a cost-saving perspective by moving your mess from your own data center to one managed by a third party. We can extrapolate that precious little has been accomplished by moving your mess to a cloud service provider doing a lift and shift. There might have been a little consideration given to VM sizing and workload profiles as that has taken place, but in terms of the cost of ownership of those applications, the features of the mess are still there.

Nick Selby: [00:22:00] Yeah, that was where I was going. It's indiscriminate migration from one thing to another. I've got this terribly functioning thing over here, but it's cheap because it's here. Then I'm going to put it into the cloud and expect it to somehow magically work. That was what I meant at the beginning: 'Here's my AWS password, I've got agility now.' But you don't; you've got a new place to run the same stuff. If you don't take care, your bad decisions and tech debt will follow you into whatever platform you're on. I said at RSA a few years ago that when you make a mistake in the cloud, you are stupid at cloud speed, but you will get to the bottom of what you've done wrong very quickly.

Chris Swan: [00:22:30] What we see is a repetition of the fables of the past. When managed service providers were taking on the mess and doing deals for 'your mess for less,' that was often predicated on being able to transform the mess into something less messy and run it at a lower cost.

Nick Selby: Exactly.

Chris Swan: [00:23:00] And deliver savings based upon that. A lot of the time that simply didn't happen. We've seen a repetition of that with lift and shift, where there are desires and notions of, 'We're going to lift and shift now and transform later.'

Nick Selby: It's always easier to do it later after you've finished. Yeah, that's what we always recommend.

Chris Swan: [00:23:30] This elite team of ninjas deployed as solution architects to take care of your cloud migration—lift and shift being a big chunk of that. Once they're done with the lift and shift, they are supposedly going to be available to proceed with the transformation.

Nick Selby: Yeah.

Chris Swan: [00:24:00] How many of those have actually happened? I would say a precious few that I've seen. I think there is a 'sands of time' thing here where new applications come along and reside on new platforms. Old applications sometimes eventually wither on the vine and die out, or are replaced by new applications or services. If people are consuming SaaS, there's still an awful lot of legacy, which is often core tech sitting there like a psychopath running the business without necessarily needing much messing around with it.

Nick Selby: Right.

Chris Swan: [00:24:30] The costs associated with messing around with it for the sake of doing a transformation can be quite extreme. That's another reason why it often hasn't happened: there was a business case in favor of the cloud service provider to do the lift and shift, but there isn't a business case for the transformation.

Nick Selby: [00:25:00] You've done that. You're in the cloud. What is the good behavior we're trying to encourage? I've seen situations where something was poorly deployed, or badly imagined and envisioned. You look at all the problems you'd have in redoing it, and oftentimes we end up rebuilding it and then shifting over, running A/B for a while. In the worst cases, I've seen people fall for the siren song of, 'Google Cloud defaults are better and more secure than AWS, so let's rebuild it over there.' They do it with the same lack of competence they had with AWS. Not only will it not work, but all the problems will be different, so they don't even benefit from the expertise they gained from why it was bad on AWS. What's the best way to approach this? Is it to rebuild next to each other like the fishing bridges in Florida, where once you're done building the new bridge, you redirect the traffic and turn the old one into a fishing bridge? What do you do?

Chris Swan: [00:26:00] I think you've touched upon security, and that's going to need another episode.

Nick Selby: Okay.

Chris Swan: You're also touching upon the strangler pattern: creating new functionality using microservices and then ultimately strangling off the old functionality. That's a good pattern for when we are trying to modernize things and there is a good business case to do that.

Nick Selby: [00:26:30] That's fair enough. We will think about doing a second episode on this. This has been the Tech Debt Burndown podcast. I'm Nick Selby.

Chris Swan: And I'm Chris Swan.

Nick Selby: Thanks for joining us.
