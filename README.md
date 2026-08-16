# Enterprise AI SOP

**白泽明理 · Formal eXplainable AI**  
Hangzhou consultancy for enterprise AI adoption and process redesign.  
Website: [https://fxai.ai](https://fxai.ai) · Method: [https://fxai.ai/method/](https://fxai.ai/method/) · Services: [https://fxai.ai/services/](https://fxai.ai/services/)

This repository is a public blueprint, not a product. It describes how we design organization-level AI work: diagnose first, then access, then engineering, then delivery, then compound. Execution stays with the client team.

Do not treat this as a forex, trading, or “AI agent army” kit. It is consulting methodology.

---

## The rule that sits above the five steps

Write the boundary before you automate.

If the team cannot list, on one page, which actions AI may take alone and which actions a person must approve, do not scale tools. Scaling without that list just multiplies unowned actions.

---

## Five stages

```
Diagnose → Access → Engineer → Deliver → Compound
诊断      接入      工程       交付      沉淀
```

Each stage has an exit test. If the test fails, stay. Do not skip Access to chase Delivery.

### 1. Diagnose · 诊断

**Question:** Where does AI already run, where is it blocked, and where should it never run?

**Collect**

- Tools in use (Codex, Claude Code, Cursor, Copilot, chat UIs, unofficial relays)
- Who holds keys and subscriptions
- Which data classes have already left the company
- One real workflow that management wants faster (not “we want to use AI”)

**Produce**

- A two-column boundary table: autonomous vs human-approved
- A priority list of three workflows, with the reason the others wait
- A risk note: data, audit, vendor lock-in, shadow IT

**Exit:** Legal and a business owner can both sign the boundary table without adding a new committee.

**Do not:** Start by buying more seats. Seats are not a diagnosis.

### 2. Access · 接入

**Question:** How does the organization call models so permission, routing, cost, and audit live in one place?

Minimum access layer (Codex relay or LLM API gateway):

| Control | What “done” looks like |
| --- | --- |
| Auth | Team keys, not personal API keys in repos |
| Route | Task type → primary model, with an explicit fallback |
| Limit | Per-team quota. Burst fails closed, not open |
| Cost | Monthly spend by team, without opening five vendor consoles |
| Audit | Who called what, when, from which app. Prompt bodies retained only as long as policy allows |
| Degrade | Upstream 5xx or policy deny returns a defined backup, not a raw vendor error in the product |

**Produce:** architecture sketch, permission matrix, retention window, incident path.

**Exit:** A new engineer can get a key, make a call, and appear in the audit log the same day, without borrowing someone else’s ChatGPT Plus.

**Do not:** Put a commercial relay in the path if prompts or repo context must stay inside the company boundary. A private gateway still sends the request to the upstream model. It only removes the extra middleman.

Details we use with clients: [What an LLM API gateway actually solves](https://fxai.ai/notes/what-llm-gateway-solves/).

### 3. Engineer · 工程

**Question:** How does AI enter the real development loop (requirements, implementation, test, review, docs) instead of living in side chats?

Two designs belong here.

**AI development SOP**

- Which tickets Codex / Claude Code / Cursor may finish alone
- What must stay a human draft
- What the PR description must disclose (“AI-assisted: scope X”)
- Who owns the merge if the model wrote the bulk of the diff

**Loop Engineering**

A loop is not “try again in the chat.” It is a designed cycle:

1. Plan the change against an acceptance check
2. Execute
3. Observe (tests, traces, reviewer notes)
4. Correct, then stop when the check passes

Three loops we install most often:

- Eval loop for a recurring task (a small golden set beats a vibe check)
- Agent loop for multi-step work (plan → act → look → fix)
- Production loop (failures become the next eval, not a Slack shrug)

**Exit:** The same task run twice, two weeks apart, is scored the same way. Quality is no longer “this time it felt good.”

**Do not:** Raise test coverage as the goal. Models will pad tests. Lock behaviour with an oracle, then let structure move. See [Loop Engineering](https://fxai.ai/notes/what-is-loop-engineering/) and [engineering guardrails](https://fxai.ai/notes/engineering-guardrails-for-ai/).

### 4. Deliver · 交付

**Question:** What is the path from an idea to a shippable increment, with a check at every stage?

**Produce**

- Stage list (problem, design, build, verify, release)
- Owner per stage
- Evidence required to leave the stage
- Explicit non-goals (what this increment will not do)

White-Ze only designs this path. The client team builds. We do not staff an outsourcing bench.

**Exit:** A non-engineer executive can point to the current stage and the evidence that is missing.

### 5. Compound · 沉淀

**Question:** What becomes reusable so the next team does not start from a chat history?

Typical assets:

- Skills (procedures the model must follow, not one-off prompts)
- The boundary table, living next to the repo
- Eval sets
- Incident notes from Access

**Exit:** A new hire can run the Access + Engineer path from documents, without a verbal tour.

---

## One-page check (use in a 45-minute diagnostic)

Copy this. Fill it in a meeting. If a row is blank, that row is the next design job.

| # | Check | Yes / No / Date |
| --- | --- | --- |
| 1 | Boundary table exists and is signed |  |
| 2 | Personal model keys are gone from application code |  |
| 3 | There is one gateway or relay, with fallback written down |  |
| 4 | Cost can be answered for last month in ten minutes |  |
| 5 | An incident can be replayed from logs |  |
| 6 | AI-assisted PRs disclose scope |  |
| 7 | At least one eval set exists for a recurring task |  |
| 8 | A delivery increment has stage evidence, not a demo video only |  |
| 9 | One Skill or SOP is reused by two people |  |

---

## What we refuse to put in this repo

- Customer names, prompts, or architecture that identifies a client
- Vendor account sharing instructions
- “Best AI forex bot” copy, or any trading system
- A promise that we will write or operate your production system

For the full service ladder and a diagnostic booking path, use [https://fxai.ai](https://fxai.ai).

---

## License

Documentation in this repository is provided as-is for reading and adaptation inside your company. Brand names 白泽明理 and Formal eXplainable AI remain with Baize Tech.
