---
title: "Three Abstraction Shifts in One Career"
date: 2026-07-20T09:00:00Z
description: "The web abstracted away distance, cloud abstracted away infrastructure, and AI is abstracting away implementation itself. The third one is different in kind, not just degree."
strand: "Essay"
topic: "Practice"
series: "Part one of two"
draft: false
coda: "The position I keep: as each layer gets absorbed, the work left over is classification rather than solution, deciding which problems belong to the machine and which stay human, and that judgement takes more than one discipline to make. That sits next to [The Botnet With One Member](/writing/the-botnet-with-one-member/), where the advantage also moved to the boundary rather than living in either system, and it asks the same question that [Compliance as an Inherited Property](/writing/compliance-as-an-inherited-property/) asks of a golden path: what should exist, and what should be allowed to reach it. The thread I can't tie off is whether the pattern holds this time at all. The first two shifts settled onto ground that eventually stopped moving. This one hasn't, and that is the argument of the second half, where I set about disagreeing with most of what I have just said."
context:
  written: "July 2026"
  moment: "Agentic AI had become an ordinary working tool rather than a novelty, and 'context engineering' had settled in as the dominant name for the discipline assembling around it. An industry of courses, certifications and pattern catalogues had built itself in roughly two years, on a substrate that was still changing every few months."
  standing: "Thirty years spent inside the three shifts this describes: a web development and hosting company in the late 1990s, a service provider and then Juniper Networks through the cloud years, and now a security vendor, where I won the company's inaugural MCP Hackathon with a system of fourteen agents. This is the first half of a two-part piece. The second half argues against it."
---

I remember the mass. Racks and racks of it. Cable management that was part engineering, part art form. Knowing which patch panel connected to which switch, which VLAN carried which traffic, how to trace a Layer 2 loop at 2am when the spanning tree had other ideas.

I was in the engineering team at a public-sector service provider running a full-mesh MPLS backbone across three thousand connected customer networks, and I built a good deal of what sat on top of it: the filtering proxy farms, the mass web hosting, the email.

That knowledge felt permanent. It was hard-won, deep, and valuable. And then it wasn't.

Cloud computing didn't make networking knowledge worthless. It made a specific _layer_ of networking knowledge unnecessary for most of the people who had spent years acquiring it. The problems didn't disappear - they moved behind an API. The question shifted from "how do I run this" to "how do I architect this." When was the last time you troubleshot a Layer 2 issue in AWS? That problem domain is broadly solved. Not because it stopped being complex, but because the complexity got abstracted into someone else's concern.

I've now watched this happen three times in a single career.

---

The first shift was the web, in the late 1990s. I joined a web development and hosting company when there were twelve of us and left a few years and two acquisitions later, when there were several hundred. It abstracted away physical distribution. Suddenly the interface was a browser, and the question moved from "how do I get this to people" to "what do I build." Entire industries reoriented around that single change.

You could see it in the plumbing if you were looking. The first Layer 7 switching I ever saw was an ArrowPoint box, making routing decisions on URLs and cookies rather than addresses, because what mattered had moved up a layer. Cisco bought them in 2000 for five point seven billion dollars.

I saw the second one arriving before I understood what I was looking at. In 2003 or 2004, at a converged-solutions company that was acquired while I worked there, a VMware pre-sales team demonstrated a running virtual machine moving from one physical host to another without going down. No outage, no reboot. The thing simply carried on somewhere else. I remember thinking it was remarkable. I did not think it was a notice of redundancy served on a large part of what I knew, which is roughly what it turned out to be.

This second shift was cloud, through the 2000s and 2010s. I joined Juniper Networks in 2006, the year EC2 launched, which seemed like nothing at the time. It abstracted away infrastructure. The interface became the API. A generation of engineers who had built their careers on knowing how to run things had to learn how to architect things instead. Some made the jump. Some moved sideways, some left the field entirely. The pattern I'm describing is what I saw work, not what inevitably happened.

The third is happening now. Large language models and AI agents are abstracting away implementation detail itself. The interface is natural language. The skill shift is from "how do I implement this" to "what should exist and why."

The first two shifts followed a predictable logic: a new platform replaced an old process, one for one. Cloud APIs did what rack engineers did, just at scale. But this third shift is different in kind, not just degree. AI agents don't substitute for an existing capability - they generate possibilities you wouldn't have explored alone. You're not delegating a known task to a reliable system. You're navigating a possibility space the tool itself is creating. That changes the cognitive relationship entirely.

