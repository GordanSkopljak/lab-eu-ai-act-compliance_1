# Classify your product

> **How you'll submit this lab**
>
> This repo is your lab. Fork it, do the work described below in your fork, then open a pull
> request back into this repository. An AI reviewer will check your PR against `rubric.md` and
> leave feedback directly on the PR. See `README.md` for the full workflow.

In this lab, you act like a consultant. You and a partner will each create client use cases across the four AI Act outcomes, then swap roles and review each other's proposals as if you were advising a real company. 

## Lesson alignment

- **Learning objectives:** By the end, you can **recommend** solutions that are compliant with the EU AI Act.
- **Lesson setup requirements:** Revisit the lesson sections on `Article 5 prohibited practices`, `high-risk Annex III uses`, `Article 50 transparency obligations`, `minimal risk`, and `provider vs deployer`.

---

## Submission hygiene

- **Filenames:** Use clear, descriptive names (avoid vague names such as `lab.docx` or `case_study.pdf`).
- **Scope:** Your **GitHub** repository must contain **only materials for this lab**—no unrelated projects, dumps, or personal files.
- **README or cover note:** If you submit multiple files, add a short map listing each file and what it contains.

**GitHub only:** Submit the URL to a **GitHub repository** that contains everything for this lab (Markdown, code, exports, images, decks). Do **not** submit a standalone Google Doc, Notion page, or cloud-only link as your primary deliverable—put sources or exports (for example `.md`, `.pdf`, `.pptx`, screenshots) **in the repository**.

## Kick-off

This lab practices one consulting competency: turning a vague client request into an AI Act risk call, an AI architecture recommendation, and an approval decision.

### Setup / first run

1. Open a blank working document titled `EU AI Act Approval Pack - YourName`.
2. Split the document into two parts: `Private answer key` and `Consulting response`.
3. Add four scenario headings in your `Private answer key`: `Case 1 - Prohibited`, `Case 2 - High-risk`, `Case 3 - Limited risk / transparency`, and `Case 4 - Minimal risk`.
4. Under each heading, write a short client use case that fits that target category.
5. In the `Consulting response` section, copy the same four case descriptions but remove the category labels before sharing them with your partner.

### Expected output

You should have four empty case shells ready and one drafted hidden scenario with:
- a client need
- the proposed AI behavior
- the people affected

**There should not be any clue that helps a reviewer infer the likely tier.**

Keep the labels hidden on purpose. In a real consulting conversation, clients do not tell you, "This is a prohibited AI use case" or "This is a transparency-only case." You have to infer that from the business context, the system design, and who is affected. Hiding the answer turns this from a matching exercise into a realistic discovery and advisory task.

### First Step

Draft your first client brief in 5 to 7 lines for **one specific target category**:
- one scenario must be **prohibited**
- one scenario must be **high-risk**
- one scenario must be **limited risk / transparency**
- one scenario must be **minimal risk**

Write the real category only in your `Private answer key`. In the version your partner sees, remove the label and present it like a normal client request. Make it realistic enough that a partner can infer the likely legal treatment from the facts, not from the heading.

## Pair workflow at a glance

1. You write **four hidden client scenarios**.
2. Your partner writes **four hidden client scenarios**.
3. You swap briefs without revealing the intended category labels.
4. You act as the consultant and review all four partner scenarios.
5. You produce a **3-page max approval pack** covering architecture, roles, obligations, and decision.
6. You discuss the results with your partner, who acts as the client and either accepts the proposal, challenges it, or asks for a redesign.

## CFU checkpoints

### 1. Recognize

Create four hidden client cases. Your private answer key must include exactly one case for each of these outcomes:
- prohibited
- high-risk
- limited risk with transparency obligations
- minimal risk with no specific AI Act obligations

### 2. Apply

Swap briefs and infer the likely category for each partner case without seeing their answer key. Use the lesson to justify each first-pass classification.

