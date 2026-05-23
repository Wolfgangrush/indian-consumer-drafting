---
name: _drafting_common
description: Shared reference for all 10 consumer / medical-negligence / product-liability / unfair-trade-practice / consumer-appeal drafting skills. Holds the anti-pollution rules, the consumer privacy firewall protocol (complainant names + opposite-party names — including treating-doctor / hospital / manufacturer / service-provider — product names + invoice numbers + medical-procedure particulars + claim figures substituted with placeholders before downstream AI processing; real-value re-substitution local-only in the Refiner step), the AI-style-marker blacklist, citation discipline, statutory currency rules (Consumer Protection Act 1986 → 2019 transition, Forum → Commission nomenclature, CrPC → BNSS, IEA → BSA, Drugs Rules 1945 → New Drugs and Clinical Trials Rules 2019, Companies Act 1956 → 2013), the medical-negligence threshold doctrine (Jacob Mathew / Martin F. D'Souza / Kusum Sharma / V.P. Shantha / Spring Meadows / Achutrao Haribhau Khodwa), the product-liability strand map (Sections 84 / 85 / 86 / 87 of the 2019 Act), the unfair-trade-practice ingredient map (Section 2(47) — eight categories), the pecuniary-tier rule (District ≤ ₹1 crore / State ₹1 crore — ₹10 crore / NCDRC > ₹10 crore), the territorial-jurisdiction rule (Sections 34(2) / 47(4) / 58(2)), the Section 69 limitation rule (two years from cause-of-action, condonation under the proviso), the appeal pre-deposit rule (Section 41 / 51), and the Lucknow Development Authority v. M.K. Gupta statutory-authority-as-service-provider doctrine. NOT invoked directly — referenced from every case-type skill in this plugin.
allowed-tools: Read
---

# `_drafting_common` — shared consumer drafting infrastructure

## Privacy firewall

Consumer and medical-negligence pleadings routinely contain highly sensitive material — patient medical records, treating-doctor identity, hospital admission and discharge particulars, prescription histories, billing statements, product purchase invoices, complainant identity, opposite-party manufacturer identity, claim quantum, expert-opinion contents, insurance policy numbers, payment gateway references. The plugin's privacy discipline:

1. **Reader** substitutes every complainant name, every opposite-party name, every treating-doctor name, every hospital / clinical-establishment name, every product name, every invoice / order-ID number, every claim figure, every patient name, every medical-procedure particular, every prescription reference, every complaint reference number, and every expert-opinion author with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw patient names or raw medical records.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

## AI-style-marker blacklist

Stripped by the Refiner before output:

- Em-dash (`—`) used as sentence-internal pause (replaced with semicolon or comma-bounded clause)
- Sentence-final *thereby* / *hereby* / *whereby* without an attached verb
- *Moreover*, *furthermore*, *additionally*, *in addition* as sentence-openers — replaced with *"The Complainant submits that"* / *"The Complainant further submits that"*
- *Navigate*, *delve*, *foster*, *robust*, *seamless* (metaphorical uses)
- *It is important to note that*, *it should be noted that*, *worthy of note* — replaced with direct prose
- Bullet-list-style structure in operative paragraphs (operative paragraphs are numbered, not bulleted)

## Citation discipline

The Drafter does **not** generate case names + citations from training memory. Every case citation in any explanatory note or recital must trace to a user-supplied source. Untraceable citations become `[CITATION NEEDED]` placeholders.

Headline cases the Verifier scans for fabrication:

- *Indian Medical Association v. V.P. Shantha* (1995) 6 SCC 651 — medical service is *"service"* under the Consumer Protection Act
- *Lucknow Development Authority v. M.K. Gupta* (1994) 1 SCC 243 — statutory authorities providing service for consideration fall within the Act; sovereign-function immunity unavailable for service deficiencies
- *Spring Meadows Hospital v. Harjol Ahluwalia* (1998) 4 SCC 39 — vicarious liability of hospital for the negligence of nurses and other staff
- *Achutrao Haribhau Khodwa v. State of Maharashtra* (1996) 2 SCC 634 — *res ipsa loquitur* in medical negligence (foreign body left inside the patient)
- *Jacob Mathew v. State of Punjab* (2005) 6 SCC 1 — standard of care in medical-negligence cases; modified-Bolam standard
- *Martin F. D'Souza v. Mohd. Ishfaq* (2009) 3 SCC 1 — expert-opinion safeguard at the threshold of a medical-negligence complaint
- *Kusum Sharma v. Batra Hospital* (2010) 3 SCC 480 — balanced-standard caution; courts must not second-guess medical judgment on a debatable question
- *Common Cause v. Union of India* (2018) 5 SCC 1 — recognition of "Living Wills" and Advance Medical Directives
- *Paschim Banga Khet Mazdoor Samity v. State of West Bengal* (1996) 4 SCC 37 — right to emergency medical care as part of Article 21
- *Pyaridevi Chabiraj Steels Pvt Ltd v. National Insurance Company* — NCDRC line on pecuniary-tier computation under the 2019 Act (value of consideration paid as the operative metric)

## Statutory currency rules

Every pleading filed today should cite the operative statute. Common substitution checks:

### Consumer Protection Act 1986 → 2019 transition

The 1986 Act has been repealed in toto by the Consumer Protection Act 2019 (with effect from 20 July 2020). The 2019 Act introduced significant changes — pecuniary-tier reformulation, product-liability scheme (Chapter VI), e-commerce regulation, mediation referral, Central Consumer Protection Authority, and most notably the displacement of *"Forum"* with *"Commission"* across the tiers. Every 1986-Act citation in a present-day pleading is a legacy mis-citation and must be converted:

| 1986 Act | 2019 Act |
|---|---|
| Section 2(1)(g) (deficiency) | Section 2(11) |
| Section 2(1)(c) (complaint) | Section 2(6) |
| Section 2(1)(d) (consumer) | Section 2(7) |
| Section 2(1)(r) (unfair trade practice) | Section 2(47) |
| Section 11 (District Forum jurisdiction) | Section 34 |
| Section 12 (filing of complaint) | Section 35 |
| Section 13 (procedure on admission) | Section 38 |
| Section 14 (findings of the District Forum) | Section 39 |
| Section 15 (District-to-State appeal) | Section 41 |
| Section 17 (State Commission jurisdiction) | Section 47 |
| Section 19 (State-to-NCDRC appeal) | Section 51 |
| Section 21 (NCDRC jurisdiction) | Section 58 |
| Section 22 (NCDRC powers) | Section 59 |
| Section 23 (NCDRC-to-SC appeal) | Section 67 (revisional) read with the Supreme Court's special-leave jurisdiction |
| Section 24A (limitation) | Section 69 |
| Section 25 (enforcement of orders) | Section 71 |
| Section 27 (penalty for non-compliance) | Section 72 |

The 1986-Act term *"District Forum"* / *"Forum"* is displaced by *"District Consumer Disputes Redressal Commission"* / *"Commission"* in the 2019 Act. Any residual *"Forum"* in a pleading filed today is a legacy nomenclature defect.

### CrPC 1973 → BNSS 2023

In any procedural cross-citation (rare in consumer pleadings, common in execution applications referencing CPC and in any cross-citation to a criminal-process step):

- **Section 200 CrPC 1973 → Section 223 BNSS 2023** — Magistrate cognizance of a complaint.
- **Section 482 CrPC 1973 → Section 528 BNSS 2023** — inherent powers.

### Indian Evidence Act 1872 → Bharatiya Sakshya Adhiniyam 2023

- **Section 65B IEA 1872 → Section 63 BSA 2023** — admissibility of electronic records (relevant for billing-statement printouts, email correspondence, e-commerce screenshots).
- **Section 126 IEA 1872 → Section 132 BSA 2023** — advocate-client privilege.

### Drugs and Cosmetics Rules 1945 → New Drugs and Clinical Trials Rules 2019

For any medical-negligence complaint where clinical-trial consent is in issue, the operative regulation is the **New Drugs and Clinical Trials Rules 2019**. Schedule Y of the 1945 Drugs and Cosmetics Rules has been substantially carried into the 2019 Rules. Any pleading citing Schedule Y of the 1945 Rules in a present-day clinical-trial-consent dispute is a legacy mis-citation.

### Companies Act 1956 → Companies Act 2013

For any corporate opposite party — the 2013 Act applies for incorporation / registered-office / authorised-signatory references.

Dual-citation is acceptable in any transitional pleading.

## Medical-negligence threshold doctrine

For any medical-negligence complaint, the following doctrinal stack is the floor:

1. **Service-character anchor** — *Indian Medical Association v. V.P. Shantha* (1995) 6 SCC 651: medical service rendered for consideration falls within Section 2(42) *service* under the 2019 Act; government and free-care services are within the Act where rendered to a payer or to a beneficiary of a paid scheme.
2. **Standard of care** — *Jacob Mathew v. State of Punjab* (2005) 6 SCC 1: a medical professional is liable when the negligence is "gross" — a mere error of judgment is not negligence. The Bolam test (a body of competent professional opinion that would have acted similarly) applies in modified form.
3. **Threshold safeguard** — *Martin F. D'Souza v. Mohd. Ishfaq* (2009) 3 SCC 1: before issuing notice on a medical-negligence complaint, the Commission ought to obtain an expert medical opinion supporting the negligence allegation. Practical implication — the Drafter recommends procuring an expert opinion before filing wherever the facts permit.
4. **Balanced standard** — *Kusum Sharma v. Batra Hospital* (2010) 3 SCC 480: Commissions / Courts must not second-guess medical judgment on a debatable question; medical opinion is contestable; deviation from the standard of care, not the outcome, is the test.
5. **Vicarious liability of the hospital** — *Spring Meadows Hospital v. Harjol Ahluwalia* (1998) 4 SCC 39: a hospital is vicariously liable for the negligence of its nurses, junior doctors, and ancillary staff acting in the course of employment.
6. **Res ipsa loquitur** — *Achutrao Haribhau Khodwa v. State of Maharashtra* (1996) 2 SCC 634: where the act is such that it speaks for itself (e.g. foreign body left inside the patient), the burden may shift.
7. **Advance Medical Directives** — *Common Cause v. Union of India* (2018) 5 SCC 1: recognition of "Living Wills"; procedural-safeguard regime for withdrawal of life-prolonging treatment.
8. **IMC Regulations 2002 anchors** —
   - Clause 7.14 — informed consent
   - Clause 7.16 — confidentiality
   - Clause 1.3.2 — maintenance of medical records (3 years from last entry)
   - Clause 7.17 — second opinion
9. **NHRC / MoHFW Charter of Patients' Rights (2018 / 2021)** — informational anchor for the substantive list of patient rights (Right to Information; Informed Consent; Right to Refuse Treatment; Right to Second Opinion; Right to Confidentiality; Billing Transparency; Right to Records).

## Product-liability strand map (Chapter VI of the 2019 Act)

For any product-liability action, the strand mapping is non-negotiable:

- **Section 84 — Product manufacturer** liable where the product contains a manufacturing defect / deviates from manufacturing specifications / does not conform to express warranty / does not contain adequate instructions / does not contain adequate warnings.
- **Section 85 — Product service provider** liable where the service is faulty / imperfect / deficient / inadequate; or there is an act of omission, commission, or negligence; or there is failure to issue adequate instructions or warnings.
- **Section 86 — Product seller** liable where the seller exercised substantial control over the design / testing / manufacturing / packaging / labelling; or altered or modified the product; or made an express warranty; or sold the product where the identity of the manufacturer is not known; or failed to exercise reasonable care in assembling / inspecting / maintaining the product or in passing on warnings or instructions from the manufacturer.
- **Section 87 — Exceptions** (the manufacturer is not liable where the product was misused / altered / modified after sale; where the harm arose from the user's failure to follow adequate instructions; etc.) — pre-empted in the complaint where the facts permit.

The Drafter maps the defendant array to the appropriate strand per Sections 84 / 85 / 86. A single product-liability action may engage all three strands against three separate opposite parties.

## Unfair-trade-practice ingredient map (Section 2(47) — eight categories)

The Section 2(47) definition recognises eight categories of unfair trade practice:

(i) False representation as to standard, quality, quantity, grade, composition, style, or model
(ii) False representation that goods or services have sponsorship, approval, performance, characteristics, accessories, uses, or benefits which they do not have
(iii) Bargain-price falsity (representing that goods or services are being offered at a bargain price when they are not)
(iv) Offering gifts, prizes, or other items with the intention of not providing them, or creating an impression that something is being given free
(v) Conduct of contests, lotteries, games of chance, or skill for the purpose of promoting goods or services
(vi) Manufacture of spurious goods or false grading
(vii) Permitting publication of any advertisement of goods or services that is false or misleading
(viii) Permitting the sale or supply of goods that do not comply with mandatory standards

For an e-commerce UTP, the Consumer Protection (E-Commerce) Rules 2020 and the Guidelines for Prevention and Regulation of Dark Patterns 2023 are read with Section 2(47). The Section 49 (State Commission) / Section 59 (National Commission) discontinuance prayer is the operative remedy.

## Pecuniary-tier rule

The 2019 Act tiers pecuniary jurisdiction by value of consideration paid as goods or services (NOT by the compensation claimed, per the *Pyaridevi Chabiraj* NCDRC line):

- **District Commission (Section 34)** — value of consideration paid up to ₹50 lakh (originally under the 2019 Act, the threshold was ₹1 crore; amended by the Consumer Protection (Jurisdiction of the District Commission, the State Commission and the National Commission) Rules 2021 to ₹50 lakh; verify against current notification before drafting).
- **State Commission (Section 47)** — value of consideration paid exceeding ₹50 lakh (or ₹1 crore per the original) but not exceeding ₹2 crore (originally ₹10 crore; amended in 2021); verify current notification.
- **National Commission (Section 58)** — value of consideration paid exceeding ₹2 crore (originally ₹10 crore); verify current notification.

The Drafter pulls the current threshold from `case-config.md` (which should reflect the user's verification of the latest notification). The Verifier flags a pecuniary mis-alignment as a fatal defect.

## Territorial-jurisdiction rule (Sections 34(2) / 47(4) / 58(2))

A Commission has territorial jurisdiction where:

(a) The opposite party / each of the opposite parties ordinarily resides or carries on business or has a branch office or personally works for gain at the time of the institution of the complaint, OR
(b) Any of the opposite parties resides or carries on business (with the leave of the Commission, or where the others acquiesce in the institution), OR
(c) The cause of action wholly or in part arises, OR
(d) (Section 34(2) of the 2019 Act ONLY — a 2019 enlargement for the District Commission tier) The complainant resides or personally works for gain.

The complainant-residence ground is District-Commission-specific and is NOT available at the State Commission or NCDRC tiers under the analogous Sections 47(4) and 58(2). The Verifier flags any State / NCDRC pleading that purports to invoke the complainant-residence ground.

## Section 69 limitation rule

Section 69 of the 2019 Act prescribes a two-year limitation from the date of cause of action for filing a complaint before any Commission. The proviso permits condonation for sufficient cause to be recorded in writing. The Drafter pleads the limitation paragraph for every complaint:

- Cause-of-action date
- Date of filing
- Days within limitation (or days beyond + sufficient-cause grounds)

For appeals — Section 41 (District-to-State, 45 days) / Section 51 (State-to-NCDRC, 30 days); condonation under proviso to each sub-section.

For execution — no separate limitation under the 2019 Act, but Section 71 enforcement is subject to Article 136 of the Limitation Act 1963 (12 years from the date the decree becomes enforceable) when treated as a decree of civil court.

## Appeal pre-deposit rule (Sections 41 / 51)

- **Section 41 appeal (District-to-State)** — where the appeal is against an order requiring the appellant to pay any amount, the appellant must deposit 50% of that amount or ₹25,000, whichever is less (verify against current notification). A separate waiver application with grounds may be moved.
- **Section 51 appeal (State-to-NCDRC)** — where the appeal is against an order requiring the appellant to pay any amount, the appellant must deposit 50% of that amount or ₹50,000, whichever is less (verify against current notification). A separate waiver application with grounds may be moved.

The Verifier computes the pre-deposit from `case-facts.md` and flags any appeal memo that omits the computation.

## Statutory-authority-as-service-provider doctrine

For any complaint against a statutory authority (development authority / municipal corporation / public-sector undertaking / state housing board / state electricity board / regional transport authority), *Lucknow Development Authority v. M.K. Gupta* (1994) 1 SCC 243 anchors the proposition that statutory authorities rendering service for consideration fall within the Consumer Protection regime and cannot plead sovereign-function immunity. The Overseer ensures this anchor is invoked where applicable.


---

## v0.2.1 RENDER DISCIPLINE (load-bearing — Drafter must follow)

**Pandoc + reference.docx + post-pandoc fix script.** The Drafter writes Markdown using the heading discipline below. Pandoc converts the Markdown to `.docx` using the SHIPPED reference.docx at `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/reference.docx` — pre-customised with locked Word styles matching the filing-grade Bombay HC Nagpur convention (extracted from an actual filed Second Appeal pleading):

- **Body (Normal)** — TNR 14pt, 1.5 line spacing, justified, 0.5cm first-line indent
- **Heading 1** — TNR 14pt **bold + centered** (NOT underlined) — for the Court / Forum / Tribunal header line and the case-number line
- **Heading 2** — TNR 14pt **bold + UNDERLINED + centered + letter-spacing** — for spaced section headers (`F A C T S`, `G R O U N D S`, `P R A Y E R`, `I N D E X`, `S Y N O P S I S`, `L I S T   O F   A N N E X U R E S`, `V E R I F I C A T I O N`)
- **Heading 3** — TNR 14pt **bold + UNDERLINED + centered** — for unspaced section headers (`SUBSTANTIAL QUESTIONS OF LAW`, `ACTS & RULES`, `CITATIONS`) and statutory opening (`WRIT PETITION UNDER ARTICLE 226 …`)
- **Heading 4** — TNR 14pt **bold + UNDERLINED + left-aligned** — for left-anchored bold-underlined headings (`MOST RESPECTFULLY SHEWETH:`)
- **Tables** — `tblLayout = fixed`; first row bold centered; cell margins locked

### Markdown heading mapping

| Markdown | Rendered as | Used for |
|---|---|---|
| `# Heading 1` | Bold centered (no underline) | Court header line; case-number line; cover-page anchors |
| `## Heading 2` | Bold centered UNDERLINED with letter-spacing | Spaced section headers (`## F A C T S`, `## G R O U N D S`, `## P R A Y E R`, `## I N D E X`, `## S Y N O P S I S`, `## L I S T   O F   A N N E X U R E S`, `## V E R I F I C A T I O N`) |
| `### Heading 3` | Bold centered UNDERLINED | Unspaced section headers + statutory opening |
| `#### Heading 4` | Bold left UNDERLINED | `#### MOST RESPECTFULLY SHEWETH:` |
| Body paragraph | TNR 14pt justified 1.5 spacing 0.5cm first-line indent | Everything else |
| `**Bold inline**` | Bold | Property descriptors / annexure markers / key terms inline within Facts narrative |

### Bold-number paragraph convention

Facts and Grounds paragraphs use **BOLD NUMBERS**: `**1.**`, `**2.**`, `**3.**` followed by a tab + body. Renders as the gold-standard pleading layout.

### Two-step pandoc command (Step 2 is NON-NEGOTIABLE)

```bash
# Step 1 — pandoc → .docx with locked Word styles
pandoc draft-v1.md -o draft-v1.docx \
  --reference-doc="${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/reference.docx" \
  --from=markdown+pipe_tables+raw_tex

# Step 2 — force table column widths
python3 "${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/fix_docx_tables.py" draft-v1.docx
```

Step 2 forces column widths on every table — 5-col (Sr.No / Annx / Particulars / Date / Pgs) = 8/8/60/14/10; 4-col = 10/10/65/15; 3-col = 10/75/15; 2-col Dates–Events = 18/82. Locks first-row bold + centered + vertically-centered cells. **Skipping the fix script reproduces the v0.2.0 Index-table defect (Sr.No / Annx columns stacking vertically).**

Do NOT auto-generate a fresh reference.docx in the case folder. Use the shipped one or a `<case-folder>/reference.docx` override.

### Cover-page discipline

INDEX, SYNOPSIS, LIST OF ANNEXURES each begin on a new page (`\newpage` in Markdown) and carry ONLY: forum header (`#`) + case-number line (`#`) + short cause-title (Petitioner short name `///VERSUS///` Respondent short name) + section header (`##`) + table + Counsel block. DO NOT repeat the full party address block on cover pages.

### Pipeline-optionality (advocate-cost discipline)

The full 6-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) is **NOT** mandatory. Only the first three stages are required to produce a filing-grade draft. Stages 4–6 are OPTIONAL QC layers the advocate explicitly invokes. Default exit point is here, after Drafter (~280K tokens). Full pipeline ~600K tokens — disproportionate for routine pleadings.

When `draft-v1.docx` is written, the Drafter's job is complete. The advocate decides whether to invoke the QC stages.
