# Market Intelligence Skill Pair: market-corpus + market-lens

This is an overview of a two-skill system Travis built for GTM and market research, mentioned during the workshop's "deep end" segment. It is the most complete worked example of the patterns in [dynamic-workflows.md](dynamic-workflows.md): agent swarms, barriers, and anti-slop verification, assembled into one repeatable research machine.

## What it does

Given a market question ("who are the serious players in X, and how do they sell?"), the system produces a verified company corpus and then runs analytical "lenses" over it: commercial model, who they sell to, positioning, and so on. The output is grounded market intelligence you can put in front of a client, not a confident-sounding essay.

## The architecture, conceptually

**Two skills, two jobs.**

- **market-corpus** builds the evidence base: a roster of companies, then a per-company evidence file gathered by fan-out collector agents working in small batches.
- **market-lens** runs analysis over an existing corpus. Lenses are cheap to rerun; the corpus is the expensive part. Separating them means one research investment supports many analyses.

**Human-approved gates (barriers).** The pipeline stops at four gates: roster, corpus, descriptive findings, synthesis. The synthesis gate is hard-blocked until the descriptive stage is approved. Why: the most expensive failure mode in market research is synthesizing from a bad roster or thin evidence. A wrong premise poisons everything downstream, so the human checkpoints sit early, where errors compound.

**Confidence labels and evidence files.** Every claim carries a label: verified, single-source, or inferred. Each company gets its own evidence file with compile dates, and anything older than 30 days gets flagged as stale. No naked assertions.

**Anti-slop rule: one editorial author.** Collection fans out to agent swarms, but each lens analysis is written by a single agent, never stitched together from a swarm. Multi-agent prose averages out into mush. Swarms gather, one author writes.

**Pressure-tested behavior.** The skills were tested adversarially: a baseline agent without them fabricated rosters and figures from memory and synthesized prematurely. With the skills installed, the agent refused memory-based claims, ran the gates, and held the synthesis gate even under deadline and authority pressure, offering a clearly-labeled partial brief instead.

## Why it exists

A premature synthesis once forced a full positioning rework. The skill pair encodes that lesson reusably: the discipline lives in the system, not in remembering to be careful.

## The takeaway you can use tomorrow

Even without these specific skills, steal the shape: separate evidence-gathering from analysis, put human gates where errors compound, label confidence on every claim, and never let a swarm write your final prose.

**Full skill source: ask Travis.** [linkedin.com/in/travcjohnson](https://www.linkedin.com/in/travcjohnson)
