<div align="center">

<img src="docs/banner.png" width="820"/>

**Claude-compatible plugin for drafting Indian consumer-protection and medical-negligence pleadings before District / State / NCDRC Commissions**

Visit the live site: [wolfgangrush.github.io](https://wolfgangrush.github.io)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/Wolfgangrush/indian-consumer-drafting/pulls)
[![GitHub Repo](https://img.shields.io/badge/wolfgang__rush-eleventh--plugin-8A2BE2)](https://github.com/Wolfgangrush)

</div>


# indian-consumer-drafting

> **Open-source Claude-compatible plugin for drafting Indian consumer-protection, medical-negligence, product-liability, unfair-trade-practice, and consumer-appeal pleadings.**
>
> Six-agent drafting pipeline · ten case-type skills · case-config-aware · Consumer Protection Act 2019 + Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 + Consumer Protection (E-Commerce) Rules 2020 + Sale of Goods Act 1930 + Indian Medical Council (Professional Conduct) Regulations 2002 + New Drugs and Clinical Trials Rules 2019 + Bharatiya Nagarik Suraksha Sanhita 2023 + Bharatiya Sakshya Adhiniyam 2023 discipline encoded.
>
> Released under MIT. Open infrastructure for the legal community. **No commercial engagement offered through this repository** — see Disclaimer below.

> ⚠️ **AI can make mistakes. Always verify the output.**
>
> This software generates assistive drafts and suggestions only. Every legal claim, citation, statute reference, procedural step, deadline calculation, and ground of relief must be independently verified by a qualified human practitioner before filing, advising a client, or relying on the output. The publisher accepts no liability for outputs used without verification.

> 🛡️ **Privacy primitive — Reader agent invokes the gateway:** This drafting plugin's **Reader agent** (the first agent in the 6-agent pipeline) calls [pseudonymisation-gateway](https://github.com/Wolfgangrush/pseudonymisation-gateway) (MIT · wolfgang_rush) on the user's case folder BEFORE any cloud-LLM call. Real client names · government IDs · case numbers · phone numbers · currency amounts are replaced with placeholders (`[PERSON_1]` · `[AADHAAR_1]` · `[CASE_NO_1]` · etc.) in a session-scoped in-memory token map that never touches disk. Downstream agents (Format · Drafter · Verifier · Refiner) work entirely on the sanitized text. The **Overseer agent** (the final agent) calls `desanitize()` to restore real values in the final pleading before it reaches the file system. Cloud LLM vendors never see your client's real PII.


## 🚀 Install — wolfgang_rush marketplace

This plugin is part of the [wolfgang_rush plugin family](https://github.com/Wolfgangrush/wolfgang-rush-marketplace) — 14 Indian-court drafting plugins distributed via one Claude Code marketplace.

**Via Claude Code (CLI) — recommended for the plugin family:**

```bash
/plugin marketplace add Wolfgangrush/wolfgang-rush-marketplace
/plugin install indian-consumer-drafting@wolfgang-rush
```

**Via Claude Desktop:** see the [Installation](#installation) section below for the `.zip` upload flow.

---

---

## Table of contents

1. [What this plugin does](#what-this-plugin-does)
2. [Case-type skills (full inventory with statutory authority)](#case-type-skills-full-inventory-with-statutory-authority)
3. [The 6-agent drafting pipeline (what each agent does)](#the-6-agent-drafting-pipeline)
4. [Installation](#installation) — Claude Desktop application
5. [Your first pleading — step-by-step walkthrough](#your-first-pleading--step-by-step-walkthrough)
6. [The `case-config.md` file](#the-case-configmd-file)
7. [Built-in compliance disciplines](#built-in-compliance-disciplines)
8. [Privacy firewall — extra discipline for consumer / medical content](#privacy-firewall--extra-discipline-for-consumer--medical-content)
9. [Why MIT License](#why-mit-license)
10. [Sibling plugins](#sibling-plugins)
11. [Why this exists](#why-this-exists)
12. [Roadmap](#roadmap)
13. [Contributing](#contributing)
14. [Contact](#contact)
15. [Author and brand](#author-and-brand)
16. [Provenance and privilege statement](#provenance-and-privilege-statement)
17. [Disclaimer and Bar Council of India Rule 36 compliance](#disclaimer-and-bar-council-of-india-rule-36-compliance)
18. [License](#license)

---

## What this plugin does

This plugin lets an Indian advocate, sitting inside the Claude Desktop application, point at a case folder on disk and obtain a complete consumer-forum pleading in `.docx` form — Cause Title, Memo of Parties, Statutory Opening, List of Dates, Facts, Deficiency / Defect / Unfair-Trade-Practice / Product-Liability / Medical-Negligence pleadings, Cause of Action, Pecuniary and Territorial Jurisdiction paragraphs, Limitation, Prayer, Verification, Affidavit-in-support, Index, List of Documents, and the accompanying applications (interim relief under Section 38(9), condonation of delay under the proviso to Section 69, exemption from filing certified copies, urgent listing, mediation reference under Section 37, ex-parte application where the opposite party fails to appear) — formatted in the Commission's idiom and the case-type-specific structure, sourced from a `case-config.md` file the user places in the case folder.

The pipeline is six agents running in sequence:

1. **Reader** — extracts consumer case-facts (complainant, opposite parties, transaction date, purchase consideration, product or service description, deficiency event, service-failure timeline, medical-procedure record, expert opinion, prior-correspondence trail, compensation claimed) from the case folder with a per-document audit log, and applies the **consumer-specific privacy firewall** (every complainant name, every opposite-party name including manufacturer / service-provider / doctor / hospital, every product name, every invoice number, every claim figure, every patient name, every treating-doctor name, and every complaint reference number substituted with structural placeholders before downstream AI processing; the placeholder → real-value mapping is stored locally on the user's machine only).
2. **Format** — loads the case-type skill template, reads the user's `case-config.md`, and pre-substitutes Commission name / case-number prefix / fee / statutory opening / limitation anchor into a `format-shell.md` ready for the Drafter.
3. **Drafter** — writes the actual pleading. Cause Title in the correct Commission nomenclature ("District Consumer Disputes Redressal Commission" / "State Consumer Disputes Redressal Commission" / "National Consumer Disputes Redressal Commission" — the 2019 Act replaced the 1986 Act's term "Forum" with "Commission"), Memo of Parties, Statutory Opening invoking the operative section, List of Dates, Facts as numbered narrative paragraphs with inline annexure markers, Deficiency / Defect / UTP / Product-Liability / Medical-Negligence pleadings, Pecuniary and Territorial Jurisdiction, Limitation, Prayer with case-type-specific reliefs, Verification, Affidavit-in-support, Index, List of Documents, and accompanying applications.
4. **Verifier** — anti-hallucination firewall **plus** statutory-currency check (Consumer Protection Act 1986 → 2019 transitions; *Forum* → *Commission* nomenclature; CrPC 1973 → BNSS 2023; IEA 1872 → BSA 2023; Drugs Rules 1945 → New Drugs and Clinical Trials Rules 2019) **plus** pecuniary-jurisdiction cross-check (≤ ₹1 crore / ₹1 crore to ₹10 crore / above ₹10 crore) **plus** territorial-jurisdiction check under Sections 34(2) / 47(4) / 58(2) **plus** limitation computation under Section 69 (two years from the cause-of-action date) **plus** medical-negligence pleading discipline (*Jacob Mathew* threshold + *V.P. Shantha* inclusion + *Martin F. D'Souza* expert-opinion safeguard + *Kusum Sharma* balanced-standard direction) **plus** product-liability pleading discipline (Sections 82 to 87 — manufacturer / product service provider / product seller liability mapping) **plus** unfair-trade-practice ingredient discipline under Section 2(47) **plus** notice-of-defect / notice-of-deficiency trajectory check.
5. **Refiner** — applies Verifier flags, polishes language to formal Indian Commission register, enforces internal numbering and annexure-cross-reference consistency, strips AI-style markers, and re-substitutes real party names, real product particulars, real invoice numbers, real medical-procedure particulars, and real compensation figures into the final `.docx` (strictly on the user's local machine — the underlying AI never holds real values).
6. **Overseer** — reads the polished draft with an opposing-counsel lens (opposite-party's counsel for a complainant's pleading; complainant's counsel for an opposite party's reply or written version; the manufacturer's counsel for a product-liability defence; the hospital's counsel for a medical-negligence defence). Flags weak deficiency narrative, missing *Jacob Mathew* threshold pleading, missing expert opinion in a medical-negligence complaint, broken Section 69 limitation, weak prayer, internal contradictions, *Spring Meadows Hospital* / *Achutrao Haribhau Khodwa* line on medical service / nurse vicarious liability, *Lucknow Development Authority v. M.K. Gupta* on consumer status of an applicant against a statutory authority, *Common Cause* on Advance Medical Directives.

The output is what an advocate would put before the Commission for filing — **not a template. Not a checklist. A pleading** — ready for the advocate's review, professional verification, signature, fee, and filing.

---

## Case-type skills (full inventory with statutory authority)

The plugin ships with ten case-type skills, each covering a distinct consumer / medical-negligence / product-liability case-type:

### 1. `district-commission-complaint-section-35-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 34 (jurisdiction of the District Commission) + Section 35 (filing of complaint; manner) + Section 36 (procedure on admission) + Section 38 (procedure on admission of complaint) + the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020. **Use case:** consumer complaint for deficiency of service / defective goods / unfair trade practice where the value of the goods or services paid as consideration does not exceed ₹1 crore (pecuniary tier as amended by the Consumer Protection (Jurisdiction of the District Commission, the State Commission and the National Commission) Rules 2021 — verify the current threshold). **Output:** complete complaint with Cause Title in District Commission nomenclature, Section 35 statutory opening, Memo of Parties, List of Dates, Facts paragraphs anchored to purchase / service / deficiency annexures, Cause of Action, Pecuniary and Territorial Jurisdiction (Section 34(2)), Limitation (Section 69), Prayer with refund / replacement / compensation / interest / costs, accompanying applications.

### 2. `state-commission-complaint-section-47-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 47 (jurisdiction of the State Commission, including original and appellate jurisdiction) + the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020. **Use case:** original complaint before the State Commission where the value of the consideration exceeds ₹1 crore but does not exceed ₹10 crore. **Output:** complete complaint with Cause Title in State Commission nomenclature, Section 47 statutory opening, full pleadings, Pecuniary and Territorial Jurisdiction (Section 47(1)(a)(i) and Section 47(4)), Prayer, accompanying applications.

### 3. `ncdrc-complaint-section-58-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 58 (jurisdiction of the National Commission, including original / appellate / revisional jurisdiction) + NCDRC (Practice and Procedure) Regulations + the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020. **Use case:** original complaint before the NCDRC where the value of the consideration exceeds ₹10 crore. **Output:** complete complaint with Cause Title in NCDRC nomenclature, Section 58 statutory opening, full pleadings, Pecuniary and Territorial Jurisdiction (Section 58(1)(a)(i) and Section 58(2)), Prayer, accompanying applications. **NCDRC Practice Direction discipline** enforced — Memo of Parties on a separate sheet, Index with running paragraph anchors, List of Dates immediately following the Cause Title.

### 4. `medical-negligence-complaint-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 2(11) (definition of *deficiency*) + Section 2(42) (definition of *service*) + relevant Commission jurisdiction (District / State / NCDRC per pecuniary tier); Indian Medical Council (Professional Conduct, Etiquette and Ethics) Regulations 2002; New Drugs and Clinical Trials Rules 2019 (where clinical-trial consent is in issue); Clinical Establishments (Registration and Regulation) Act 2010; *Indian Medical Association v. V.P. Shantha* (1995) 6 SCC 651 (medical service is *service* under the Act); *Jacob Mathew v. State of Punjab* (2005) 6 SCC 1 (standard of care; Bolam test imported in modified form); *Martin F. D'Souza v. Mohd. Ishfaq* (2009) 3 SCC 1 (expert-opinion safeguard at the threshold); *Kusum Sharma v. Batra Hospital* (2010) 3 SCC 480 (balanced standard, no second-guessing); *Spring Meadows Hospital v. Harjol Ahluwalia* (1998) 4 SCC 39 (vicarious liability of hospital for the negligence of nurses and other staff); *Achutrao Haribhau Khodwa v. State of Maharashtra* (1996) 2 SCC 634 (foreign body left inside the patient — *res ipsa loquitur*). **Use case:** complaint alleging deficiency of medical service against a treating doctor / hospital / clinical establishment. **Output:** complete complaint pleading the *Jacob Mathew* threshold (gross negligence, not mere error of judgment), the *Martin F. D'Souza* expert-opinion safeguard (expert opinion supporting the negligence claim before filing), the *Kusum Sharma* balanced-standard caution, the *V.P. Shantha* service-character anchor, the *Spring Meadows* vicarious-liability head where the hospital is impleaded, and the IMC Regulations 2002 (Clauses 7.14 on informed consent / 7.16 on confidentiality / 1.3.2 on records). **Anti-fabrication discipline** — the Drafter does NOT invent medical-procedure dates, prescription particulars, discharge-summary details, or expert opinions; every clinical fact must trace to a user-supplied medical record in the case folder.

### 5. `product-liability-action-section-83-draft`

**Statutory authority:** Consumer Protection Act 2019 — Sections 82 to 87 (product liability scheme): Section 82 (application of Chapter VI); Section 83 (product liability action); Section 84 (liability of product manufacturer — defective manufacture / defective design / deviation from manufacturing specifications / non-conformity with express warranty / failure to contain adequate instructions / inadequate warning); Section 85 (liability of product service provider — faulty / imperfect / deficient service / act of omission or commission or negligence / failure to issue adequate instructions or warnings); Section 86 (liability of product seller — exercise of substantial control over the design / testing / manufacturing / packaging / labelling / altered the product / made an express warranty / sold the product where the identity of the manufacturer is not known / failed to exercise reasonable care in assembling / inspecting / maintaining the product); Section 87 (exceptions to product liability action). **Use case:** product-liability action for harm caused by a defective product against the product manufacturer, product service provider, or product seller. **Output:** complete product-liability complaint with the Section 84 / 85 / 86 liability-strand mapped to the defendant array, the harm-causation chain pleaded, and the Section 87 exception pre-empted in the grounds.

### 6. `unfair-trade-practice-complaint-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 2(47) (definition of *unfair trade practice* — eight categories, including false representation as to standard / quality / quantity / grade / composition / style / model; misleading advertisement; bargain price falsity; offering gifts / prizes with the intention of not providing them or creating an impression of free gift; conduct of contests / lotteries / games of chance for promoting goods or services; manufacturing of spurious goods or false grading; permitting publication of any advertisement of goods or services that is false or misleading; selling goods that do not comply with mandatory standards) + Section 49 (powers of the State Commission to direct discontinuance of the unfair trade practice) + Section 59 (powers of the National Commission for the same). **Use case:** complaint alleging an unfair trade practice — misleading advertisement, false representation, bargain-price falsity, dark-pattern in e-commerce (read with the Consumer Protection (E-Commerce) Rules 2020 and the Guidelines for Prevention and Regulation of Dark Patterns 2023). **Output:** complete UTP complaint with the Section 2(47) ingredient pleaded by category, the Section 49 / 59 discontinuance prayer, and the compensation prayer.

### 7. `consumer-appeal-section-41-district-to-state-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 41 (appeal from order of the District Commission to the State Commission — 45-day limitation from the date of the order; condonation of delay under the proviso for sufficient cause; appeal against an order awarding compensation requires the appellant to deposit 50% of the awarded amount, capped at ₹25,000, as a pre-deposit per Section 41 proviso (verify against current notification)). **Use case:** appellant aggrieved by the order of the District Commission. **Output:** complete Memorandum of Appeal with grounds (erroneous appreciation / misapplication of law / procedural irregularity / quantum miscalculation / limitation / jurisdiction), Prayer to set aside the impugned order, accompanying applications (condonation of delay / pre-deposit waiver / urgent listing / stay of operation of the impugned order).

### 8. `consumer-appeal-section-51-state-to-ncdrc-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 51 (appeal from order of the State Commission to the NCDRC — 30-day limitation from the date of the order; condonation of delay under the proviso to sub-section (1); appeal against an order awarding compensation requires the appellant to deposit 50% of the awarded amount, capped at ₹50,000, as a pre-deposit under Section 51(2) — verify against current notification). **Use case:** appellant aggrieved by the order of the State Commission. **Output:** complete Memorandum of Appeal with grounds, Prayer, accompanying applications (condonation of delay / pre-deposit waiver / stay).

### 9. `consumer-revisional-application-section-67-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 67 (revisional jurisdiction of the National Commission — calling for records and passing such order as it thinks fit, where the State Commission has exercised jurisdiction not vested in it / failed to exercise jurisdiction vested in it / acted in exercise of jurisdiction illegally or with material irregularity; supervisory scope, not appellate; Article 227-type discipline). **Use case:** party aggrieved by an interlocutory or final order of the State Commission where the order is not appellable under Section 51 but suffers from jurisdictional / illegality / material-irregularity defects. **Output:** complete Revisional Application with grounds anchored to Section 67(a) / (b) / (c), Prayer for setting aside the impugned order and remitting, accompanying applications.

### 10. `consumer-execution-application-section-71-draft`

**Statutory authority:** Consumer Protection Act 2019 — Section 71 (every order made by a District / State / National Commission may be enforced as if it were a decree or order made by a court in a suit pending before it; manner of execution per the Code of Civil Procedure 1908) + Section 72 (penalty for non-compliance with order — imprisonment up to three years / fine up to ₹1 lakh / both). **Use case:** decree-holder seeking enforcement of a Commission's compensation order against a judgment-debtor that has failed to pay. **Output:** complete Execution Application with the order being executed annexed, the demand for payment / specific performance, the Section 72 penalty prayer where wilful disobedience is alleged, and the prayer for attachment / sale / arrest per CPC modes of execution.

### Shared infrastructure skills

- **`_drafting_common`** — anti-pollution rules, consumer-specific privacy firewall, AI-style-marker blacklist, citation discipline, **statutory currency rules** (Consumer Protection Act 1986 → 2019 transition with *Forum* → *Commission* nomenclature; CrPC → BNSS / IEA → BSA / Drugs Rules 1945 → New Drugs and Clinical Trials Rules 2019), **medical-negligence threshold rule** (*Jacob Mathew* + *Martin F. D'Souza* + *Kusum Sharma* + *V.P. Shantha*), **product-liability liability-strand map** (Sections 84 / 85 / 86), **unfair-trade-practice ingredient map** (Section 2(47) eight categories), **pecuniary-tier rule** (District ≤ ₹1 crore / State ₹1 crore to ₹10 crore / NCDRC > ₹10 crore), **territorial-jurisdiction rule** (Sections 34(2) / 47(4) / 58(2) — opposite-party residence / cause-of-action / complainant residence), **Section 69 limitation rule** (two years from cause-of-action; proviso for condonation for sufficient cause).
- **`_consumer_drafting_base`** — universal Indian consumer-pleading skeleton (Cause Title, Memo of Parties, Statutory Opening, List of Dates, Facts, Deficiency / Defect / UTP / Product-Liability / Medical-Negligence pleadings, Cause of Action, Pecuniary and Territorial Jurisdiction, Limitation, Prayer, Verification, Affidavit-in-support, Index, List of Documents, accompanying applications).

---

## The 6-agent drafting pipeline

| Agent | What it reads | What it writes | Key consumer-domain specialisation |
|---|---|---|---|
| **`reader`** | Every file in the case folder + the case-type skill's expected annexures list | `case-facts.md` with per-document audit log + privacy-firewalled placeholder mapping in the header | Privacy firewall — substitutes complainant names + opposite-party names (manufacturer / service-provider / doctor / hospital) + product names + invoice numbers + claim figures + medical-procedure particulars + patient names + complaint reference numbers before downstream AI processing; mapping stored locally only |
| **`format`** | `case-facts.md` + `case-config.md` + case-type SKILL.md + `_consumer_drafting_base` | `format-shell.md` with Commission name / case-number-prefix / fee / statutory-opening / limitation-anchor pre-substituted | Resolves District / State / NCDRC Commission nomenclature for the Cause Title; legacy *Forum* nomenclature flagged and converted |
| **`drafter`** | `case-facts.md` + `format-shell.md` + case-type SKILL.md + `_consumer_drafting_base` + law PDFs | `draft-v1.md` + `draft-v1.docx` | Writes Cause Title + Memo of Parties + Statutory Opening + List of Dates + Facts (with inline annexure markers) + Deficiency / Defect / UTP / Product-Liability / Medical-Negligence pleadings + Cause of Action + Pecuniary and Territorial Jurisdiction + Limitation + Prayer + Verification + Affidavit + Index + List of Documents + accompanying applications |
| **`verifier`** | `draft-v1.md` + `case-facts.md` + `case-config.md` + law PDFs | `verification-report.md` | Anti-hallucination + statutory-currency (CPA 1986 → 2019; *Forum* → *Commission*; CrPC → BNSS / IEA → BSA / Drugs Rules 1945 → New Drugs and Clinical Trials Rules 2019) + pecuniary-tier check + territorial-jurisdiction check + Section 69 limitation map + medical-negligence threshold discipline (*Jacob Mathew* / *Martin F. D'Souza* / *Kusum Sharma* / *V.P. Shantha*) + product-liability strand check (Sections 84 / 85 / 86) + unfair-trade-practice ingredient check (Section 2(47)) + appeal pre-deposit computation under Section 41 / 51 |
| **`refiner`** | `draft-v1.md` + `verification-report.md` + `case-config.md` + `case-facts.md` | `draft-v2.md` + `draft-v2.docx` | Polish to Indian Commission formal register + internal numbering / cross-reference / annexure-marker consistency + privacy-firewall reversal (real values re-substituted from local mapping into final `.docx`) |
| **`overseer`** | `draft-v2.docx` + `case-facts.md` + `case-config.md` | `opposing-notes.md` + `final-draft.docx` | Opposing-counsel critique — weak deficiency narrative, missing *Jacob Mathew* threshold pleading, missing expert opinion in a medical complaint, broken Section 69 limitation, weak prayer, internal contradictions, *Spring Meadows* / *Achutrao Haribhau Khodwa* / *V.P. Shantha* / *Lucknow Development Authority v. M.K. Gupta* / *Common Cause* anchors |

---

## Installation

This is a Claude-compatible plugin in the Anthropic plugin format, designed to run inside the **Claude Desktop application** (available at <https://claude.ai/download>). The plugin folder location depends on your OS:

| OS | Plugin folder path |
|---|---|
| **macOS** | `~/Library/Application Support/Claude/plugins/` |
| **Windows** | `%APPDATA%\Claude\plugins\` (typically `C:\Users\<you>\AppData\Roaming\Claude\plugins\`) |
| **Linux** | `~/.config/Claude/plugins/` |

Clone the plugin into that folder:

```bash
# macOS / Linux
mkdir -p ~/Library/Application\ Support/Claude/plugins   # adjust per OS table
cd ~/Library/Application\ Support/Claude/plugins
git clone https://github.com/Wolfgangrush/indian-consumer-drafting.git indian-consumer-drafting

# Windows (PowerShell)
mkdir -Force $env:APPDATA\Claude\plugins
cd $env:APPDATA\Claude\plugins
git clone https://github.com/Wolfgangrush/indian-consumer-drafting.git indian-consumer-drafting
```

Restart the Claude Desktop application. The plugin is auto-discovered on the next session start.

### Anthropic Plugin Marketplace (when available)

When the plugin lands on the Anthropic Plugin Marketplace, you will be able to install it from inside the application's plugin browser without `git`. Until then, the manual clone steps above are canonical.

### Verifying the install

In a Claude session, type:

- *"draft District Commission complaint"* / *"draft consumer complaint District"* — triggers `district-commission-complaint-section-35-draft`
- *"draft State Commission complaint"* / *"draft State Commission original complaint"* — triggers `state-commission-complaint-section-47-draft`
- *"draft NCDRC complaint"* / *"draft NCDRC original complaint"* — triggers `ncdrc-complaint-section-58-draft`
- *"draft medical negligence complaint"* — triggers `medical-negligence-complaint-draft`
- *"draft product liability action"* / *"draft Section 83 CPA"* — triggers `product-liability-action-section-83-draft`
- *"draft unfair trade practice complaint"* / *"draft UTP complaint"* — triggers `unfair-trade-practice-complaint-draft`
- *"draft District-to-State appeal"* / *"draft Section 41 appeal"* — triggers `consumer-appeal-section-41-district-to-state-draft`
- *"draft State-to-NCDRC appeal"* / *"draft Section 51 appeal"* — triggers `consumer-appeal-section-51-state-to-ncdrc-draft`
- *"draft NCDRC revisional"* / *"draft Section 67 revision"* — triggers `consumer-revisional-application-section-67-draft`
- *"draft consumer execution"* / *"draft Section 71 execution"* — triggers `consumer-execution-application-section-71-draft`

---

## Your first pleading — step-by-step walkthrough

Suppose you wish to draft a **medical-negligence complaint** before the State Consumer Disputes Redressal Commission, alleging deficiency of medical service by a treating doctor and a hospital, claiming compensation of ₹2.5 crore.

### Step 1 — create a case folder

```
~/Desktop/cases/
└── medical-negligence-state-2026/
    ├── case-config.md         ← declares Commission tier + pecuniary value + medical-negligence character
    ├── inputs/
    │   ├── admission-card.pdf
    │   ├── consent-form.pdf
    │   ├── discharge-summary.pdf
    │   ├── medical-records.pdf
    │   ├── prescription-trail.pdf
    │   ├── billing-statements.pdf
    │   ├── second-opinion.pdf
    │   ├── expert-medical-opinion.pdf
    │   ├── correspondence-with-hospital.pdf
    │   └── prior-notice-to-doctor.pdf
    └── laws/
        ├── consumer-protection-act-2019.pdf
        ├── cdrc-rules-2020.pdf
        ├── imc-regulations-2002.pdf
        ├── new-drugs-and-clinical-trials-rules-2019.pdf
        └── limitation-act-1963.pdf
```

### Step 2 — write `case-config.md`

```yaml
forum: "State Consumer Disputes Redressal Commission, Maharashtra (Mumbai Circuit Bench)"
case_type: "medical-negligence-complaint"
case_number_year: 2026
pecuniary_tier: "state"           # district / state / national
compensation_claimed_rupees: 25000000   # ₹2.5 crore
deficiency_character: "medical-negligence"
medical_procedure_date: "[Procedure-Date-Placeholder]"
discharge_date: "[Discharge-Date-Placeholder]"
cause_of_action_date: "[CoA-Date-Placeholder]"
limitation_anchor: "Section 69 — two years from cause of action"
expert_opinion_supplied: true
territorial_jurisdiction_anchor: "Section 47(4) — cause of action arose in the State of Maharashtra at the hospital located in Mumbai"
parties:
  - role: "Complainant"
    party_type: "Patient (or legal heir of deceased patient)"
    party_name: "[Complainant-Placeholder]"
  - role: "Opposite Party No. 1"
    party_type: "Treating Doctor"
    party_name: "[OP-1-Placeholder]"
  - role: "Opposite Party No. 2"
    party_type: "Hospital / Clinical Establishment"
    party_name: "[OP-2-Placeholder]"
  - role: "Opposite Party No. 3"
    party_type: "Insurer of the Hospital (where impleaded)"
    party_name: "[OP-3-Placeholder]"
```

### Step 3 — invoke the plugin

Open Claude Desktop, navigate to the case folder, and type:

> *draft medical negligence complaint*

The pipeline runs:

1. **Reader** reads every PDF in `inputs/`, builds `case-facts.md` with privacy-firewalled placeholder mapping, validates that all required statutes are in `laws/`.
2. **Format** loads the `medical-negligence-complaint-draft` skill, reads `case-config.md`, builds `format-shell.md`.
3. **Drafter** writes `draft-v1.md` and `draft-v1.docx`.
4. **Verifier** reads `draft-v1.md` against `case-facts.md`, writes `verification-report.md`.
5. **Refiner** applies the verification flags, polishes the prose, re-substitutes real values, writes `draft-v2.docx`.
6. **Overseer** reads `draft-v2.docx` with a hospital's-counsel lens, writes `opposing-notes.md` and `final-draft.docx`.

The advocate now reviews `final-draft.docx` against `opposing-notes.md`, makes professional adjustments, applies court fee, signs the verification, swears the affidavit, and files.

---

## The `case-config.md` file

This file declares all Commission-level / case-type-level / matter-level constants that the plugin substitutes into the format shell. Keep it on the user's local machine — `.gitignore` excludes it from any git repo.

Minimum fields:

- `forum` — exact name of the Commission (e.g. *"District Consumer Disputes Redressal Commission, [bench city]"* / *"State Consumer Disputes Redressal Commission, Maharashtra"* / *"National Consumer Disputes Redressal Commission, New Delhi"*)
- `case_type` — one of the ten supported case types
- `case_number_year` — current year for case-number placeholder
- `pecuniary_tier` — *"district"* (≤ ₹1 crore) / *"state"* (₹1 crore — ₹10 crore) / *"national"* (> ₹10 crore)
- `compensation_claimed_rupees` — the value of the consideration paid + the compensation claimed
- `deficiency_character` — *"deficiency-of-service"* / *"defect-in-goods"* / *"unfair-trade-practice"* / *"product-liability"* / *"medical-negligence"*
- `cause_of_action_date` — date the cause of action arose (for Section 69 limitation)
- `limitation_anchor` — Section 69 default; proviso-grounds where condonation is sought
- `territorial_jurisdiction_anchor` — opposite-party residence / cause-of-action / complainant residence per Section 34(2) / 47(4) / 58(2)
- `parties` — list of party-role + party-type + party-name-placeholder

Case-type-specific fields (for the relevant skill) layer on top of the minimum schema — see each case-type SKILL.md.

---

## Built-in compliance disciplines

The Verifier enforces several disciplines mandatory in Indian consumer-forum practice — see `skills/_drafting_common/SKILL.md` for the full discipline framework. Headline disciplines:

- **Statute currency** — Consumer Protection Act 2019 (NOT the repealed Consumer Protection Act 1986); *Commission* nomenclature (NOT the legacy *Forum* term that the 1986 Act used and the 2019 Act displaced); New Drugs and Clinical Trials Rules 2019 (NOT the Drugs and Cosmetics Rules 1945) for clinical-trial consent; CrPC 1973 references converted to BNSS 2023; IEA 1872 references converted to BSA 2023
- **Pecuniary-jurisdiction tier** — claim quantum cross-checked against the Section 34 / 47 / 58 thresholds (District ≤ ₹1 crore; State ₹1 crore — ₹10 crore; NCDRC > ₹10 crore — as amended by the Consumer Protection (Jurisdiction of the District Commission, the State Commission and the National Commission) Rules 2021; verify the current threshold before filing)
- **Territorial-jurisdiction anchor** — Section 34(2) / 47(4) / 58(2) tested (opposite-party residence / cause-of-action / complainant residence)
- **Section 69 limitation** — two years from cause-of-action; proviso-grounds for condonation pleaded with sufficient cause
- **Medical-negligence threshold discipline** — *Jacob Mathew v. State of Punjab* (2005) 6 SCC 1 modified-Bolam standard; *Martin F. D'Souza v. Mohd. Ishfaq* (2009) 3 SCC 1 expert-opinion safeguard at the threshold; *Kusum Sharma v. Batra Hospital* (2010) 3 SCC 480 balanced-standard caution; *Indian Medical Association v. V.P. Shantha* (1995) 6 SCC 651 service-character anchor; *Spring Meadows Hospital v. Harjol Ahluwalia* (1998) 4 SCC 39 vicarious-liability anchor; *Achutrao Haribhau Khodwa v. State of Maharashtra* (1996) 2 SCC 634 *res ipsa loquitur* discipline
- **Product-liability strand map** — Section 84 (manufacturer) / Section 85 (product service provider) / Section 86 (product seller); Section 87 exceptions pre-empted
- **Unfair-trade-practice ingredient map** — Section 2(47) eight categories; read with the Consumer Protection (E-Commerce) Rules 2020 and the Guidelines for Prevention and Regulation of Dark Patterns 2023
- **Appeal pre-deposit discipline** — Section 41 (District to State; 50% capped at ₹25,000 per current notification) / Section 51 (State to NCDRC; 50% capped at ₹50,000 per current notification) — verify against current notification before drafting
- **Order-execution discipline** — Sections 71 and 72; CPC modes of execution; Section 72 penalty (up to 3 years / ₹1 lakh / both)

---

## Privacy firewall — extra discipline for consumer / medical content

Consumer and medical-negligence pleadings contain some of the most sensitive material an advocate handles — patient medical records, treating-doctor identity, hospital admission details, prescription histories, billing statements, product purchase invoices, complainant identity, opposite-party manufacturer identity, claim quantum, expert-opinion contents. The plugin's privacy discipline is therefore stricter than the generic discipline of sibling plugins:

1. **Reader** substitutes every complainant name, every opposite-party name (treating doctor, hospital administrator, manufacturer, service provider, seller), every product name, every invoice number, every claim figure, every patient name, every medical-procedure particular, every prescription reference, and every complaint reference number with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw patient names or raw medical records.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

The user can verify the firewall by inspecting `case-facts.md` after the Reader runs — every party name appears as `[Complainant]` / `[OP-1]` / `[OP-2]`, every patient name as `[Patient-Placeholder]`, every product as `[Product-Placeholder]`. The mapping is in the header of the same file.

---

## Why MIT License

The MIT licence is the most permissive widely-recognised open-source licence. Anyone may use, modify, distribute, sublicense, or sell the plugin or any derivative. The licence is short, well-understood, and compatible with every other open-source licence the legal community is likely to encounter. No proprietary gating, no field-of-use restriction, no contributor licence agreement (CLA) gymnastics. The accompanying `NOTICE.md` does not modify the licence — it documents the provenance and the privilege position so that any future audit can verify the plugin's clean origin.

---

## Sibling plugins

This plugin is one in the **wolfgang_rush** family of Indian legal-drafting plugins. All thirteen siblings ship under the same six-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) and the family-of-plugins doctrine — each plugin narrowly scoped to one practice area / forum:

| Plugin | GitHub repo | Scope |
|---|---|---|
| `supreme-court-drafting` | [supreme-court-drafting-litigation](https://github.com/Wolfgangrush/supreme-court-drafting-litigation) | SLPs · Writ Art 32 · Transfer · Review · Curative — Supreme Court of India |
| `indian-hc-drafting` | [indian-hc-drafting-litigation](https://github.com/Wolfgangrush/indian-hc-drafting-litigation) | Pleadings across all 25 Indian High Courts (bench-config-aware) |
| `district-court-drafting` | [district-court-drafting-litigation](https://github.com/Wolfgangrush/district-court-drafting-litigation) | Plaints · WS · CPC applications · BNSS complaints across 25+ States (state-config) |
| `indian-family-drafting` | [indian-family-drafting-litigation](https://github.com/Wolfgangrush/indian-family-drafting-litigation) | HMA · SMA · IDA · matrimonial · custody · DV Act · maintenance · adoption |
| `indian-contracts-drafting` | [indian-contracts-drafting-litigation](https://github.com/Wolfgangrush/indian-contracts-drafting-litigation) | MSA · NDA · employment · lease · sale · GPA · SHA · will · loan · arbitration |
| `indian-banking-drafting` | [indian-banking-drafting-litigation](https://github.com/Wolfgangrush/indian-banking-drafting-litigation) | DRT · SARFAESI · NI Act 138 · IBC §7 / §95 · DRAT |
| `indian-labour-drafting` | [indian-labour-drafting-litigation](https://github.com/Wolfgangrush/indian-labour-drafting-litigation) | ID Act · POSH · PG · EPF · ESI · MW · IESO + State exemplars |
| `indian-property-drafting` | [indian-property-drafting-litigation](https://github.com/Wolfgangrush/indian-property-drafting-litigation) | Gift · Exchange · Release · Trust · Wakf · Easement · Partition · Settlement · Mortgage · TIR |
| `indian-company-drafting` | [indian-company-drafting](https://github.com/Wolfgangrush/indian-company-drafting) | NCLT (241/242 · 245 · 230-232 · 66 · 252 · 213) · NCLAT (421 + 61) · IBC §9 / §10 |
| `indian-tax-drafting` | [indian-tax-drafting](https://github.com/Wolfgangrush/indian-tax-drafting) | Form 35 CIT(A) · Form 36 ITAT · Form 10A · Sec 148A · 263/264 · 271/270A · 144C · 201 · 260A |
| `indian-consumer-drafting` (this) | [indian-consumer-drafting](https://github.com/Wolfgangrush/indian-consumer-drafting) | District / State / NCDRC + medical-negligence + product liability |
| `indian-mact-drafting` | [indian-mact-drafting](https://github.com/Wolfgangrush/indian-mact-drafting) | MV Act 1988 (2019 amended) · Sarla Verma + Pranay Sethi · state-config |
| `indian-ip-drafting` | [indian-ip-drafting](https://github.com/Wolfgangrush/indian-ip-drafting) | Copyright · Trade Marks · Patents · Designs + HC IP Divisions (post-IPAB-abolition) + Anton Piller / John Doe |

Each plugin can be installed independently, each plugin's Rule 36 firewall is narrow and reviewable, each plugin's bench / forum discipline is depth-validated within its scope, and the user installs only what they need.

---

## Why this exists

Indian consumer-protection practice currently has no open-source pleading-drafting infrastructure. The Consumer Protection Act 2019 replaced the 1986 Act, replaced *Forum* with *Commission*, restructured the pecuniary tiers, introduced a full product-liability scheme in Sections 82 to 87, codified mediation as a referral step under Section 37, brought e-commerce under express regulation through the Consumer Protection (E-Commerce) Rules 2020 + the Guidelines for Prevention and Regulation of Dark Patterns 2023, and changed the limitation rule (Section 69 — two years from the cause-of-action). A meaningful fraction of pleadings filed today still carry residual 1986-Act terminology, residual *Forum* references, residual mis-citation of repealed sections, and residual pecuniary-tier errors. A plugin that codifies the 2019-Act discipline plus the medical-negligence doctrine (*Jacob Mathew* / *Martin F. D'Souza* / *Kusum Sharma* / *V.P. Shantha*) plus the product-liability strand map plus the privacy firewall is the first piece of infrastructure that the Indian consumer-forum practice has had — the second piece is community contribution from advocates who file regularly in specific District / State / NCDRC benches and who deepen the bench-specific Practice Directions discipline.

Foreign legal-AI tools cannot fill this gap. The Consumer Protection Act 2019 is jurisdiction-specific; the medical-negligence threshold (the *Jacob Mathew* modified-Bolam standard) has Indian-specific contours; the pecuniary-tier amendments are issued by Indian notifications that foreign training data does not index at depth; the *Forum* → *Commission* nomenclature shift is an Indian doctrinal event that has no analogue in any other jurisdiction. The plugin opens that door.

---

## Roadmap

- [x] **v0.1.0-alpha (current)** — universal consumer-pleading skeleton + 10 case-type skills + 6-agent pipeline + privacy firewall + Verifier disciplines + 0 bench-specific exemplars
- [ ] **v0.1.x** — bug fixes, quality-gate iteration, language-register polish, formatting refinements driven by user feedback
- [ ] **v0.x onward** — bench-specific Practice Direction calibration deepening per District Commission / State Commission / NCDRC bench, additional case-type skills (mediation reference under Section 37 / class-action complaint under Section 38(11) / restraint application against unfair terms in standard-form contracts under Section 49(1)(b) + Section 59(1)(b) / class-action UTP complaint), and procedural-rule updates as they arrive
- [ ] **v1.0.0** — stable release after community-validated formatting and field-testing

Per-bench deep validation will arrive in the order advocates contribute.

---

## Contributing

Advocates with regular consumer-forum / medical-negligence / product-liability practice are invited to contribute bench-config calibration for the specific Commission they practise before. Open a GitHub issue with:

- Your practice Commission (e.g., *"District Consumer Disputes Redressal Commission, [bench city]"* / *"State Consumer Disputes Redressal Commission, Maharashtra"* / *"NCDRC New Delhi"*)
- Your Commission's Cause Title format
- Your Commission's case-number convention
- Your Commission's filing-counter conventions (annexure markers / index format / verification format)
- Recent Practice Directions issued by the Commission affecting pleading format

Pull requests are welcome with a one-paragraph explanation of the change and a reference to the Commission's rule or Practice Direction that justifies it.

This plugin is open source under MIT.

---

## Contact

Author and maintainer: **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa.

GitHub: <https://github.com/Wolfgangrush>

Issues raised with reproducible context are handled on a best-effort basis; this is an open-source contribution maintained outside the author's professional engagements and does not constitute a vehicle for legal services.

---

## Author and brand

The author is **Rushikesh R. Mahajan**, Advocate, practising before the High Courts of India. The plugin is published under the open-source brand **wolfgang_rush**, which is the author's publishing handle for legal-technology infrastructure. Personal accountability under the Advocates Act 1961 attaches to the author regardless of the use of a publishing handle.

---

## Provenance and privilege statement

See `NOTICE.md` for the full provenance + privilege + privacy + Rule 36 compliance statement. The short version:

- The plugin contains only universal procedural skeletons, formatting conventions, statutory references, and generic placeholders
- The plugin contains no specific client matter, no client communications, no client documents, no personal data of any data principal, and no tracking / telemetry / analytics
- The plugin is, in legal character, identical to a published consumer-protection-law textbook — procedural knowledge in machine-readable form
- The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961 and the Bar Council of India Rules

---

## Compliance posture — Supreme Court e-Committee AI framework

This plugin is **assistive drafting infrastructure**, not autonomous decision-making software. Its operational posture is aligned with the Supreme Court of India e-Committee's stated position on AI in legal work.

> *"AI and digital tools must be used as supportive instruments and should not be allowed to override judicial reasoning."*
>
> — **Justice Rajesh Bindal**, Judge, Supreme Court of India
> [*Judicial Process Re-engineering and Digital Transformation*](https://www.sci.gov.in/press-release-dated-april-12-2026/) conference, 11–12 April 2026
> Organised by the Supreme Court e-Committee in collaboration with the Department of Justice, Government of India.
> ([Coverage — Law Trend](https://lawtrend.in/ai-must-not-replace-judicial-reasoning-warns-supreme-court-justice-rajesh-bindal/))

The same posture underpins the Supreme Court's own AI infrastructure for the judiciary:

- **[SUPACE](https://www.drishtiias.com/daily-news-analysis/ai-portal-supace)** — *Supreme Court Portal for Assistance in Court Efficiency.* AI-enabled assistive tool launched on 6 April 2021 by then-CJI S.A. Bobde. Provides legal research, fact extraction, document review, and drafting assistance to judges and legal researchers. **By design, SUPACE is not a decision-making system** — it processes facts and surfaces them to the human user. The Supreme Court has recommended adoption across all Indian High Courts.

- **[SUVAS](https://www.drishtijudiciary.com/current-affairs/supreme-court-vidhik-anuvaad-software-suvas)** — *Supreme Court Vidhik Anuvaad Software.* AI-powered translation tool launched in November 2019 by then-CJI S.A. Bobde. Translates judicial documents, orders, and judgments between English and ten Indian regional languages.

### What this plugin does — and does not — do under that framework

**Does:**

- Generate structural skeletons of pleadings, drawing on public statutes, schedule forms, and court rules.
- Run a six-agent assistive pipeline (Reader → Formatter → Drafter → Verifier → Refiner → Overseer) over the user's case facts.
- Surface citations, procedural anchors, and bench-specific conventions for advocate review.

**Does NOT:**

- Generate final filings autonomously.
- Substitute for advocate professional judgment.
- Replace human verification.
- Operate without an enrolled advocate retaining full professional responsibility.

**Every draft produced through this plugin must be advocate-owned and human-verified before filing.** The enrolled advocate using this plugin retains full professional responsibility under the Advocates Act 1961 and the Bar Council of India Rules, including verification of facts, accuracy of citations, correctness of legal grounds, propriety of the prayer, and signature on every pleading filed.

This is the same standard the Supreme Court itself applies to its own AI infrastructure (SUPACE / SUVAS): **AI as supportive instrument, never as decision-maker.**

---

## Disclaimer and Bar Council of India Rule 36 compliance

This repository is published as a personal open-source contribution to the legal-technology ecosystem. It is **not** an advertisement of professional services, **not** a solicitation of work, **not** an undertaking to act as counsel in any matter, and **not** a vehicle through which the author accepts professional engagement.

Bar Council of India Rule 36 of the Standards of Professional Conduct and Etiquette prohibits an advocate from soliciting work or advertising professional services through any medium. This repository complies with Rule 36 in both letter and spirit:

- **No commercial engagement is offered through this repository.**
- No representation of professional results is made.
- No invitation to engage the author professionally is made.
- The README contains no contact details inviting professional retainer.

The plugin is published in the same legal character as any practitioner's open-source library, public continuing-legal-education contribution, or published textbook chapter — the medium is software, the content is procedural knowledge, the practitioner retains full Bar discipline and accountability.

---

## License

MIT — see `LICENSE`.
