# Session 2 · The Bridge: Deliverable → App

This is the shortest session and the biggest idea of the night.

Your deliverable from Session 1 is not the end of the line. It is the seed for an app. And you don't need to know how to build the app. You need Claude to write the prompt that builds the app.

## The bridge prompt

When your Session 1 deliverable is done, paste this into the same conversation, verbatim:

```
Help me turn this into a simple app. Suggest 3 ways I could make it better,
then write me a prompt to build a proof of concept from scratch.
```

Claude will come back with three improvement ideas and a complete build prompt. That build prompt is your input to [Session 3](03-build-an-app.md).

## Why plan-then-implement matters

You could just say "build me an app" and sometimes get lucky. The bridge prompt works better for three reasons:

1. **Claude has the context.** It just did the work. It knows your data shape, your audience, and your format better than a cold prompt ever could.
2. **The improvement step forces a spec.** Asking for three ways to make it better turns a vague idea into concrete features before any code exists. Cheap to change now, expensive to change later.
3. **A written prompt is a reviewable plan.** You read the build prompt before you run it. If something is wrong, you fix words, not code. This is the same plan-then-implement discipline professional AI engineers use, compressed into one sentence.

This pattern generalizes way beyond tonight. Any time you want Claude to do something complex, the highest-leverage move is asking it to write the plan or the prompt first, reviewing that, and then executing.

## What good output looks like

A solid bridge response gives you:

- Three improvements that are actually about your use case, not generic polish
- A build prompt that names the data, the screens, the interactions, and the look
- Something you could hand to a stranger and they'd build roughly the same app

If the build prompt feels thin, push back once: "Make the prompt more specific about the data model and the main screen." Then take it to Session 3.

Next: [Session 3 · Build an app](03-build-an-app.md).
