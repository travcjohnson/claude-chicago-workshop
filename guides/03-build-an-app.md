# Session 3 · Build a Real App, On Your Machine

Goal: a working app running locally on your own computer, built from the prompt you wrote in Session 2. Not a chat artifact on a website. A real file, in a real folder, that does what you told it to do.

## The build path: brainstorm → plan → build

This is the same three-beat loop every professional Claude workflow uses (it's the heart of the popular brainstorming and feature-development skills): explore the idea before you build, plan before you code, then build small.

```
1. BRAINSTORM — paste the bridge prompt from Session 2 on your
   Session 1 deliverable. Claude hands back a build prompt.
2. PLAN — read it. Cut scope to ONE screen. Tell Claude what to
   drop. Plan first, build second.
3. BUILD — make a Desktop folder (my-app) → Claude Desktop →
   Code tab → Select folder → paste the prompt, then add:
   "Build it as a single index.html — plain HTML/CSS/JS,
    no installs, no frameworks."
   ONE build + max 2 refinements → double-click index.html.
   (No Code tab? The Cowork tab pointed at the same folder works too.)
```

### Why a single index.html

No node, no npm, no git on Mac, no accounts. Claude writes one file and your browser runs it. The browser is the runtime. This covers trackers, dashboards, utilities, and landing pages comfortably, and the whole app is one file you can email, drag onto a hosting service, or keep iterating on.

### Why the two-refinement rule

Your plan usage is shared across all Claude surfaces. A single build is normally 1 to 3 messages, which is cheap. Endless "now make the button bigger" loops are how people burn an evening's quota on one app. Batch your refinements: one message, three fixes.

## Stuck? Use the internet.

Don't debug environments during a workshop. The two common snags and the moves:

- **Windows asks you to install Git** when opening the Code tab. Skip it tonight: point the **Cowork** tab at your folder instead and give it the same prompt.
- **Anything else fights you:** go to [claude.ai](https://claude.ai), paste the same prompt, and say "build this as an interactive artifact," then click Publish for a shareable link. Build locally at home later. The prompt is the part that matters, and you already have it.

## The recipe library

Four app types that reliably work in a single prompt. Fill in the brackets, and keep the "single index.html, plain HTML/CSS/JS, no installs" line on the end.

### 1. Habit / personal tracker

```
Build a [habit/mood/water] tracker with a weekly grid, streak counter,
and one-tap logging. Save my data in the browser so it persists between
visits. Big touch targets. Single index.html, plain HTML/CSS/JS, no installs.
```

Browser localStorage gives you persistence with no account and no backend.

### 2. Dashboard from a spreadsheet

```
Here's my data [paste CSV]. Build a dashboard with 3 charts that answer
[question], a filter by [column], and a one-line insight summary at the top.
Single index.html, plain HTML/CSS/JS, no installs.
```

Paste the CSV straight into the prompt. The data ships inside the file.

### 3. Landing page

```
Create a polished landing page for [product/event]: hero with headline,
3 benefit cards, one testimonial, email-signup placeholder, [brand] colors.
Single index.html, all CSS inline, no external assets.
```

This is the recipe that pairs best with Netlify Drop, since landing pages get sent to other people.

### 4. Small utility / tool

```
Build a [tip splitter / unit converter / countdown timer / decision spinner]:
one screen, instant results as I type, no submit button, large friendly
controls. Single index.html, plain HTML/CSS/JS, no installs.
```

## Want a public URL?

Drag your `index.html` (inside a folder) onto [app.netlify.com/drop](https://app.netlify.com/drop).

- No account needed for an instant URL
- Unclaimed sites expire in about 24 hours; a free 30-second signup keeps the URL permanently
- The file must be named `index.html` at the folder root

## When you're serious: the production stack

The single file proves the idea. When an app needs real users, accounts, and a database, the AI-native production stack I recommend is TypeScript plus three services — a huge share of simple web apps are built with just these three and Claude:

- **[Vercel](https://vercel.com)** for hosting and deployment. Push code, get a URL, previews on every change.
- **[Supabase](https://supabase.com)** for the database, auth, and storage. Postgres with a generous free tier.
- **[GitHub](https://github.com)** for the code. Every AI coding tool speaks Git fluently.

All three have first-class support inside Claude Code, which means Claude can deploy, migrate, and manage the stack for you. That jump, from local file to production app, is exactly what tools like Claude Code are for. Start with the free official course links in the [README](../README.md) and build up.
