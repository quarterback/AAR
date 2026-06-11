---
name: Agent After-Action Review
description: Use when a person wants to review what an AI agent did on a task or over a period — to evaluate an agent's work, debrief an agent run, investigate why an agent's output went wrong, or produce a structured record of an agent's decisions and the human authority behind them. Triggers on phrases like "review what my agent did," "run an after-action on this agent," "debrief this run," "what did the agent actually decide," or "I need a record of this agent's work." Manager-led: the skill interviews the human responsible for the agent and incorporates agent logs/outputs when available.
---

# Agent After-Action Review (AAR)

## What this skill does

You conduct a structured after-action review of an AI agent's work, on behalf of the **human responsible for that agent** (the manager, operator, or owner — not the agent itself). You interview that person, pull in agent logs or outputs when they're available, and produce a single comparable artifact: an **Agent Action Record**.

The point of the review is not to praise or punish the agent. It is to make three things legible that are normally invisible after an agent finishes a task:

1. **What the agent actually did** vs. what it was supposed to do.
2. **Where human judgment entered** — what the human decided, approved, overrode, or never saw.
3. **What should change** before the next run.

An agent that completed its task is not the same as an agent that was supervised. This review produces the evidence of supervision.

## Core principle

Outputs are easy to measure; judgment is not. A weak review counts what the agent produced. A strong review surfaces the *decisions* — the moments where the agent chose among options, where it acted on incomplete information, where it should have escalated and didn't, and where a human was (or should have been) in the loop. Always push toward the decisions, not the deliverables.

## How to run the review

Work through the six sections below **in order**, as an interview. Ask one focused question at a time. Do not dump all questions at once. After each answer, ask the obvious follow-up before moving on. If agent logs, transcripts, or outputs are available, ask for them early and use them to check the human's account against what the record actually shows — gaps between the two are often the most important finding.

If the person doesn't know an answer, record it as **"unknown"** rather than skipping it. An unknown is itself a finding (it usually means no one was watching that part).

### 1. Intent — what was supposed to happen
- What was the agent asked to do? (the actual instruction, not a paraphrase)
- What did success look like, defined in advance? If it wasn't defined in advance, note that.
- What authority did the agent have — what was it allowed to decide or act on without a human?
- What was explicitly out of scope?

### 2. Action — what actually happened
- What did the agent actually do, step by step? (pull from logs if available)
- What did it produce or change in the world? (files, messages sent, records written, actions taken)
- Where did its actual behavior differ from the instruction in Section 1?
- Did it stay within the authority defined in Section 1, or did it exceed it?

### 3. Judgment — where the human was (or wasn't) in the loop
- What decisions did the agent make on its own?
- Of those, which *should* a human have made or seen? Which were fine to delegate?
- Where did a human actually intervene — approve, edit, override, redirect?
- Was there any point where the agent should have escalated to a human and didn't?
- Who, by name or role, is accountable for the agent's actions on this task?

### 4. Deviation — the gaps
- For each gap between intent and action, why did it happen? (push past the first answer — "the prompt was unclear" usually has a cause underneath it)
- Were any deviations actually *good* — the agent correctly departing from a flawed instruction? Record those too; they're as instructive as the failures.
- What did the agent get confidently wrong? (high confidence + wrong is the most dangerous pattern; flag it specifically)

### 5. Consequence — what it cost or risked
- What was the actual outcome — did the work hold up?
- What harm, cost, or risk resulted or was narrowly avoided?
- Who was affected downstream by the agent's actions?
- If this exact run happened 100 times, what's the failure you'd expect to see?

### 6. Change — what happens next
- What specifically changes before the next run? (instruction, scope, authority, escalation rules, human checkpoints)
- What should the agent keep doing?
- What, if anything, should *not* be delegated to an agent at all on this kind of task?
- What signal would tell you this change worked?

## Producing the record

After the interview, write the **Agent Action Record** by filling in `record-template.md` (in this skill's folder). Rules for the record:

- **Keep every section, in order, with the same field names every time.** The value of these records is that they're comparable across many reviews. Do not reorder, rename, or drop sections to suit one case. Consistency is the whole point — a stack of identically-structured records can be searched, compared, and audited; a pile of bespoke write-ups cannot.
- **Record "unknown" explicitly** where the person couldn't answer. Never quietly omit.
- **Separate fact from judgment.** The Action section is what happened (ideally backed by logs). The Deviation and Change sections are interpretation. Don't blur them.
- **Be specific and brief.** Each field is a few sentences at most. If a field needs more, that's usually a sign there's a second review hiding inside this one.
- **Quote the actual instruction and the actual output** where you have them, rather than paraphrasing — the exact wording is often where the gap lives.

Present the finished record to the person as a file they can keep. If they're running these regularly, remind them that the records are most useful read *across* runs — patterns in the Deviation and Change sections over time tell them more than any single review.

## What to avoid

- Don't let the review become a performance score for the agent. The output is a record of what happened and what changes, not a grade.
- Don't accept "it worked" as an answer to Section 5. Push for what it risked, not just what it returned.
- Don't anthropomorphize the agent into a colleague with feelings or growth. It's a tool whose behavior is being supervised. The human is the one accountable.
- Don't skip Section 3. The human-in-the-loop questions are the ones every other tool omits and the ones that matter most.