### 3. Integrate

For every case, propose a simple AI architecture and operating model:
- what the AI system does
- what inputs it uses
- where a human sits in the loop
- who is the provider
- who is the deployer
- whether a third-party vendor is involved

### 4. Verify

Issue a consulting decision for each case:
- `Approve`
- `Approve with controls`
- `Deny and redesign`

Your decision must match the AI Act logic you identified.

### 5. Debrief

Compare your partner's intended answer key with your inferred classifications. Discuss where the hidden scenario worked well, where it was too vague, and how your recommendation would change after the client conversation.

## Core

### Phase 1: Build the hidden client brief

Write four short client use cases. Keep them realistic and slightly messy, like a real discovery call. Do **not** name the category in the version your partner will read.

Each scenario must include:
- company type or industry
- business problem to solve
- what the AI system is expected to do
- what data or signals the system uses
- who is affected by the output
- whether a human reviews or overrides the output

Your private answer key should stay hidden from your partner. It should include the intended category and one sentence explaining why.

Use this author template in your private notes:

| Case | Client brief for partner | Intended category in your private answer key | Why you chose it |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |

### Scenario quality bar

Your four cases should not feel like textbook examples. Add enough detail that they feel plausible, but not so much that the answer becomes obvious in the first sentence.

Aim for these patterns:
- one case that clearly crosses into **prohibited** territory
- one case that lands in **high-risk** because it affects a protected Annex III area
- one case that mainly triggers **transparency** duties
- one case that stays in **minimal** territory even though AI is involved

### Phase 2: Review your partner as the consultant

Swap only the client briefs, not the private answer key.

For each case, fill in a consulting review table like this:

| Case | Likely category | Why this is your first-pass call | Proposed AI architecture | Provider / deployer / vendor | Required obligations or controls | Decision |
|---|---|---|---|---|---|---|
| 1 | | | | | | |
| 2 | | | | | | |
| 3 | | | | | | |
| 4 | | | | | | |

Your `Proposed AI architecture` can stay compact, but it must be specific. Include:
- the user or business trigger
- the model or system behavior
- the human review point
- the output or decision
- the record, logging, or disclosure layer if relevant

### Phase 3: Write the approval pack

Turn your table into a short consulting document of **3 pages max**. Write it as if the client asked you, "Can we launch this?"

Your approval pack must include:
- a short executive summary covering the overall risk picture
- all four client cases
- your inferred category for each case
- the proposed architecture and role map
- the compliance implications for that case
- your decision: approve, approve with controls, or deny and redesign
- for any prohibited case, a redesign option that moves the client toward a lawful alternative

### Required decision rules

Use these rules consistently:
- **Prohibited:** deny as proposed, then offer a redesigned lawful alternative.
- **High-risk:** do not deny automatically, but approval must depend on clear controls, oversight, and documentation.
- **Limited risk / transparency:** approval depends on clear disclosures and safe deployment boundaries.
- **Minimal risk:** approval is usually possible, but you should still flag any parallel issues such as GDPR, consumer protection, or misleading claims.

### Phase 4: Client discussion and final sign-off

Now switch into a short live review.

1. The consultant presents the approval pack.
2. The client reveals the hidden answer key.
3. The pair compares `intended category` vs `consultant category`.
4. The client either accepts the recommendation, challenges it, or asks for one redesign.
5. The consultant adds a short closing note: `What changed after the client discussion?`

## Reinforce

If you finish the core tasks early, improve the realism of your pack:
- add one borderline argument or counter-argument for each case
- note where a legal team should verify the final interpretation
- identify one operational artifact the client would need next, such as a logging policy, transparency notice, or FRIA draft

## Stretch

Pick the strongest high-risk case and turn it into a mini implementation roadmap:
- what the provider would need before market placement
- what the deployer would need before first use
- what evidence you would ask the vendor to provide

Keep this to half a page. The goal is better consulting depth, not a second full report.