---

I work in cybersecurity - at SentinelOne, previously at Venari Security, FireEye, Palo Alto Networks and Juniper Networks - and this domain has taught me to think about knowledge in a specific way. Security has always required triaging problems into categories: what's solved (signature-based detection, known CVE scanning), what's being solved (behavioural analysis, AI-generated phishing detection), and what nobody has cracked (novel attack chains, adversarial AI, the human factors that no model captures).

But my career hasn't just been security. It's been networking, software architecture, coding, and many years in pre-sales - sitting in the gaps between disciplines, translating between domains, understanding where one field's solved problem is another field's open question. That cross-domain perspective turns out to be where the most interesting work lives now.

There's almost a P=NP quality to it. In computer science, knowing whether a problem is efficiently solvable changes everything about how you approach it, and the classification is worth more than any individual attempt at a solution, because it tells you whether to attempt one at all. Nobody wants the brilliant heuristic for a problem that had a closed form sitting next to it, and nobody wants six months spent on something provably intractable.

The same holds with AI. The most valuable skill isn't solving problems, it's classifying them: which ones a model handles well, which ones it handles badly, and which ones it should be kept away from entirely.

That classification isn't a technical judgement. It needs the security implications, the architectural constraints, the business context and what the person actually needs, all at once, and no single discipline supplies all four. The intersections do. Which is why this work tends to fall to people who sat in the gaps rather than to the specialists at the centre of any one field.

The industry has settled on "context engineering" for one half of it: supplying a model with the right information, tools and memory at the right moment. That's the downstream question, and it's being worked on hard by people who are good at it. The upstream one, whether the model should be anywhere near the problem at all and which parts stay human, doesn't have a name, and I'm not going to give it one.

---

When I won the MCP Hackathon at S1 with IRIS - a reporting tool that orchestrates 14 AI agents for security analysis - it wasn't because I wrote better code. It was because I understood which parts of the problem the agents could handle and which parts needed human judgment. The architecture mattered more than the implementation.

The more useful thought came afterwards: IRIS shouldn't stand alone. It needs to be a component in larger workflows. So I added an MCP server and a Skill interface, making it composable. Then I added a knowledge base of common queries - not for humans to browse, but for other agents in the chain to choose from, based on what _they_ need to accomplish their own goals.

I was building tools for tools. Designing how agents think about what they need. And that recursive, meta-level design work - deciding which capabilities to expose, at what level of abstraction, for what kinds of downstream reasoning - is where I spend most of my time now. Not implementing. Deciding what should exist, and what should be allowed to reach it.

---

I see it playing out in teams too. BCG ran a field experiment with 244 consultants using AI tools. Twenty-seven percent became what the researchers called "Self-Automators" - they delegated everything to the AI and learned nothing. I've watched the opposite pattern too: people who use AI and get measurably sharper, because they maintain active engagement with what the tool is doing. The difference isn't intelligence or experience. It's whether you're using the tool to think harder or to stop thinking.

Each previous abstraction shift created kinds of work nobody had anticipated. The web was supposed to put brochures on screens and it produced social networks, search engines and the entire app economy. Cloud was supposed to move servers somewhere cheaper and it produced DevOps, SRE and platform engineering. The people who saw those possibilities early weren't necessarily the best technologists. They were the ones who could see across domain boundaries.

The person who knows _that_ you can connect three systems is becoming less valuable than the person who knows _whether_ you should, and what the second-order consequences will be. This work is to AI agents what urban planning was to the automobile. The car did more than speed up travel. It restructured cities. Someone had to think about where the city should grow, and the person building the road was not that person.

---

Three shifts. Same structural pattern, though the third one is harder and stranger than the first two. The boundary moves up, the old layer gets absorbed, and the space for new kinds of work opens up in ways nobody fully predicts.

Each time a layer gets absorbed it also reveals work that wasn't visible before. The most interesting problems I have now didn't exist five years ago, and the ones I'll have in five years are presumably invisible to me today, sitting in the gaps between domains.

I'm not sure the boundary I'm describing is permanent. AI systems are developing their own forms of evaluation and judgement, and what's hard today may not stay hard. That has been true at every shift. And at every one of them I was standing inside the layer that was about to be absorbed, reasonably confident that what I knew was the durable part.
