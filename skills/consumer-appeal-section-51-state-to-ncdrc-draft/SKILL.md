---
name: consumer-appeal-section-51-state-to-ncdrc-draft
description: Draft a First Appeal from the State Consumer Disputes Redressal Commission to the National Consumer Disputes Redressal Commission (NCDRC) under Section 51 of the Consumer Protection Act 2019. For a party aggrieved by an order of the State Commission — whether the Complainant aggrieved by a dismissal / inadequate relief, or the Opposite Party aggrieved by an adverse finding / quantum direction. Encodes the 30-day limitation from the date of the order, the condonation-of-delay proviso to Section 51(1) for sufficient cause, the pre-deposit obligation under Section 51(2) where the appeal is against an order requiring payment of any amount (50% of that amount or ₹50,000 whichever is less — verify against current notification), and the NCDRC's appellate jurisdiction under Section 58(1)(a)(ii). Auto-fires on "draft State-to-NCDRC appeal", "draft Section 51 appeal", "draft consumer first appeal NCDRC", "draft FA NCDRC", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Consumer Appeal Section 51 (State-to-NCDRC) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: FIRST APPEAL UNDER SECTION 51 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: NCDRC_FIRST_APPEAL
case_number_prefix: F.A.
pleading_type: Memorandum of First Appeal
typical_forum: National Consumer Disputes Redressal Commission (appellate jurisdiction per Section 58(1)(a)(ii))
typical_parties: Appellant (party aggrieved by the State Commission's order) + Respondent (the other party / parties before the State Commission)
limitation: 30 days from the date of the order of the State Commission (Section 51(1)); condonation under the proviso to sub-section (1) for sufficient cause
pre_deposit: where the appeal is against an order requiring the appellant to pay any amount — 50% of that amount or ₹50,000, whichever is less (Section 51(2); verify against current notification); separate waiver application may be moved
statutory_opening: "This First Appeal is filed under Section 51 of the Consumer Protection Act 2019 against the order dated ____ of the State Consumer Disputes Redressal Commission, [State], in [Consumer Complaint / First Appeal] No. ____ of ____."
ground_clauses:
  - "Erroneous appreciation of facts — the State Commission has erred in [particulars by paragraph reference]."
  - "Misapplication of law — the State Commission has misapplied [Section / Rule / Regulation / decision of the Supreme Court or the NCDRC binding on it]."
  - "Procedural irregularity — the State Commission has [refused cross-examination / declined to consider an annexure / decided on a ground not pleaded / failed to consider an interim order / etc.]."
  - "Quantum miscalculation — the State Commission has [under-awarded / over-awarded contrary to the pleaded heads / wrongly computed interest / wrongly applied the multiplier in a personal-injury / medical-negligence case / etc.]."
  - "Limitation / jurisdiction — the State Commission has [wrongly held the complaint barred by limitation under Section 69 / wrongly assumed pecuniary or territorial jurisdiction]."
  - "Inconsistent finding — the State Commission has [recorded a finding inconsistent with its own earlier finding / inconsistent with the documentary evidence]."
prayer_clauses:
  - "(a) Set aside the impugned order dated ____ of the State Consumer Disputes Redressal Commission, [State], in [Consumer Complaint / First Appeal] No. ____ of ____;"
  - "(b) Pass such further order as this Hon'ble National Commission deems fit and proper, including (where the appellant is the Complainant) granting the reliefs originally claimed in the Complaint;"
  - "(c) Stay the operation of the impugned order pending disposal of this Appeal;"
  - "(d) Award costs of these proceedings to the Appellant;"
mandatory_annexures:
  - certified_copy_of_the_impugned_order_dated_____of_the_state_commission
  - copy_of_the_original_consumer_complaint_filed_before_the_district_commission_where_relevant
  - copy_of_the_consumer_complaint_or_first_appeal_filed_before_the_state_commission
  - copy_of_the_written_version_or_reply_filed_by_the_opposite_party
  - copies_of_documentary_evidence_filed_before_the_state_commission
  - copies_of_relevant_pleadings_or_evidence_recorded_in_the_state_commission_proceedings
  - pre_deposit_proof_under_section_51_2_where_applicable
  - power_of_attorney_or_authorisation_letter
accompanying_applications:
  - "I.A. for stay of operation of the impugned order pending disposal of the Appeal"
  - "I.A. for condonation of delay under the proviso to Section 51(1) (where filed beyond 30 days; sufficient cause particularised)"
  - "I.A. for waiver / reduction of pre-deposit under Section 51(2) proviso (where the pre-deposit obligation is engaged and the appellant seeks waiver)"
  - "I.A. for exemption from filing certified copies of certain documents"
  - "I.A. for urgent listing where stay of impugned order is necessary"
filing_fee: "Per NCDRC fee schedule; verify against current notification."
```

## Section 51 appeal — structural discipline

The Memorandum of First Appeal under Section 51 follows the same shape as a Section 41 appeal but is filed before the NCDRC. The Drafter follows the NCDRC Practice Direction discipline:

- Memo of Parties on a separate sheet
- Index with running paragraph anchors
- List of Dates immediately following the Cause Title
- Verification on a separate signed sheet
- Affidavit-in-support on a separate notarised sheet

## Pre-deposit computation rule (Section 51(2))

Where the appeal is against an order requiring the appellant to pay any amount, Section 51(2) requires the appellant to deposit 50% of that amount or ₹50,000, whichever is less (verify against current notification before drafting). The Drafter computes:

- Amount the appellant was directed to pay (from the impugned order)
- 50% of that amount
- ₹50,000
- Pre-deposit = lesser of the above two

The pre-deposit proof (challan / online-payment receipt) is annexed. Where waiver is sought, a separate application with grounds is moved.

## Limitation discipline

Section 51(1) limitation = 30 days from the date of the order of the State Commission. (Note: this is SHORTER than the 45-day Section 41 limitation — a common error in legacy templates is to apply 45 days at the State-to-NCDRC stage.) The Drafter computes:

- Date of the impugned order
- Date of filing of the appeal
- Days elapsed
- Within / beyond limitation
- Where beyond — condonation grounds anchored to the specific factual cause

## Cross-references to revisional jurisdiction (Section 67)

Where the order being challenged is NOT appellable under Section 51 (typically because it is an interlocutory order from which an appeal does not lie, or because the order suffers from jurisdictional / illegality / material-irregularity defect that requires supervisory rather than appellate intervention), the appropriate remedy is a Revisional Application under Section 67 — see `${CLAUDE_PLUGIN_ROOT}/skills/consumer-revisional-application-section-67-draft/SKILL.md`. The Drafter does not conflate the two — Section 51 is appellate and goes to the merits; Section 67 is supervisory and is confined to the three jurisdictional grounds.
