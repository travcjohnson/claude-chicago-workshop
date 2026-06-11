# Zernio: Post to LinkedIn from Your Terminal

During the workshop intro, a selfie went from phone to a live LinkedIn post in one sentence to Claude, while the talk kept moving. The tool behind that demo is Zernio, a CLI for publishing to LinkedIn and other social platforms from the terminal.

## Why a CLI for marketing

The point isn't typing posts in a terminal for fun. The point is that **once posting is a command, it's automatable by an agent.** Claude can draft the post, attach the image, schedule it for the right time slot, and queue three variants, all inside the same session where it did the actual work the post is about.

That collapses the distance between "did a thing" and "told the world about the thing," which is where most solo marketing dies.

## Setup

Install the CLI and authenticate (see Zernio's docs for the current install command for your platform). Your credentials live in a local config file:

```
~/.zernio/config.json
```

Keep your key out of scripts and repos. Reference it from the config or an environment variable, never inline:

```bash
# config.json holds your key, or:
export ZERNIO_KEY=<YOUR-ZERNIO-KEY>
```

You'll also need the account ID for each surface you post to (a personal LinkedIn profile and a company page are separate accounts with separate IDs).

## The core pattern: posts:create

```bash
# Plain text post
zernio posts:create --account <ACCOUNT_ID> --text "Shipped the workshop repo. Link below."

# Post with an image
zernio posts:create --account <ACCOUNT_ID> --text "Tonight's room." --media ./selfie.jpg
```

A note from real use: organization tags (tagging a company page) render as real clickable tags. Tagging individual people from the API is unreliable on LinkedIn, so plan posts around org tags and do person-tags manually if they matter.

## Scheduling and drafts

```bash
# Schedule for a specific time instead of posting now
zernio posts:create --account <ACCOUNT_ID> --text "..." --schedule "2026-06-12T09:00:00-05:00"

# Create as a draft to review in the dashboard before it goes live
zernio posts:create --account <ACCOUNT_ID> --text "..." --draft
```

Flags evolve, so check `zernio --help` for the current set.

## The agent workflow

Where this gets interesting is handing the whole loop to Claude:

```
Draft a LinkedIn post about the feature we just shipped. My voice, no hype words.
Show me the text for approval. Once I approve, post it to my personal account
with the screenshot, and schedule a follow-up for the company page tomorrow at 9am.
```

The approval step matters. Let the agent draft and stage everything, but keep a human green light between the draft and anything that posts publicly. That one habit prevents every category of embarrassing automation story.
