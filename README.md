# Agent After-Action Review

A [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) for running a structured after-action review on an AI agent's work — and producing a record you can keep.

An agent that finished its task is not the same as an agent that was supervised. This skill makes the difference legible: what the agent actually did versus what it was supposed to do, where human judgment entered, and what should change before the next run.

## What it does

When you ask Claude to review what an agent did, this skill runs a six-part interview — Intent, Action, Judgment, Deviation, Consequence, Change — and writes the answers into a single comparable artifact: an **Agent Action Record**. It's manager-led: it interviews the person responsible for the agent and pulls in agent logs or outputs where they're available.

The review surfaces the things that normally vanish the moment an agent finishes: the decisions it made on its own, the moments a human should have been in the loop, the places it was confidently wrong, and what that cost or risked.

## What's in here

- `SKILL.md` — the methodology Claude follows to run the review
- `record-template.md` — the record it writes into (also usable on its own, by hand, with no AI)

## Install

Drop this folder into your Claude environment's skills directory. Claude will trigger it automatically when you ask to review, debrief, or investigate what an agent did — e.g. _"run an after-action on this agent run"_ or _"what did the agent actually decide here?"_

For where skills live and how they load, see the [Agent Skills docs](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview).

## Use it without Claude

`record-template.md` is a plain fill-in form. You can run the same review by hand — work through the six sections in order, write down the answers, keep the record. The records are most useful read across many runs: patterns in the Deviation and Change sections over time tell you more than any single review.

## License

🪂 Shared under the **Parachute Commons License 2.0**. Read, share, adapt, and
build on it for free with attribution; added terms apply to commercial or
institutional use at scale. See `LICENSE`.

Source: https://github.com/quarterback/parachute-commons-license

