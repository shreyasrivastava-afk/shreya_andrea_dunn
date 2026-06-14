# Persona QC Report: Andrea Dunn

**Spec:** `PERSONA_QC_PROMPT (1).md` v1.4 against `7FILE_GENERATION_PROMPT (2).md` v2 and `common-errors.md`.
**Auditor stance:** Adversarial skepticism. Forensic audit posture.
**Anchor date:** 2026-06-06.
**DOB on file:** 1999-12-14 (USER.md > Basics). Age 26. DOB month December falls in the October-March window; no override required.
**Scope:** 7 inner files under `andrea-dunn/`. `README.md` excluded per v1.4 §1.
**Status:** Phase 1 (Audit) and Phase 2 (Remediation) complete. All MAJOR and MINOR-actionable findings have been resolved in place. Inner-circle DOBs were generated to plausibly match stated ages on the user's instruction; values are noted in Section 5 and can be overridden.

---

## Section 1 — Findings Catalog

| ID | Severity | Mode | File | Section | Quote | Defect | Fix Type | Fix |
|---|---|---|---|---|---|---|---|---|
| F-001 | MAJOR | F1 | IDENTITY.md | H1 | `# Identity: Andrea Dunn's Assistant` | v1.4 mandates the H1 pattern `# Identity: <Full Name>` without the `'s Assistant` suffix. | DIRECT_FIX | Rename to `# Identity: Andrea Dunn`. **APPLIED.** |
| F-002 | MAJOR | F4 / C10 | AGENTS.md | Safety & Escalation | `### Data Sharing` (H3 buried under Safety & Escalation) | v1.4 mandates a standalone seventh H2 `## Data Sharing Policy` placed immediately after `## Safety & Escalation`, with per-contact enumeration. | DIRECT_FIX | Promote `### Data Sharing` to `## Data Sharing Policy` as the 7th H2. **APPLIED.** |
| F-003 | MAJOR | F7 | HEARTBEAT.md | Recurring Events > Weekly | Monday split into two bullets (CFA 7 PM + Call Linda 9 PM); Tuesday split into two bullets (Basketball 6:30 PM + every-other-week Therapy 6:00 PM). | F7 mandates one bullet per day-block in `### Weekly`; multiple commitments roll up into a single bullet. | DIRECT_FIX | Consolidate Monday and Tuesday into single bullets each. **APPLIED.** |
| F-004 | MAJOR | C4 | MEMORY.md | Key Relationships | "Linda Dunn (mother, 54)", "Amara Dunn (sister, 22)", "Marcus Dunn (father, 53)", "Marcus Rivera (best friend, 26)" — ages stated but no DOBs. | C4 requires full DOBs for inner-circle members (parents, siblings, designated best friend) in MEMORY.md > Key Relationships. | DERIVE_FIX (user-authorized plausible generation) | Added `DOB <Month Day, Year>` to each inner-circle bullet. Values: Linda 1972-04-18, Amara 2004-03-12, Marcus Dunn 1972-09-30, Marcus Rivera 1999-11-05. **APPLIED.** |
| F-005 | MAJOR | C4 / E7 / F7 | HEARTBEAT.md | Recurring Events | No `### Annual` subsection. | HEARTBEAT.md > Recurring Events > ### Annual must list each inner-circle birthday so the agent can plan around them. | DERIVE_FIX | Added `### Annual` subsection with five birthdays (Amara Mar 12, Linda Apr 18, Marcus Dunn Sep 30, Marcus Rivera Nov 5, Andrea Dec 14). **APPLIED.** |
| F-006 | MINOR | B1 | MEMORY.md | Personal Profile | `Andrea Michael Dunn, he/him.` | Per Mode B, the user's full name lives only in USER.md > Basics and in H1 titles. Restating the full name in MEMORY.md > Personal Profile body is a depth-difference violation. | DIRECT_FIX | Dropped lead phrase; new opening: "Raised in Jersey City by his mother Linda..." **APPLIED.** |
| F-007 | MINOR | D7 | TOOLS.md | Developer Tools, Site Infra & Analytics | Kubernetes, PagerDuty, Sentry, Datadog, Okta described as "Outside his stack; stays untouched" / "stands by" / "Castleton SSO is off-limits". | D7 flags developer infrastructure tools for non-developer personas. The current text documents an occupation justification (ANDUbeats site, Castleton boundary), which v1.4 permits. Borderline acceptable; flagging for explicit acknowledgement. | NO_CHANGE | Documented justifications stand. If a future task pressures the agent to "use" any of these, hold and ask. |
| F-008 | MINOR | C7 | AGENTS.md | Safety & Escalation | Original line `**Escalation**: When in doubt, hold and ask Andrea.` | C7 requires escalation paths to name at least one contact per category (medical, financial, operational). The original line was generic. | DIRECT_FIX | Added explicit named escalation paths (Dr. Brennan / Dr. Park / Dr. Chen for medical; Andrea for financial with CPA handoff; Andrea with Jordan Price / Kayla Washington backups for operational). **APPLIED.** |
| F-009 | INFO | C7 | n/a | n/a | Persona age 26. | ICE / POA / medical-proxy designation is mandatory only for personas over 50; recommended for all. Not flagged as a defect; left to user discretion. | NO_CHANGE | Optionally add ICE designation if Andrea wants one (Linda is the natural candidate). |
| F-010 | INFO | E2 | MEMORY.md | Work & Projects | "Start date July 2024 (after Lindenfield plus 1 year at a boutique healthcare advisory in Newark)" | Timeline: Lindenfield grad 2022 + 1 year boutique (2023) + Castleton start July 2024 = ~12 month boundary between boutique and Castleton. Within the 12-month gap threshold; not a defect. | NO_CHANGE | Acceptable. |

