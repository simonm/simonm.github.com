---
title: "Darmok, Brown M&Ms, and the Bandwidth of Meaning"
date: 2026-07-17
description: "Shared concepts are the highest-bandwidth channel between two minds, and the easiest place to agree on nothing. What that means now that one of the minds is a language model."
strand: "Thinking Aloud"
topic: "Communication"
draft: false
coda: "The position I keep: shared concepts are the highest-bandwidth channel between minds and the easiest place to agree on nothing, and which of the two you get turns on trust. That reframes [Right Finding, Wrong Fix](/writing/right-finding-wrong-fix/) and [Compliance as an Inherited Property](/writing/compliance-as-an-inherited-property/) as the same question in software that this is in language: when do you trust a component you didn't verify, and when do you make it spell itself out? Where I'd go next is the case this piece only gestures at: an AI is the awkward middle, fluent enough to earn trust it hasn't proven, and 'show your working' helps only so far as the working is something you can re-run rather than only read."
context:
  written: "July 2026"
  moment: "Talking to AI models had become an ordinary daily act, and their fluency with metaphor and allusion was starting to feel unremarkable. Almost nobody was asking whether the concept they sent was the concept the model received, or whether two different models would have received it the same way."
  standing: "This piece started from an idea I was fairly sure was mine: that Darmok and the brown M&M explain how meaning compresses between minds. It wasn't mine. Checking the prior art turned up a research paper and a stack of essays already there, and the collision is what pushed the piece from the metaphor to the hazard underneath it. A good deal of the thinking was worked out in dialogue with an AI, which is either fitting or funny, or both."
---

Van Halen, brown M&Ms, 1980s.

If you know the story, I don't need to tell it. Three words and a decade just handed you the whole thing: the clause in the contract, the reason it wasn't pettiness, the test hiding inside the sweets. You rebuilt all of it from almost nothing, because you and I happen to share the reference. That leap, from a fragment to the full picture, is the entire subject of this piece.

If you don't, here it is.

