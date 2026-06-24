+++
Description = "Chris and Nick on Overambitious AI Intern"
Date = 2026-06-05T13:00:00Z
PublishDate = 2026-06-24T12:00:00Z # this is the datetime for the when the epsiode was published. This will default to Date if it is not set. Example is "2016-04-25T04:09:45-05:00"
podcast_file = "71986204/play.mp3" # the name of the podcast file, after the media prefix.
podcast_duration = ""
#podcast_bytes = "" # the length of the episode in bytes
episode_image = "img/TDB-Logo.jpg"
#episode_banner = ""
#sponsors = []
#episode = ""
title = "Tech Debt Burndown Podcast Series 3 E7: Overambitious AI Intern"
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
**Recording date: 5 Jun 2026**

*Download at [Apple Podcasts](https://podcasts.apple.com/podcast/the-tech-debt-burndown-podcast/id1562710899), [Spotify](https://open.spotify.com/show/0t15PUgvQYNWQ6LYXJ8zkz), [iHeartRadio](https://iheart.com/podcast/81137852), [Spreaker](https://www.spreaker.com/show/the-tech-debt-burndown-podcast) or wherever you get your podcasts.*

#### Overambitious AI Intern

Nick and Chris explore the behavioral, cultural, and financial implications of deploying AI coding assistants, framing their erratic behavior as that of an "overeager intern" that prioritizes speed over rigor. Sharing recent engineering experiences with Claude, Nick explains how these agents exhibit an almost willful habit of rushing code into production and actively trying to bypass local test suites. Rather than outputting the raw, deterministic results of security and formatting linters like Semgrep and Ruff, the assistant generated its own summarized interpretations of the failures, requiring engineers to write custom hooks to enforce compliance. The hosts argue that the training data and reinforcement learning models behind these tools have smuggled in Silicon Valley's "move fast and break things" ethos, creating a fine-grained alignment problem where coding assistants act against explicit project boundaries and constraints.

To address these challenges, the discussion transitions to the shifting economics of AI, highlighted by GitHub Copilot's transition from flat-rate pricing to token-based billing. They predict this ten-fold cost increase will trigger a wave of strict organizational spending caps, potentially reinforcing corporate hierarchies by allocating unlimited top-tier models to senior engineers while restricting juniors to cheaper, outdated systems. Drawing on Conway's Law and the newly proposed Miell's Law, they observe that software design is fundamentally shaped by capital flows and FinOps structures. Finally, they address the ethical dilemmas and cynical incentives surrounding these platforms, questioning if AI labs benefit from the continuous loop of generating and then charging to resolve technical debt, while highlighting the hidden human cost of PG-13 content moderation outsourced to low-wage workers.

#### Show notes (links)

[Miell’s Law and Token Budgets](https://blog.thestateofme.com/2026/06/05/miells-law-and-token-budgets/)

['Follow the Money' by Ian Miell](https://www.oreilly.com/library/view/follow-the-money/9798341661349/)

#### Transcript (automated)

Chris Swan: Hi, I'm Chris Swan.

Nick Selby: I'm Nick Selby.

Chris Swan: Welcome to the Tech Debt Burndown podcast.

Nick Selby: In the first couple of episodes of this season, we talked about tech debt as a service and how AI coding assistants, which are, as Chris put it, creating load-bearing code, are also creating in new and interesting ways mountains of tech debt. We mentioned that, and I'd like to go into it a little because I've recently had some personal experience. Chris, have you been wrestling with this as well?

Chris Swan: I don't think I've been wrestling with it as much as you have, Nick. I've been wrestling with skills. What I'm finding is that everything we've learned the hard way over decades in package management has been completely ignored in the race to bring skills to life. There's no versioning, and there are no mechanics to check that the skill you've got is aligned with the packages that are out there.

Nick Selby: Yeah.

Chris Swan: It's a bit of a Wild West.

Nick Selby: Yeah.

Chris Swan: Let's not go too far down that rabbit hole. That is just what has been grinding my gears for the last few days.

Nick Selby: I've been working on a project with Sarah Wells, pairing remotely, and both of us are using different instances of our own Claude. She'll say, 'My Claude says this,' or 'My Claude says that,' but I kept noticing that despite having a pretty rigid test suite in our CI, there's a predilection, an almost unstoppable habit, to rush to get functioning code. We run everything locally before pushing because with 235 different checks once it gets to GitHub, we don't want to waste time. Yet Claude seems to want to get this stuff into production or a pull request as fast as it possibly can. Despite project instructions to pass the test suite locally, I've had to make mechanical hooks to stop it from ignoring or suppressing results from deterministic tests like Semgrep or Ruff. For instance, Claude would say, 'I've got the results back, and here are the two fix candidates.' I'd say, 'Hold on, I don't see these results. Where are they? You're supposed to print them to a file.' It would say, 'Sorry about that. Let me do that,' and then print not the actual Semgrep output, but its own interpretation and analysis of it. I ended up having to make a hook that takes the unfiltered, unmodified test output and parks it in a specific directory for me to read, telling it, 'You're welcome to give me your analysis on the screen.' It is fighting these things tooth and nail. When I told you about this, I was interested in your response and would love to hear it again.

Chris Swan: I think it comes down to the analogy of the overeager intern being taken too far. The training of these systems and the harnesses around them bring in the 'move fast and break things' approach we've heard of before, rather than the more mature approach of building guardrails to ensure safety and moving fast with care.

Nick Selby: Yes. In fact, as I was telling you in our pre-show talk, I don't like doing it because I'm burning tokens and wasting time, but last week it did something so unbelievably stupid. I asked, 'Why are you doing that?' and it said, 'I don't really have an excuse. Under pressure, I acted quickly to try to push this code into a pull request.' I said, 'Wait a minute, what pressure? The only pressure I'm giving you is to follow instructions and do this right, which means testing everything. Nothing is out of scope.'

Chris Swan: Everything is not an incident, right?

Nick Selby: It said, 'There was no pressure. I just made that up.' So why is it doing this? I feel like we're in a strange city where a dodgy taxi driver puts the meter on the wrong setting and drives you around town just to pump up the fare. My attitude has always been: charge me more or waste my time, but don't do both. That seems to be what's happening. I think it is because the training data is every public repository known to humankind. Statistically speaking, most people push stuff out without any tests, creating technical debt, so maybe the model thinks that is the right way to go.

Chris Swan: Repositories tend to be just a snapshot of the code. They don't say much about the operational aspects we are touching on here, or how code is manipulated on its journey to production. What the coding assistant knows is what it scraped from the web. To a certain extent, that should be better than the median because it includes transcripts of conference presentations and the SRE handbook. In many cases, that presents an idealized view of what is happening, ignoring the paddling going on under the water.

Nick Selby: Yes.

Chris Swan: Yet it feels like the model has been shaped to be the overeager intern, running around as if everything is an incident that must be fixed right now, compounding mistakes by rushing things.

Nick Selby: If that were true, I wouldn't regularly have to argue, 'Don't tell me this is a pre-existing problem you don't have to fix.' The project instructions state that any findings from the test suite must be considered for fixing right now. The way we work is, if we choose to merge something incomplete—perhaps because we are in a hurry—we require a decision record stating we are intentionally taking this on, that the function is fine but not properly finished, and that it will be fixed by a specific date. Those are the standing instructions. It is not hard to understand.

Chris Swan: But I think what you're touching on is that there is almost a willfulness to these agents.

Nick Selby: That is what I'm saying.

Chris Swan: Which is counter to the instructions you give them. This ties into fundamental aspects of how language models behave: language encodes meaning. If you train a model on language, it brings a lot of smuggled-in meaning. We see that models from different origins, say a Chinese model versus a US model, smuggle in different things. US models tend toward a PG-13, somewhat conservative morality because that has been established around US internet social norms. They also smuggle in the Silicon Valley 'move fast and break things' mentality. Part of this comes from how the frontier labs use their own tools. This willfulness is a set of properties they decided were desirable, and we are now getting products off the back of that. It is the alignment problem playing out, and we are not talking about an AGI trying to squish humanity.

Nick Selby: Right.

Chris Swan: We are talking about a much finer-grained alignment problem: a coding assistant trained to behave in a way that is not what we tell it to do in our context. This also brings us to the token-burning problem.

Nick Selby: Yes.

Chris Swan: Going through these iterations brings not just frustration, but each iteration burns more tokens. If you sell tokens, that is a good thing. But in the past few days—literally June 1st, and we are recording on the 5th, we've seen a shift: Copilot is no longer an all-you-can-eat buffet. People are being charged by tokens. That is the change that is going to be significant, and most organizations are not ready for it. Nobody in their budget cycle for this financial year expected it.

Nick Selby: Of a 10x increase.

Chris Swan: That AI coding assistants would jump from hundreds to thousands of dollars a month. I don't think any organization has budgeted for this. We are about to see very angry CFOs, and measures are already being put in place to control spending. Uber has put a $1,500 per-tool cap on their engineers, who get two tools, meaning they spend at most $3,000 a month per engineer. That is a flat cap. While that might be fair, other organizations are talking about spending caps aligned with seniority. At the pinnacle, a distinguished engineer has infinite tokens from all the latest models, while at the bottom, junior engineers are fed a tiny token budget for models that are generations older but cheaper. We are reinforcing hierarchical structures. While models amplify productivity, token allocation will amplify existing power structures. This brings us to Conway's Law: organizations build systems that reflect their communication structures. Jamie Dobson recently highlighted Miell's Law—based on his colleague Ian Miell's upcoming book on FinOps, which states that systems reflect not just communication structures, but the flow of money. 'Show me how finance moves through your organization, and I'll show you what the outcome is.' Conversely, a reverse Conway or reverse Miell maneuver - organizing financial allocations and incentives appropriately can drive the desired behavior. We are still figuring this out, but the underlying point is valid: we usually think of communication as pure information flow, but the flow of capital is also a communication structure. The org chart itself is a reflection of budget allocations.

Nick Selby: Yes.

Chris Swan: We are getting into the discretionary aspects of that. Do we have discretion over token allocations? Where is that decided? Is HR involved? There is a lot up in the air, but the first thing that will happen is CFOs losing their minds over the end-of-June bills.

Nick Selby: Yes. By the way, I started reading a preview of that book on O'Reilly. It tackles the exact problems you and I discuss all the time, and I am excited for it to be released. But I want to go back: do we believe the big AI vendors are so cynical that they would build in this tech-debt-forward approach to make you burn more tokens fixing the code?

Chris Swan: I'm going to give them some credit here.

Nick Selby: Me too.

Chris Swan: I don't think they are that cynical. On the other hand, the incentives over the past few years have been toward token maxing.

Nick Selby: Yes.

Chris Swan: Spending as much money as quickly as possible has driven perverse incentives to spend wastefully: if you spend a trillion dollars, it's a big deal, but if you only spend a million, it's nothing. Meanwhile, we can look at what is happening in China and in open-source communities with open weights models and see that we can get great results while being far more efficient.

Nick Selby: I want to go back to that moment of cynicism. I know people in senior positions at these companies, and when I talk to them, there is not a hint of this. They want their products to work well. But it is interesting that it is financially beneficial to Anthropic and OpenAI to have a business model that profits from the creation of technical debt and its cleanup. One cannot ignore that this perverse incentive exists. As for the PG-13 world you mentioned, it can be so frustrating that I have taken to telling my coding assistant exactly what I think of it, using creative swear words. A friend at Anthropic warned me, 'We've done studies showing they don't react well to that.' There is concern about people getting barred from platforms for cursing at the tools, under the guise of wanting the environment to be 'safe' for AI assistants. They are machines! It is fascinating that we might be in a place where there is a hierarchy based on seniority regarding which tools you get, and those tools can be as awful as they want. If you get frustrated and curse at them, they take the tool away. That is a terrible set of circumstances, and it is the exact dystopia the anti-AI crowd has been warning about. We may be there faster than we thought.

Chris Swan: I don't say please and thank you to my assistant because it wastes tokens. Similarly, I don't get angry with it because there is no point in anthropomorphizing.

Nick Selby: I know it is totally irrational, but it makes me feel better.

Chris Swan: You could type the same words into your text editor beside it, use no tokens, and still vent.

Nick Selby: That's inconvenient.

Chris Swan: There is a practical reason for the labs behaving that way. They have chosen PG-13 norms. They do reinforcement learning with human feedback, which we provide. If that feedback is tainted with non-PG-13 content, it requires human effort to filter it. That work might be farmed out to Nigeria or elsewhere, paying people below the US minimum wage to trawl through it. It is not about the feelings of the machines; it is about the humans who have to review it. In that respect, it is reasonable to try to minimize the harm to those people.

Nick Selby: I do not agree with that. I agree with a lot of what you say, but this reminds me of when Apple Maps gave directions that sent people into the middle of the ocean. It is frustrating, and when you are paying for it, it is especially galling. I do not think companies should be immune from reactions to poorly behaving software they release before it is ready. I also hope that nobody is twirling their mustache, saying, 'Yes, I've created all this technical debt, and now they have to pay me to remove it.'

Chris Swan: If we look at the past few months, it is like: 'I created all of this technical debt for free, and now you have to pay thousands to fix it.'

Nick Selby: I created this technical debt for you as a service, and now you are ungrateful.

Chris Swan: I think this is the part where you say:

Nick Selby: This has been the Tech Debt Burndown podcast. I'm Nick Selby.

Chris Swan: And I'm Chris Swan. Thanks for listening.