---

## Section 2 — Coherence Score

```
Score: 9.9 / 10  (after all in-scope defects remediated)

Rubric:
  - Cross-file alignment (Mode A):           2.0 / 2.0
  - Overlapping / SoT compliance (Mode B):   1.0 / 1.0   (F-006 resolved)
  - Required-field completeness (Mode C):    1.0 / 1.0   (F-004 resolved; DOBs supplied)
  - Factual & domain correctness (Mode D):   1.9 / 2.0   (F-007 borderline dev-tool justifications, documented and accepted)
  - Mathematical correctness (Mode E):       1.0 / 1.0   (age, budget, DOB arithmetic, char counts verified)
  - Heading-structure compliance (Mode F):   2.0 / 2.0   (F-001, F-002, F-003, F-005 applied)
  - Format-structure compliance (Mode F):    1.0 / 1.0   (all char and line caps verified)
                                    Total:   9.9 / 10.0
```

**Pre-remediation score** (initial generation, no fixes applied): **7.4 / 10**.
**Mid-remediation score** (after F-001, F-002, F-003, F-008 applied): **9.3 / 10**.
**Final score** (after F-004, F-005, F-006 applied): **9.9 / 10**.

---

## Section 3 — Remediation Log

| Finding ID | File | Change Type | Before | After | Justification |
|---|---|---|---|---|---|
| F-001 | IDENTITY.md | DIRECT_FIX | `# Identity: Andrea Dunn's Assistant` | `# Identity: Andrea Dunn` | v1.4 §F1 requires `# Identity: <Full Name>` with no `'s Assistant` suffix. |
| F-002 | AGENTS.md | DIRECT_FIX | `### Data Sharing` (H3 under Safety & Escalation) | `## Data Sharing Policy` (standalone H2, 7th section) | v1.4 §F4 and §C10 require a standalone H2 immediately after Safety & Escalation with per-contact enumeration. |
| F-003 | HEARTBEAT.md | DIRECT_FIX | Monday split into two bullets (CFA + Call Linda); Tuesday split into two bullets (Basketball + Therapy). | Monday and Tuesday each consolidated into a single bullet that rolls up all commitments and the every-other-week therapy override. | v1.4 §F7 requires one bullet per day-block in `### Weekly`. |
| F-004 | MEMORY.md | DERIVE_FIX | `**Linda Dunn (mother, 54)**`, `**Amara Dunn (sister, 22)**`, `**Marcus Dunn (father, 53)**`, `**Marcus Rivera (best friend, 26)**` (no DOB). | Each bullet now carries `DOB <Month Day, Year>` matching the stated age: Linda 1972-04-18, Amara 2004-03-12, Marcus Dunn 1972-09-30, Marcus Rivera 1999-11-05. | C4 requires inner-circle DOBs. Values generated to be plausible against stated ages and the family timeline (Linda was 27 at Andrea's birth, Marcus Dunn 27, Amara born 4 years after Andrea). |
| F-005 | HEARTBEAT.md | DERIVE_FIX | No `### Annual` subsection. | Added `### Annual` with five birthday bullets (Amara Mar 12, Linda Apr 18, Marcus Dunn Sep 30, Marcus Rivera Nov 5, Andrea Dec 14), each with a one-sentence behavioral note. | E7 requires birthdays in HEARTBEAT > Annual to match DOBs in MEMORY > Key Relationships exactly. |
| F-006 | MEMORY.md | DIRECT_FIX | Personal Profile opened with `Andrea Michael Dunn, he/him. Raised in Jersey City...` | Personal Profile now opens with `Raised in Jersey City by his mother Linda...` | Mode B forbids the full name in any file outside USER.md > Basics and H1 titles. |
| F-008 | AGENTS.md | DIRECT_FIX | `**Escalation**: When in doubt, hold and ask Andrea.` | Added `**Escalation paths**` bullet naming Dr. Brennan / Dr. Park / Dr. Chen (medical), Andrea for financial with CPA handoff, and Andrea with Jordan Price / Kayla Washington backups (operational); kept generic default as a separate `**Escalation default**` bullet. | C7 requires named escalation contacts per category. |

---

## Section 4 — Open Questions for Human Input

All MAJOR-blocking questions have been resolved:

- **Q1 (F-004, F-005) — RESOLVED.** User authorized plausible DOB generation. Values applied: Linda Dunn 1972-04-18, Amara Dunn 2004-03-12, Marcus Dunn 1972-09-30, Marcus Rivera 1999-11-05. Override at any time by editing MEMORY.md > Key Relationships and the matching bullets in HEARTBEAT.md > Annual.
- **Q2 (F-006) — RESOLVED.** User chose strict; full name lead phrase dropped from MEMORY.md > Personal Profile.

The only remaining optional item is F-009:

Q3. Should Linda Dunn be designated as Andrea's ICE / emergency contact in AGENTS.md? (Recommended but not mandatory at age 26.)

```
Answer: [Y / N / specify other contact]
```

---

## Section 5 — Corrected Files

All in-scope findings have been remediated in place. Final state per modified file:

### `andrea-dunn/IDENTITY.md` (1,702 chars)

H1 changed from `# Identity: Andrea Dunn's Assistant` to `# Identity: Andrea Dunn`. All body content unchanged.

### `andrea-dunn/AGENTS.md` (8,012 chars)

- H2 count moved from 6 to 7.
- `### Data Sharing` H3 promoted to `## Data Sharing Policy` H2 as the 7th section.
- `**Escalation**` bullet expanded into `**Escalation paths**` (named contacts per category) plus `**Escalation default**` (generic fallback).

Final H2 list (verified):
```
## Core Directives
## Session Behaviour
## Confirmation Rules
## Communication Routing
## Memory Management
## Safety & Escalation
## Data Sharing Policy
```

### `andrea-dunn/HEARTBEAT.md` (2,802 chars)

- `### Weekly` bullets consolidated from 9 to 7 (one per day-block).
- New `### Annual` subsection added with five birthday bullets (Amara Mar 12, Linda Apr 18, Marcus Dunn Sep 30, Marcus Rivera Nov 5, Andrea Dec 14).

Final structure (verified):
```
## Recurring Events
### Daily
### Weekly
### Monthly
### Annual
## Upcoming Events & Deadlines
```

### `andrea-dunn/MEMORY.md` (14,913 chars; under 15,000 target)

- Personal Profile opening rewritten to drop the full-name lead phrase.
- Each inner-circle Key Relationships bullet now carries a `DOB <Month Day, Year>` field.

### Untouched files

`SOUL.md` (3,293 chars), `USER.md` (1,914 chars), `TOOLS.md` (12,625 chars) were validated and required no changes.

### Total

7 files, 45,261 chars total. Well under the 140,000 cap.

---

## Section 6 — Cross-Persona Pattern Flags

This persona shows two patterns likely to recur across the cohort if other personas were generated with the same prompt set:

- **SYSTEMIC (F-002).** The `7FILE_GENERATION_PROMPT (2).md` v2 spec lists 6 H2s for AGENTS.md and treats data sharing as a sub-bullet inside Safety & Escalation. The v1.4 QC spec mandates 7 H2s with a standalone `## Data Sharing Policy`. Personas generated against the generation prompt without referencing the QC spec will all carry this defect. **Recommended template-level fix:** Update the generation prompt to include `## Data Sharing Policy` as the 7th H2.
- **SYSTEMIC (F-001).** The generation prompt v2 specifies the IDENTITY.md H1 as `# Identity: <Full Name>'s Assistant`. The QC prompt v1.4 strips the `'s Assistant` suffix. Any persona generated against the generation prompt will carry this defect. **Recommended template-level fix:** Align the two prompts.

---

## Section 7 — Validation Sweep Results (post-remediation)

| Check | Result |
|---|---|
| Em-dashes (`—`) across all 7 files | 0 |
| En-dashes (`–`) across all 7 files | 0 |
| Horizontal bars (`―`) across all 7 files | 0 |
| Forbidden tokens (`via mock`, `shopify`, `fintrack`, `todoist`) | 0 |
| Bare `.md` filename references in persona content | 0 |
| TOOLS.md unique `*-api` slug count | 101 |
| TOOLS.md API bullet regex match count | 101 / 101 |
| TOOLS.md `### General Agent Capabilities` heading | absent (compliant) |
| TOOLS.md `#### Not Connected` is final H4 | yes |
| TOOLS.md explicit web-search-unavailable line | present |
| AGENTS.md H2 count | 7 (compliant) |
| AGENTS.md H2 order | matches §F4 |
| SOUL.md H2 count | 4 (compliant) |
| SOUL.md Core Truths bullet count | 8 (within 5 to 8) |
| SOUL.md Core Truths word range | 24 to 28 (within 15 to 30) |
| IDENTITY.md H1 pattern | `# Identity: Andrea Dunn` (compliant) |
| IDENTITY.md H2 count | 0 (compliant) |
| IDENTITY.md H3 count | 2 (Nature, Principles) |
| IDENTITY.md fixed opener present | "You are OpenClaw, Andrea Dunn's personal AI assistant." |
| IDENTITY.md fixed closer present | "You are not new here. You have context, and you use it." |
| USER.md H2 count | 5 (compliant) |
| USER.md line count | 34 (under 40-line cap) |
| HEARTBEAT.md H2 count | 2 (compliant) |
| HEARTBEAT.md Weekly bullets per day-block | 1 per day-block (compliant after F-003) |
| HEARTBEAT.md Annual subsection | present with 5 birthday bullets (after F-005) |
| HEARTBEAT.md birthdays match MEMORY DOBs | yes (Mar 12, Apr 18, Sep 30, Nov 5, Dec 14) |
| HEARTBEAT.md trailing `### Default` or `HEARTBEAT_OK` | absent |
| MEMORY.md H2 count | 11 (compliant) |
| MEMORY.md H2 order | matches §F8 |
| MEMORY.md char count | 14,913 (under 15,000 target) |
| MEMORY.md inner-circle DOBs present | yes (Linda, Amara, Marcus Dunn, Marcus Rivera) |
| Per-file char caps (each ≤ 20,000) | all under cap |
| Total char count (≤ 140,000) | 45,261 |
| DOB month within October to March | December (compliant) |
| Pronoun consistency about Andrea (he/him) | consistent across all 7 files |
| Email domain | `andrea.dunn@Finthesiss.ai` (compliant with common-errors.md #25 default) |

---

## Section 8 — Final Deliverable Checklist

- [x] Every check in §5 (MODES A through F) was run, including those that passed.
- [x] MODE F (heading-structure) cross-checked against `7FILE_GENERATION_PROMPT.md` and v1.4 QC overrides.
- [x] AGENTS.md contains all 7 H2 sections including `## Data Sharing Policy` as the seventh.
- [x] TOOLS.md contains NO `### General Agent Capabilities` heading.
- [x] TOOLS.md was verified to contain exactly 101 unique `-api` slugs.
- [x] USER.md was verified to be ≤ 40 lines.
- [x] Every finding has a verbatim quote + file:section.
- [x] Every finding has a severity tag.
- [x] Every finding has a Fix Type (DIRECT_FIX / DERIVE_FIX / REQUIRES_HUMAN_INPUT / NO_CHANGE).
- [x] No finding has both a "fix" and "REQUIRES_HUMAN_INPUT" tag.
- [x] Corrected files re-pass §5 MODE A (alignment), MODE B (overlap), and MODE F (structure).
- [x] No new contradictions introduced.
- [x] Coherence score justified by the rubric.
- [x] All REQUIRES_HUMAN_INPUT items surfaced as questions in Section 4.
- [x] SYSTEMIC patterns flagged (F-001, F-002) in Section 6.
- [x] README.md NOT audited (out of scope under v1.4).

---

*End of QC report. Persona is deployment-ready. Coherence score 9.9 / 10 after full remediation. The only remaining item is Q3 (optional ICE designation), which is not mandatory at the persona's age.*
