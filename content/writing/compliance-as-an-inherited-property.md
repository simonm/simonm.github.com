---
title: "Compliance as an Inherited Property"
date: 2026-07-16
description: "Why enterprise AI governance should work like a type system, not an audit queue."
topic: "AI Governance"
strand: "Essay"
draft: false
coda: "What I carry forward: you scale trust by making the safe thing the default and saving human judgement for what's actually new. Cleverer review doesn't scale; inherited safety does. Where this meets its own limit: the certified-parts model assumes you can see what a thing is made of, and [Right Finding, Wrong Fix](/writing/right-finding-wrong-fix/) is what happens when you can't. Underneath both sits the question [Darmok, Brown M&Ms, and the Bandwidth of Meaning](/writing/darmok-bandwidth-of-meaning/) asks of language: how far can you trust a component whose meaning you never verified yourself? Next, the runtime rather than the review: what a governed platform owes builders so the blessed path stays the easy one."
context:
  written: "July 2026"
  moment: "Enterprises were a year deep into standing up AI governance functions, and most had just worked out that the binding constraint on adoption was the review queue, not model capability or budget. 'Agentic' was the word of the year, and teams were shipping agents faster than anyone could govern them."
  standing: "I was inside a large security vendor, building the kind of paved-road tooling this piece argues for, after watching a documentation tool get stopped by a scanner over an rm -rf in a man page."
---

The scanner stopped us because of an uninstall command.

We had built a small documentation-lookup tool for internal AI use at a global security vendor: a way for a language model to answer questions from official product documentation instead of guessing, and to ensure that everyone had the same chance equivalent (but not necessarily identical) answers from the LLM guided sessions. The reference material included a vendor's published, supported uninstall procedure, which, like ten thousand other uninstall procedures, contains `rm -rf`. The static security scanner in the review pipeline found the string, classified it as a critical finding, and the pull request stopped at InfoSec.

Nobody was going to run that command. It was documentation about the command, sitting in a text file, retrieved to answer the question "how do I remove this agent?" The tool was fine. The process could not tell reference material from executable intent, and a context-blind gate treated both the same.

I have come to think of this as a whole category: friction that looks like security but isn't. It is worth taking seriously, because in most large organisations it is now the binding constraint on AI adoption. Not model capability, not budget, not appetite. Review friction.

## The audit model was built for a different world

Most enterprise governance rests on an assumption so old it is invisible: new tools arrive occasionally, they are built by engineering teams, and therefore reviewing each one individually is affordable. A few submissions a quarter, each from people who know how to write a design document, each assessed by security, legal, and GRC in turn. Slow, but survivable.

AI breaks the assumption from both ends at once. Everyone can now build, so the volume of things needing review explodes. And what they build often contains a model, so each individual review is harder than it used to be, not easier. A sales engineer can produce a working internal tool in an afternoon. The review of that tool takes six weeks, if it finishes at all.

The failure sequence is predictable and I have watched it run. The queue grows. Time-to-approval stretches. Builders respond the way people always respond to a slow gate: some abandon the idea, and some route around the process entirely. The organisation ends up with shadow AI it cannot see and a governance function that, having tightened, now has less visibility than before. Meanwhile the same security, legal, and GRC questions get re-answered from scratch for every submission, because each idea arrives as a bespoke artefact requiring bespoke judgement.

Notice which ideas die in this system. Not the risky ones. The ones whose builders had the least patience. The selection pressure is exactly backwards.

There is a second problem hiding next to this one, which is that good internal tools do not travel across a large organisation even after they clear review. That distribution problem deserves its own discussion, and I will give it one separately. This piece is about the gate.

## Stop auditing artifacts. Start certifying parts.

The way out is an inversion. Instead of reviewing every finished thing, certify the parts things are made from. Build a set of pre-cleared building blocks: approved data-access patterns, approved credential handling, approved storage, approved templates and scaffolds. Then adopt one rule. Anything assembled entirely from certified parts is compliant by construction and requires no review. Human judgement is reserved for the one thing it is good at: data flows nobody has seen before.

Compliance stops being a verdict issued per artefact and becomes a property inherited from the components.

Software engineering has already run this experiment at industry scale, and the result is called Rust. Ask why Rust keeps taking ground from C in systems programming. It is not because Rust programmers are more careful people. The language, the compiler, and the toolchain removed whole classes of defect: buffer overflows caught by bounds checking, use-after-free and data races made inexpressible by the borrow checker at compile time. Decades of auditing C programs one at a time never achieved what one change of language achieved, because auditing scales with the number of programs and language design scales with the number of bug classes.

The mapping to governance is almost embarrassingly direct. Per-idea AI review is auditing C: expert humans reading every artefact, hunting for instances of known problem classes, forever. The certified-parts model is switching to Rust: the violation becomes something you cannot express using the blessed components, and expert attention concentrates on the small, explicitly marked residue. Rust even has a name for that residue. Code that must step outside the guarantees is wrapped in an `unsafe` block: rare, visible, and the only place trained eyes are required. A genuinely novel data flow is an `unsafe` block. Everything else should compile.

