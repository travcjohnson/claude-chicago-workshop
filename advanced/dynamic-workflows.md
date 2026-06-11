# Dynamic Multi-Agent Workflows in Claude Code

One Claude session is a worker. Multiple coordinated sessions are a team. This guide covers the patterns that actually pay off, and the ones that just burn tokens.

The core primitive: Claude Code can spawn subagents. Each gets its own context window, does a scoped job, and returns a summary to the parent. Your main session stays clean while the heavy reading happens elsewhere.

## Pattern 1: Fan-out research

Use when you have several independent questions and the answers don't depend on each other.

```
Spawn 4 research agents in parallel:
  Agent 1: verify every claim on the pricing page against the live site
  Agent 2: find how competitors X, Y, Z describe this feature
  Agent 3: check our docs for anything that contradicts the new copy
  Agent 4: pull the exact launch dates and version numbers we cite
Each agent: return findings as claim → status (verified / corrected / not-found) → source.
```

Three rules that make fan-out work:

1. **Independent tasks only.** If agent B needs agent A's output, that's a pipeline (below), not a fan-out.
2. **Tight briefs.** Each agent gets one question, the file paths or URLs it needs, and the exact return format. Vague briefs produce vague essays.
3. **Demand structure back.** "Return claim / status / source" turns ten pages of agent prose into a table you can act on.

The deck for this workshop was fact-checked by an 8-agent fan-out fleet in one afternoon. Every claim came back verified, corrected, or flagged. That work is days of manual checking.

## Pattern 2: Adversarial verification

The agent that wrote something is the worst agent to check it. It will defend its own work, because the same context that produced the mistake will reproduce it.

So separate the roles:

```
Agent A (builder): write the migration / the report / the copy
Agent B (adversary): you did NOT write this. Find what's wrong with it.
  Try to construct failure cases. Check every factual claim against the
  source. Return only problems, with evidence.
```

The adversary gets a fresh context and an explicit mandate to break things. In practice this catches a different class of error than review-by-the-author: stale stats, plausible-but-wrong attributions, edge cases the builder rationalized away.

Cheap version: open a second Claude session, paste the output, and say "find three things wrong with this before I ship it." Worth it for anything public.

## Pattern 3: Pipelines vs barriers

Two ways to chain stages, and mixing them up is the classic failure.

**Pipeline:** output of stage 1 feeds stage 2 automatically. Research → draft → format. Use when each stage's output is easy to validate mechanically and an error won't compound badly.

**Barrier:** all work stops at a gate until a human approves. Use when a stage's output shapes everything downstream. Roster of companies to research → STOP, human approves the roster → corpus building → STOP → synthesis.

The rule of thumb: **put a barrier wherever an early mistake would silently poison everything after it.** A wrong company on a research roster wastes the entire corpus built on it. A formatting mistake in the last stage costs one rerun. Barriers early, pipelines late.

## When to orchestrate vs go solo

Orchestration has overhead: writing briefs, waiting on agents, merging results. It earns its keep only in specific situations.

Go solo when:

- The task fits in one context window
- It's a single file, a single question, a single edit
- You'd spend longer writing the briefs than doing the work

Orchestrate when:

- Tasks are genuinely independent (fan-out)
- The reading load would blow out your main context (delegate the reading, keep the conclusions)
- The output is public or high-stakes (add an adversary)
- The work has stages where early errors compound (add barriers)

## Practical tips

- **Name the deliverable in the brief.** "Return a markdown table of claim / status / source" beats "look into this."
- **Don't share state between parallel agents.** They can't see each other. Design tasks so they don't need to.
- **Keep the parent thin.** The orchestrating session should hold plans and conclusions, not raw research. That's the whole point.
- **Start with two agents, not ten.** One builder plus one adversary is the highest-value team you can run, and it teaches you the coordination habits before you scale.

## Going further

- Official Claude Code docs on subagents and orchestration: [code.claude.com/docs](https://code.claude.com/docs)
- The [Compound Engineering plugin](https://github.com/EveryInc/compound-engineering-plugin) ships dozens of pre-built reviewer and researcher agents
- For a worked example of barriers in a real system, see the [market intelligence skill pair](market-intelligence-skill.md)
