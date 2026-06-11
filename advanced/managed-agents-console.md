# Managed Agents via the Anthropic Console

Everything in the workshop ran on your laptop: Cowork tasks, scheduled tasks, Claude Code sessions. That has a hard ceiling, which you hit the moment you learned that scheduled tasks only run while your machine is awake.

Managed agents are the next rung: agents that run on Anthropic's infrastructure instead of yours.

## The concept

Instead of your laptop being the runtime, you define an agent (its instructions, its tools, its triggers) and Anthropic hosts the execution. Your machine can be closed. The agent still runs.

What this changes in practice:

- **Always-on schedules.** Recurring work fires on time, every time, no laptop-awake caveat.
- **A stable home for team agents.** An agent your coworkers rely on shouldn't live on one person's machine.
- **Cleaner separation.** Your local sessions stay yours; production automations live somewhere observable and managed.

## Where to start

The surfaces evolve quickly, so go to the official sources rather than screenshots in a blog post:

- **Anthropic Console:** [console.anthropic.com](https://console.anthropic.com) is the home for API keys, usage, and agent capabilities tied to your Anthropic account
- **API and platform docs:** [docs.anthropic.com](https://docs.anthropic.com)
- **Claude Code and Agent SDK docs:** [code.claude.com/docs](https://code.claude.com/docs), including cloud and headless execution options and the Agent SDK for building your own agents in Python or TypeScript

The mental model that transfers from tonight: an agent is still just prompt + context + goal, exactly like Session 1. Managed agents change where it runs, not what it is.

## A sensible progression

1. Prove the workflow locally in Cowork or Claude Code (the six-step loop)
2. Stabilize it as a skill so it's reproducible
3. Schedule it locally and live with the results for a week
4. Only then move it to managed infrastructure, when the workflow has earned always-on status

Most workflows die at step 2 because they weren't actually worth automating. The ones that survive a week of scheduled runs are the ones worth hosting.