It is worth being precise about what this is not, because a related idea is circulating that looks similar and isn't. Several recent governance frameworks propose tiered approval: a menu of use cases sorted green, yellow, red, with the green tier auto-approved and the red tier fully reviewed. This is an improvement on the flat queue, and I do not want to argue against it. But it is still triage. Every idea is still assessed and sorted, one at a time, by someone. A faster queue is still a queue. The test that separates tiering from inheritance is simple: does an artefact assembled entirely from certified parts require zero review? If a human still glances at each one, you have an audit with better response times, and the response times will decay as volume grows, because queues do.

The inheritance model also makes a claim that sounds too convenient, so it should be stated plainly and defended: this is not a trade of security for speed. Review capacity is finite. Spent on a hundred assemblies of already-safe parts, it is smeared thin and bored. Concentrated on the handful of novel flows, it is thick and alert. The second arrangement catches more. Faster adoption and stronger control come out of the same design decision, which is the usual sign that the previous trade-off was an artefact of process rather than a law of nature.

## What the parts actually are

In practice the certified parts come in two layers, and the order matters.

_The first layer_ is authoring patterns: scaffolding, templates, linters, and preflight checks that let a builder produce an artefact that passes CI and security review the first time. The trick is to take the checklist the review pipeline already enforces and encode it into the generator, so the scaffold cannot emit the failure. The uninstall-command story resolves here. A scaffold that knows what reference material is, and packages it as data rather than as anything executable, produces artefacts the scanner has no reason to stop. You reverse-engineer the gate into the tool that writes the code.

_The second layer_ is runtime capability: shared services, secured once, that artefacts run on instead of each solving the same problems badly. A governed data-access layer, so nobody hand-rolls their own connection to sensitive systems. A credential broker, so secrets never live inside artefacts at all. Blessed storage, telemetry, and evaluation. Each service clears security review once, and every artefact built on it inherits the clearance.

One concrete example from the second layer, because abstract platform talk convinces nobody. Any company enabling generative AI eventually hits this problem: a model generates a small web application, a dashboard, a calculator, an interactive report, and an employee wants to share it with colleagues by link. You are now serving untrusted model-generated JavaScript to your own staff. Almost no organisation has named this problem, and the ad hoc answers (paste it into a personal cloud account, email the file around) are exactly the shadow paths governance exists to prevent. The paved answer is a render host built once, properly: single sign-on per user, ephemeral hosting by default, per-artefact origin isolation, a strict content security policy, a data-classification gate at publish time, and no outbound network access from the sandbox the artefact renders in. Anything it legitimately needs, it gets through the governed data-access layer rather than by calling out on its own. Built and cleared once. Inherited by every artefact after that.

I am currently building exactly this, with companion building blocks that ship default-enabled for my colleagues. The golden path is meant to be the lowest-friction way to do what people actually need, and so the quiet default.

## Four principles that keep it honest

The blessed path must be the easiest path. People route around friction, they always have, and a governance model that depends on them not doing so has already failed. Design for the bypass: reconcile drift, stay correct when someone edits things by hand, make the road smoother than the field beside it. The platform-engineering world calls this the paved road, and for once the borrowed phrase fits.

Harvest, don't invent. When the University of Sussex laid out its campus in the 1960s, the story goes that the architects left the grass bare, waited a year to see where people actually walked, and paved those lines. The same tale is told of a dozen campuses and documented at almost none, but the instinct is exactly right: you don't guess the route, you pave the desire path. Build the shared substrate from the demand your builders actually surface, not from a whiteboard guess. The certified parts catalogue is a product with users, and products invented without users rot.

Every shared service needs a named owner and a funding home. An orphaned credential broker is not a security control. It is a future incident with a login page.

Contain constraints, don't hide them. Where a real limit exists, data classification, egress, tenancy, surface it at authoring time, in the scaffold, where it reads as help. Discovered at review time, the same constraint reads as ambush, and ambushed builders become bypassing builders.

## What changes for the security team

Everything above could be misread as an argument for less security review. It is an argument for a different job. The security function moves from reviewer of everything to owner of the certified parts: a smaller surface, engineered deeply, instead of an endless queue skimmed shallowly. Review volume drops to the novel-flow residue, which is the work that actually requires senior judgement. The context-blind scanner moves off the critical path. And visibility increases rather than decreases, because the paved road is instrumented end to end while the shadow paths, having lost their reason to exist, empty out.

Security teams are the beneficiaries of this model, not its victims. The audit queue was never a position of strength. It was a position of exposure with a dashboard.

## Where to start

Start smaller than feels proportionate to the idea. Take the review checklist you already have and encode it into one scaffold, for one artefact type. Push one real artefact through the entire pipeline as the proving case, and treat every snag as a defect in the pipeline rather than in the artefact; that is how the uninstall-command class of failure gets found and fixed. Measure one number: the time from idea to reuse by a colleague. Days is the bar. Quarters is the disease.

Only after the first layer is producing artefacts that pass review on the first attempt is it worth arguing for shared runtime services, and by then you will not have to argue from theory. The demand the scaffolds surface is the business case, written by your own builders.

The measure of an AI governance programme is how little it needs to review while remaining in control. An audit queue measures its thoroughness by its own length. An inheritance model measures itself by how rarely anyone has to look, and by how much gets built, safely, while nobody does.
