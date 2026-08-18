# Consulting Response - John Adams

Four client briefs. Review each and infer the likely EU AI Act category.

### Case 1

A group of nightlife venues wants an ID-scanning tool that also lets any venue flag a patron as "problematic" and share that patron's ID scan and photo on a shared network other member venues can view.

### Case 2

A company's leadership team wants a tool that helps set quarterly goals and KPIs, lets each team build their OKRs against those targets, and tracks progress in one shared planning document.

### Case 3

A city department wants a tool to scan live crowd video feeds at public demonstrations and match faces in real time against a watchlist, alerting officers on scene to potential matches.

### Case 4

A company wants a tool that joins sales, customer service, and internal calls, transcribes them automatically, and routes relevant notes (feature requests, promo details, etc.) into the right team's system.

## Consulting Review


| Case | Likely category | Why | Proposed AI architecture | Provider / deployer / vendor | Obligations or controls | Decision |
|---|---|---|---|---|---|---|
| **1** Shared venue watchlist | High risk, Annex III 1(a). Contested against Art 5(1)(c) | 1:N face matching across venues is biometric identification, not verification. Becomes prohibited social scoring if the system itself classifies patrons from pooled flags and bans them network wide. | Door scan, face template matched against shared flag DB, staff see match card and decide entry, match and flag provenance logged, appeal route. | Provider: scanning vendor. Deployer: each venue. Association is a second deployer, and a provider under Art 25 if it retrains. | Art 9, 10, 14, 26, 27 FRIA if high risk. Blocker regardless: GDPR Art 9 biometric data with no workable basis, Art 22 automated refusal. | **Deny and redesign** |
| **2** OKR planning tool | Minimal risk | Team level goals in a shared document. No Annex III area, no Art 5 practice, no Art 50 interaction. Barely an AI system as described. | Planning cycle opens, tool drafts goals from prior quarter data, leads edit and approve everything, output is a document. | Provider: SaaS vendor. Deployer: client. Both if built in house on a GPAI API. | None specific. Art 4 AI literacy. Flips to Annex III 4(b) if it scores individuals or feeds appraisal or task allocation. | **Approve** |
| **3** Live face matching at demonstrations | Prohibited | Art 5(1)(h): real time remote biometric identification in a public space for law enforcement. Fits none of the three exceptions, and no judicial authorisation covers open ended crowd screening. | As proposed: live feed, template on every face, watchlist match, officer alert. The officer sees the match after identification has already happened, so no human cure. | Provider: biometric vendor. Deployer: city department. Both exposed. | None available. Redesign: (a) non biometric crowd density, no identity matching; (b) post incident, targeted, judicially authorised search for a named serious crime suspect, which is Annex III 1(a) high risk. | **Deny and redesign** |
| **4** Call transcription and note routing | Minimal risk under the AI Act | No direct interaction with a person, no synthetic media, no public interest text, no Annex III area. The exposure sits outside the AI Act. | Call starts, ASR transcribes, LLM extracts requests and action items, receiving team accepts or discards each note, consent capture and retention clock. | Provider: transcription vendor. Deployer: client. ASR and LLM suppliers carry Art 53 GPAI duties. | Art 4 AI literacy. Real blockers: section 201 StGB on recording without all party consent, customer notice and lawful basis, works council agreement. Adding sentiment scoring of staff would trigger Art 5(1)(f). | **Approve with controls** |

# EU AI Act Approval Pack - Gordan

**Client cases:** four, authored by John Adams · **Question asked:** can we launch this?

## Executive summary

Two of the four can go live, one needs a redesign before it can be built at all, and one must be dropped as proposed. The heaviest exposure is concentrated in the two biometric cases. Case 3 is a prohibited practice with no controls path. Case 1 is high risk on paper but fails on data protection before the AI Act even bites. Cases 2 and 4 are low exposure under the AI Act, though Case 4 carries a criminal law problem outside it.

One gap worth naming: none of the four is a clean Article 50 transparency case. Nothing here generates synthetic media or converses with a person, so the transparency regime that became applicable on 2 August 2026 is untested across this portfolio.

---

## Case 1: Shared venue watchlist

**Category:** High risk, Annex III 1(a). Contested against Article 5(1)(c) social scoring.

**Architecture:** Patron presents ID at the door. OCR on the document, face template from the door camera, 1:N match against the shared flag database. Door staff see a match card and decide entry. Match, flag origin and outcome logged; appeal route required.

**Roles:** Provider is the scanning vendor. Deployer is each member venue. The association running the shared network is a second deployer, and becomes a provider under Article 25 if it tunes or retrains the matching.

**Implications:** If the system itself classifies patrons from pooled flags and propagates a network wide ban, Article 5(1)(c) applies and controls cannot cure it. Even on the high risk reading, the blocker arrives earlier: biometric data under GDPR Article 9 with no workable legal basis, and an automated refusal under Article 22. Annex III duties (Articles 9, 10, 14, 26, 27) apply from 2 December 2027.

