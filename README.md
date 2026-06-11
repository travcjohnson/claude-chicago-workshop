# Chicago | Claude Workshop

**Claude Community · June 11, 2026 · Chicago**

Hosted by [Travis Johnson](https://www.linkedin.com/in/travcjohnson), Claude Community Ambassador for Chicago and co-founder of [AuraPath AI](https://aurapathai.com).

This repo is the take-home version of the workshop: the exact session scripts we ran in the room, the app recipe library, and advanced material for people who want to go deeper.

> **Tonight's live resource page** (updated during the event): [Google Doc](https://docs.google.com/document/d/1CUMqhP7QFfE8ePzdbIbe6zFBdtRHGSaIeJlw6XoSzoM)

## The three sessions

| # | Guide | What you build |
|---|---|---|
| 1 | [Cowork crash course](guides/01-cowork-crash-course.md) | Real knowledge work, done by Claude Cowork, using a six-step loop you can rerun forever |
| 2 | [Bridge: deliverable → app](guides/02-bridge-deliverable-to-app.md) | One prompt that turns your Session 1 deliverable into an app spec |
| 3 | [Build an app](guides/03-build-an-app.md) | A working, published app from claude.ai, zero installs |

The sessions chain together on purpose. The deliverable from Session 1 is the seed for Session 2. The prompt Session 2 writes for you is the input to Session 3. Run them in order.

## App recipe library

Four app types that reliably work in a single build prompt. Full prompt skeletons and walkthroughs in [guide 3](guides/03-build-an-app.md).

| App type | Path | Starter prompt skeleton |
|---|---|---|
| Habit / personal tracker | Local index.html (Code tab) | "Build a [habit/mood/water] tracker with a weekly grid, streak counter, one-tap logging. Save data in the browser. Single index.html, plain HTML/CSS/JS, no installs." |
| Dashboard from a spreadsheet | Local index.html + pasted CSV | "Here's my data [paste CSV]. Build a dashboard with 3 charts answering [question], filter by [column], one-line insight at the top. Single index.html, no installs." |
| Landing page | Local index.html → Netlify Drop | "Create a polished landing page for [product/event]: hero, 3 benefit cards, testimonial, email-signup placeholder, [brand] colors. Single index.html, all CSS inline." |
| Tiny utility / tool | Local index.html | "Build a [tip splitter / converter / countdown / decision spinner]: one screen, instant results as I type, large friendly controls. Single index.html, no installs." |

## Links and tools

All links verified live as of June 11, 2026.

- **Claude Ambassador Program, apply:** [claude.com/community/ambassadors](https://claude.com/community/ambassadors)
- **Free official Cowork course** (Anthropic Academy): [anthropic.skilljar.com/introduction-to-claude-cowork](https://anthropic.skilljar.com/introduction-to-claude-cowork)
- **Official knowledge-work plugins:** [github.com/anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins)
- **Skills directory:** [skills.sh](https://skills.sh). Two favorites:
  - [grill-me](https://www.skills.sh/mattpocock/skills/grill-me) by mattpocock: relentlessly interviews you about your plan before you build
  - [caveman](https://www.skills.sh/juliusbrussee/caveman/caveman) by juliusbrussee: cuts Claude's output tokens roughly 65 to 75 percent
- **Compound Engineering toolkit** (Every): [github.com/EveryInc/compound-engineering-plugin](https://github.com/EveryInc/compound-engineering-plugin) · explainer: [every.to/guides/compound-engineering](https://every.to/guides/compound-engineering)
- **Netlify Drop** (instant hosting, no account needed): [app.netlify.com/drop](https://app.netlify.com/drop)
- **Anthropic brand assets:** [anthropic.com/press-kit](https://www.anthropic.com/press-kit) (heads up: this link downloads a ZIP directly)
- **Travis:** [linkedin.com/in/travcjohnson](https://www.linkedin.com/in/travcjohnson) · [aurapathai.com](https://aurapathai.com)

## Go deeper

The [advanced/](advanced/) folder is for people who finished the sessions and want more:

- [Dynamic multi-agent workflows](advanced/dynamic-workflows.md): fan-out research agents, adversarial verification, pipelines vs barriers
- [Managed agents via the Anthropic Console](advanced/managed-agents-console.md)
- [Zernio: post to LinkedIn from your terminal](advanced/zernio-marketing-cli.md)
- [SimpleFin: personal finance data for Claude](advanced/simplefin-personal-finance.md)
- [Market intelligence skill pair](advanced/market-intelligence-skill.md): GTM research with agent swarms and human-approved gates

## Share what you built

Post your build with **#ClaudeCommunity** and **#ClaudeInChicago**. The community grows when you show your work.

## License

MIT. See [LICENSE](LICENSE).