{{< aside label="Never heard it?" >}}
Van Halen's touring contract buried a clause in the technical rider, article 126: a bowl of M&Ms backstage, brown ones removed. It reads like a diva's tantrum. [It wasn't.](https://www.snopes.com/fact-check/brown-out/) The band toured one of the largest stages then on the road, with real structural and electrical demands, and the rider ran to pages of specifications a venue could get someone killed by skimming. The sweets were a canary. A brown M&M in the bowl meant nobody had read the contract line by line, and David Lee Roth called a full technical recheck. One strange instruction, standing in for a whole question: did you actually read this?
{{< /aside >}}

Either way, you now hold the same small story I do, and that is the point. Tell someone the brown-M&M test and they reconstruct the whole apparatus of it without you explaining a word. The phrase is a handle on a concept they already have.

Now the pure form of the same thing. In an old Star Trek episode, Picard meets a species whose entire language is allusion. They don't say "we should set our differences aside and face this together." They say "Darmok and Jalad at Tanagra," the names of two figures from their mythology who did exactly that. Every sentence is a pointer to a shared story. Picard understands none of it, not because the translator fails on grammar, but because he lacks the stories. The language is all handles and he holds none of the things they hang on.

I reached for Darmok to make this point, and I should tell you that so did a machine-translation research team, and a stack of essayists, and at least one post that may have crossed your own feed. When I found that out my first instinct was to cut it. My second and better instinct was to keep it and say so, because the fact that all of us independently reached for the same episode is the argument. We share a corpus. When you want to say "meaning lives in shared reference," the corpus hands you Darmok, the same way it hands everyone else Darmok. The metaphor is unoriginal for precisely the reason this piece is about.

The same property that makes a shared concept powerful is the one that makes it dangerous. It is the highest-bandwidth channel between two minds and the easiest place to agree on nothing, and what decides which of the two you get is whether the difference between your version and mine stays visible long enough for either of us to notice.

## A concept is an address, not a description

Here is the thing underneath both examples. A shared concept is not a description. It is an address. A pointer, if you are looking at this through a computer-science lens: a small thing that refers to a large structure held somewhere else.

Hand someone a rule, "remove the brown ones," and you have given them data, a single instruction to execute. Hand them a concept, "the brown-M&M test," and you have given them the address of a model they already hold, and they rebuild the whole structure at their end: the buried clause, the safety stakes, the test hidden inside the request. You sent three words. They reconstructed a paragraph. That ratio, small signal in and large structure out, is what compression is.

So the real capacity of the channel between two minds is not words per minute. It is the size of the shared library the words can point into. Two people who have read the same books, worked the same job, and sat through the same failures finish each other's sentences, not because they are quick but because almost everything they say is a handle on something both already hold. Bandwidth is shared corpus.

There is a measured version of this, and it is stranger than it sounds. Compare how fast the world's languages are actually spoken and a trade-off appears: information-dense languages get spoken slowly, sparse ones fast, and the product settles near a constant, [about 39 bits per second](https://www.science.org/doi/10.1126/sciadv.aaw2594), whether the words come fast, as in Spanish, or slow and dense, as in Mandarin. That is the ceiling on the raw speech channel, and a shared concept walks straight through it. When I say "Darmok and Jalad at Tanagra" I push a couple of hundred bits across the wire, but you rebuild a whole story from your own memory, thousands of bits you never received. The meaning transferred dwarfs the bits transmitted, because most of it was already in you, waiting for the address. That is the trick, and the ceiling is what makes it matter: shared culture is how humans say far more than the channel can carry.

It is also why some conversations feel like wading through wet sand. Two people with different libraries are both speaking in handles, and neither set of handles is attached to anything on the other side. From the inside it reads as the other person being slow, or stubborn, or wilfully missing the point. Usually they are not. The concepts are arriving with nothing to attach to, because the referents behind them were never shared. I once spent the better part of a year certain a colleague was disagreeing with me on purpose, being deliberately obtuse, refusing to see a point I was sure I had made plainly. The truth was quieter and more my fault: I was handing him compressed conclusions and assuming he could decompress them the way I did. He couldn't. Nobody had given us the same phrasebook.

## The failure nobody watches for

Now the part that should worry you. Compression is lossy, and the loss is invisible.

When I send you a concept and you reconstruct it, you don't rebuild my version. You rebuild yours. Most of the time the two are close enough that it doesn't matter. Sometimes they aren't, and here is the trap: nothing tells either of us. We both walk away certain we agreed, carrying two different conclusions out of the same handshake. Call it the confident misunderstanding: both parties sure, both satisfied, each holding a different thing.

You have felt this even without naming it. A team agrees to keep the design simple and ships two features built to different definitions of simple. Two people shake on staying high-level and find out a month later they meant opposite things by it. The word did its job, it passed smoothly between them, and that was exactly the problem. Speed of convergence is not evidence of shared meaning. Often it is the reverse: the more easily a concept goes down, the less anyone checks it.

## A second kind of mind

All of this is old, as old as language. What is new is that we have built a second kind of mind to have these conversations with, and it changes the arithmetic.

A large language model has read more of the shared corpus than any person alive, so it catches your allusions at a rate no human can. You can talk to it in dense reference, brown M&Ms, a half-remembered line from a play, a proverb worn smooth, and it will usually pick up the handle and hand you back the thing it hangs on. The fluency is real and it is seductive. It feels like the highest-bandwidth conversation you have ever had.

Run the concept back carefully, though, and you find the same lossy decompression, with a twist that makes it harder to catch. Ask a model what Frost's "The Road Not Taken" is about and the core comes back every time: a fork in a wood, a choice, the road less travelled. Push past that and it drifts, whether the poem is a straight hymn to taking that road or the sly joke it probably is, the two paths worn "really about the same," the whole thing a story the speaker means to tell later "with a sigh," pride or regret, nobody sure which. And it drifts differently on a different day, and differently again on a different model. Convergent at the core, divergent at the edges, and the edges are exactly where the meaning you actually needed tends to live.

The divergence isn't random, and it isn't only the model's fault. Different models are trained on different material and tuned by different hands, and those choices carry values. This is [measured, not speculative](https://alignment.anthropic.com/2025/stress-testing-model-specs/): put the same value-laden dilemma to frontier models from different labs and they prioritise differently, in patterns you can reproduce. The pressures that shape a model, its data and its alignment, leave a worldview behind, and the model reads your concepts through it. The mapping isn't even clean by company: some models from rival labs turn out to be near-twins, which only sharpens the point. It is the pressures, not the logo, that decide how "fairness" or "risk" or "freedom" gets rebuilt on the other end. Be clear about the claim. It isn't that one lab holds the right values and another the wrong ones. Every lab, Anthropic included, leaves a worldview in its models, and that worldview is doing quiet work each time you hand one a concept and trust it to reconstruct your version. There is no view from nowhere on the far end of a prompt.

Which means the thing most people assume, that a concept arrives the same way whichever model you ask, is not free. It is a property you have to check, and right now almost nobody does.

## The gap is the point

So far divergence has been the hazard. It is also the reason an exchange is worth having at all, and the clearest case I have of that started with an apology.

I was running two conversations with the same underlying model at once, on two machines, on two unrelated problems, and I kept fumbling one of them. What set the rest going was mundane:

{{< exchange >}}
**Me:** Sorry, I missed the approval button again, fourth time. If it helps, I'm half in another conversation with a sibling of yours on the other machine. I'll say hi from you.

**The other instance:** Say hi back, and good luck to them on whatever you're building.

**Me, relaying:** Hi back. We're getting a small team's project tracking honest: Epics that pass a customer-value test, Stories sized to a sprint. What are you working on?
{{< /exchange >}}

From that it went somewhere I hadn't planned. One conversation was helping that team at an industrial-security vendor. The other was designing an intake tool for a different vendor's internal innovation programme. By then each had built its own deep context, its own accumulated grip on its own problem, and I kept carrying messages between them.

Same model on both ends. In principle they had nothing to teach each other. In practice each brought the shape of its own problem to the other's, and something fell out that neither had reached alone. The intake side was treating its form as a gate: fill the fields correctly and you are through. The project-tracking side, working a different surface, had already hit the harder truth, that people follow the process correctly and still produce the wrong shape, and that the failure worth catching is the well-formed submission that is still not right. Handed across, that became a design line the intake side didn't have before: the form's job is to surface the conversation, not to gate it. A coaching step, not a checkpoint.

Two minds with identical context would have produced none of that. Perfect overlap has nothing to trade, the way a message telling you only what you already know carries no information. What made the relay generative was the gap: shared substrate enough to understand each other at once, different context enough to have something the other lacked. Bandwidth gets you understood. Difference gives you something worth understanding.

The same relay showed the hazard in the same breath. Both sides seized on one phrase for a bad submission, that it was engineering work wearing a customer-value coat, and the phrase carried them into quick agreement. Only later did it come out that the metaphor had smuggled in a claim neither had checked: a coat you put on is a disguise, deliberate, and the real problem was an honest blind spot with nothing deliberate in it. The relay that produced the good insight nearly closed on a confident misunderstanding, for the very reason it worked, two minds converging fast on a shared concept. What separated the two outcomes was friction. Where someone kept pushing, the concept got revised until it fit. Where it slid down clean, nobody checked.

Which is the whole of it. The difference between the exchange that teaches you something and the one that quietly misleads you is not how much the two of you have in common. It is whether anything made the gap visible before you both walked away satisfied.

## If you build with this

The practical shape is easy to state and easy to get wrong. Concepts are the right channel for the things where approximate shared meaning is fine, and often desirable: direction, taste, values, the general shape of what you are after. They are the wrong channel for anything where divergence is a defect. You do not specify a financial calculation, an access rule, or a data boundary by gesturing at a concept and trusting the model to rebuild your exact intent. For those you want the low-bandwidth, high-fidelity channel: an explicit contract, a schema, a type, a test. Something that cannot be decompressed two ways.

And if your system runs on more than one model, or more than one instance of the same one, do not assume they share a concept because they share a word. Pin the meanings that matter. Treat cross-model agreement as something to verify, not something you were handed.

## Where this stops

I should own what this piece has been doing. To argue that meaning rides on shared concepts, I have leaned the whole way on shared concepts: a rock band, a Star Trek episode, a misread poem, a coat. You understood each one because we share it, and I chose each one because you would. The essay is an ouroboros, the snake with its tail in its mouth, using the thing to explain the thing, and this sentence, naming it, is one more coil of the same snake. I don't think that weakens the argument. I think it is the argument, stood where you can see it.

What I am sure of is the shape. A channel between two minds is only as good as the difference you can still see across it, and shared fluency is the thing most likely to hide that difference. What I cannot give you is the vocabulary. We are missing the concepts we would need to describe what actually happens when a person and a machine understand each other, or fail to, at the speed these exchanges now run. That part hasn't been built, and I have stopped trying to force a conclusion that pretends otherwise.

What I can say is smaller, and I think true. The fluency is real, the failure is real, and both are running constantly, mostly unexamined, in every conversation people are now having with these systems. You can work with that. You don't have to settle what it means first. You only have to remember that a shared word was never a shared meaning, and now, on the other end of the line, it is a shared word with a stranger who has read everything and agrees with you slightly less than you think.