**Decision: Deny and redesign.** Not denied because it is high risk. Denied because the pooled flag network cannot be given a lawful basis as scoped.

**Redesign:** Single venue, incident specific, human authored ban lists with a fixed expiry, an evidence standard and an appeal. Verification against a list the patron knows about, not identification against a shared network. Sharing between operators only through police channels.

---

## Case 2: OKR planning tool

**Category:** Minimal risk.

**Architecture:** Quarterly cycle opens, the tool drafts goal and KPI suggestions from prior quarter data, leadership and team leads edit and approve every objective, output is a shared planning document.

**Roles:** Provider is the SaaS vendor, deployer is the client. If built in house on a general purpose model API, the client is both, and the model supplier carries Article 53 duties.

**Implications:** No Annex III area, no Article 5 practice, no Article 50 trigger. Article 4 AI literacy applies to staff operating it. Two changes would flip it into Annex III 4(b): scoring individuals, or feeding appraisal, promotion or task allocation. Parallel: works council co determination the moment individual level data surfaces.

**Decision: Approve.** Conditional on the two scope limits above being written into the product spec, not just assumed.

---

## Case 3: Live face matching at demonstrations

**Category:** Prohibited, Article 5(1)(h).

**Architecture as proposed:** Live crowd feed, face template extracted from every person in frame, continuous 1:N watchlist match, push alert to officers on scene. The officer sees the match after the identification has already occurred, so there is no human review point that cures the practice.

**Roles:** Provider is the biometric vendor, deployer is the city department. Both carry exposure; the system cannot lawfully be put into service for this purpose.

**Implications:** Prohibitions have applied since 2 February 2025, so this is live exposure today, at the top penalty band. Screening an assembly is the paradigm chilling effect case under Charter Articles 11 and 12. Article 5(1)(h) is not self executing: only national law meeting Article 5(2) to (7) can authorise real time RBI, and Germany has no such enabling regime in force.

**Decision: Deny and redesign.**

**Redesign, in order of preference:**
1. **Crowd analytics with no identification.** Density, flow, bottleneck and abandoned object detection. No face templates, no database matching. Outside Article 5 and outside Annex III. Delivers the operational alerting the client actually asked for.
2. **Retrospective, targeted identification.** The ban covers real time use only. Post event identification of a named individual for a specific listed offence is Annex III 1(a) high risk, requiring authorisation by a judicial or independent administrative authority no later than 48 hours after, no untargeted sweeps, no adverse decision on the match alone, plus Article 27 FRIA and Article 49 registration.
3. Real time use is recorded as closed, not pending.

---

## Case 4: Call transcription and note routing

**Category:** Minimal risk

**Architecture:** Call starts on the telephony platform, ASR transcribes, an LLM extracts feature requests, promo terms and actions, the receiving team owner accepts or discards each routed note. Consent capture at call start, retention clock, transcript access log.

**Roles:** Provider is the transcription vendor, deployer is the client. Upstream ASR and LLM suppliers are GPAI providers under Article 53. The client becomes a provider if it rebrands the tool.

**Implications:** No direct interaction with a person, no synthetic media, no public interest text, so Article 50 is not engaged. Article 4 AI literacy applies. The real blockers sit outside the AI Act: recording spoken words without the consent of all participants engages section 201 StGB, a criminal provision; external customer calls need clear notice and a lawful basis; internal calls need works council agreement. Adding tone or sentiment scoring of employees would move this straight to Article 5(1)(f) prohibited.

**Decision: Approve with controls.** Consent capture verified before launch, works council agreement in place, and a written scope limit banning any emotion or performance inference.

---

## Where legal must verify

Whether Case 1 is social scoring under Article 5(1)(c); whether a municipal department counts as a law enforcement authority for Article 5(1)(h) in Case 3; section 201 StGB and works council exposure in Case 4.

What changed after the client discussion

The venue watchlist changed tier, not just controls. Removing the shared flag network removes the Article 5(1)(c) social scoring argument and with it the reason for denial. What remains depends on one open question: if the door check is verification against the document the patron presents, it falls outside Annex III 1(a) and drops to minimal risk, leaving a GDPR matter rather than an AI Act one. If any 1:N face matching against a local ban list survives, it stays high risk and moves from deny to approve with controls, with Article 26 deployer duties and an appeal route due before 2 December 2027. Recommended design is verification only.

Live face matching did not change. The client accepted the denial rather than taking the redesign, so no lawful alternative was carried forward. Crowd analytics with no identification stays on the record as the open path, because the operational need for on scene alerting has not gone away.

Call transcription decision unchanged.

What I would do differently. I denied the watchlist case on the pooled flag network without first asking whether the client valued the network or the door check more. They dropped the network in one sentence, which means that discovery question would have reframed the case at the start and saved a redesign cycle.