# Session 3 · Build an App

Goal: a working, published app you can share, built in one browser tab. The path is claude.ai artifacts. Zero installs, works on Free and paid plans, and one click gives you a public link that anyone can open without an account.

## The build path

```
1. Go to claude.ai → new chat (yes, the website)
2. Paste your bridge-prompt output from Session 2, or grab a recipe below
3. Say: "Build this as an interactive artifact."
4. ONE build prompt + max 2 refinements (protect your usage)
5. Click Publish → share your link
```

### Why the two-refinement rule

Your plan usage is shared across all Claude surfaces. A single artifact build is normally 1 to 3 messages, which is cheap. Endless "now make the button bigger" loops are how people burn an evening's quota on one app. State your refinements in batches: one message, three fixes.

### The least-technical escape hatch

Open the artifacts gallery in the claude.ai sidebar and **Remix** an existing app. Change one thing. You still built something, and it still counts.

## Want a real URL outside claude.ai?

**Netlify Drop:** download your artifact as an HTML file, rename it `index.html`, put it in a folder, and drag the folder onto [app.netlify.com/drop](https://app.netlify.com/drop).

- No account needed for an instant URL
- Unclaimed sites expire in about 24 hours; a free 30-second signup keeps the URL permanently
- The file must be named `index.html` at the folder root

## The recipe library

Four app types that reliably work in a single prompt. Fill in the brackets.

### 1. Habit / personal tracker

```
Build an interactive artifact: a [habit/mood/water] tracker with a weekly grid,
streak counter, and one-tap logging. Persist data between visits.
Mobile-friendly, big touch targets, no external libraries.
```

Persistence works on paid plans via artifact storage. Free users get a working session-only version, which is still a win.

### 2. Dashboard from a spreadsheet

```
Here's my data [attach or paste CSV]. Build an interactive dashboard artifact
with 3 charts that answer [question], a filter by [column], and a one-line
insight summary at the top.
```

Attach the file in chat. The published link is instantly shareable with a boss or client.

### 3. Landing page

```
Create a polished single-file HTML landing page for [product/event]: hero with
headline, 3 benefit cards, one testimonial, email-signup placeholder,
[brand] colors, all CSS inline, no external assets.
```

This is the recipe that pairs best with Netlify Drop, since landing pages get sent to people outside claude.ai.

### 4. Tiny utility / tool

```
Build a [tip splitter / unit converter / countdown timer / decision spinner]
as an interactive artifact: one screen, instant results as I type,
no submit button, large friendly controls.
```

Or skip the prompt entirely and Remix one from the gallery.

## When you're serious: the production stack

Artifacts are for proving the idea. When an app needs real users, accounts, and a database, the AI-native production stack I recommend is:

- **[Vercel](https://vercel.com)** for hosting and deployment. Push code, get a URL, previews on every change.
- **[Supabase](https://supabase.com)** for the database, auth, and storage. Postgres with a generous free tier.
- **[GitHub](https://github.com)** for the code. Every AI coding tool speaks Git fluently.

All three have first-class support inside Claude Code, which means Claude can deploy, migrate, and manage the stack for you. That jump, from artifact to production app, is exactly what tools like Claude Code are for. Start with the free official course links in the [README](../README.md) and build up.
