# SimpleFin: Personal Finance Data for Claude

Claude is a strong financial analyst with nothing to analyze. Your transaction history is locked inside bank apps that were never designed to export cleanly. SimpleFin is the bridge.

## The concept

[SimpleFin](https://www.simplefin.org) is a protocol and service for read-only access to your own financial data. You connect your bank accounts once, and SimpleFin gives you a private access URL that returns your accounts, balances, and transactions as clean structured data.

Three properties make it a good fit for Claude work:

- **Read-only.** The bridge can see transactions, never move money. The blast radius of any mistake is zero dollars.
- **You hold the credential.** One access URL, stored locally by you, revocable by you.
- **Plain structured data.** Accounts and transactions come back as simple JSON, which is exactly the shape Claude reasons over well.

## Setup pointer

Start at [simplefin.org](https://www.simplefin.org), set up the SimpleFin Bridge, and connect your institutions. You end up with an access URL. Treat it like a password: store it locally (a file outside any repo, or your keychain), never paste it into anything public, and never commit it.

From there, the workflow is: fetch your data with the access URL, save the JSON to a local working folder, and point Claude (Cowork or Claude Code) at the folder.

## Example prompts

Once Claude can see your transactions file, the analysis is the easy part:

```
Here are my transactions for the last 90 days. Categorize them, then show me
my top 10 spending categories with monthly trend. Flag anything that looks
like a subscription I might have forgotten about.
```

```
Build me a monthly cash-flow summary: income vs spending by week, with the
three biggest one-off expenses called out separately from recurring spend.
```

```
Compare this month to my 6-month average. What changed, in plain English,
in five bullets or fewer?
```

The natural next step is the Session 1 loop: save the analysis as a skill, schedule it weekly, and get a Monday-morning money briefing without asking for it.

## A note on caution

Financial data deserves the strict version of every hygiene rule: keep the data and the access URL on your machine, work in local folders rather than pasting transactions into shared docs, and keep the integration read-only. Analysis is the win here. Automating money movement is a different risk class entirely, and not what this setup is for.
