# Session 1 · Cowork Crash Course

Claude Cowork is Claude Code power for knowledge work. You give it a goal, it works your files, apps, and connectors, and it hands you back a finished deliverable. No terminal.

## Before you start: the facts

- **Paid plans only.** Cowork is available on Pro, Max, Team, and Enterprise. Free tier does not have it. If you're on Free, pair with a neighbor.
- **Desktop app only.** Mac, or the latest Windows build of Claude Desktop. There is no web version.
- **Usage limits are doubled through July 5, 2026** for paid plans. If you're learning this in June, you picked the cheapest possible time to do it.

## The six-step loop

Follow this exactly. Everyone runs the same six steps on their own domain. The steps are universal, the work is yours.

```
1. Open Claude Desktop → Cowork tab (the middle tab) → grant a working folder
2. Pick work you've ALREADY done once by hand
3. Get the data in: a connector (Gmail / Microsoft 365), a file, or paste it
4. Prompt: what to produce · for whom · in what format
5. Review the output → fix the INSTRUCTIONS → run it again
6. Stretch: "save this as a skill" → /schedule
```

### Why "work you've already done once"

You know what good looks like. That is your acceptance criteria. Reproducing a known outcome is how you learn to judge the loop, not the magic.

### Step 4 is where most people underdo it

Tell Claude three things: **what to produce, for whom, and in what format.** "Summarize this" is weak. "Turn these notes into a one-page status update for my VP, with a risks section and three bullet recommendations, as a Word doc" is a prompt.

### Step 5 is the whole lesson

If the output is wrong, the instructions were wrong. **Fix the instructions, not the AI.** You are the prompt master. Don't argue with the output in chat, edit the prompt and run it again. One full iteration of this loop teaches you more than an hour of theory.

## No connector? Zero-setup starters

These are Anthropic's own launch demos. They need nothing connected and work for everyone:

1. **Organize your messy Downloads folder.** Point Cowork at it and ask for a sensible structure.
2. **Receipt screenshots → formatted Excel file.** Drop in a pile of screenshots, get back a real .xlsx with formulas.
3. **Scattered notes → drafted report.** Give it your mess, name the audience and format, get a .docx.

If a connector gives you OAuth trouble, do not debug it during a session. Switch to a folder starter and keep moving.

## Stretch goals

Once the loop works:

1. **Make it a skill.** Tell Claude: `save this as a skill`. Skills are evolved prompts. Next time, the whole workflow is one command.
2. **Make it recurring.** Type `/schedule` to turn the task into a scheduled task (hourly, daily, weekly, weekdays, or manual).

**The one scheduling gotcha:** scheduled tasks only run while your computer is awake with Claude Desktop open. Missed runs fire the next time you open the app. Plan around it.

## Keep going

- Free official course: [Introduction to Claude Cowork](https://anthropic.skilljar.com/introduction-to-claude-cowork) (Anthropic Academy)
- Official plugins for sales, finance, legal, marketing, HR, and more: [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins)

When your deliverable is done, take it straight into [Session 2: the bridge prompt](02-bridge-deliverable-to-app.md).
