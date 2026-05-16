---
name: consumer-appeal-section-41-district-to-state-draft
description: Draft a First Appeal from the District Consumer Disputes Redressal Commission to the State Consumer Disputes Redressal Commission under Section 41 of the Consumer Protection Act 2019. For a party aggrieved by an order of the District Commission — whether the Complainant aggrieved by a dismissal / inadequate relief, or the Opposite Party aggrieved by an adverse finding / quantum direction. Encodes the 45-day limitation from the date of the order, the condonation-of-delay proviso for sufficient cause, the pre-deposit obligation where the appeal is against an order requiring payment of any amount (50% of that amount or ₹25,000 whichever is less — verify against current notification), and the State-Commission appellate jurisdiction under Section 47(1)(a)(ii). Auto-fires on "draft District-to-State appeal", "draft Section 41 appeal", "draft consumer first appeal District", "draft FA State Commission", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Consumer Appeal Section 41 (District-to-State) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: FIRST APPEAL UNDER SECTION 41 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: SC_FIRST_APPEAL
case_number_prefix: F.A.
pleading_type: Memorandum of First Appeal
typical_forum: State Consumer Disputes Redressal Commission (appellate jurisdiction per Section 47(1)(a)(ii))
typical_parties: Appellant (party aggrieved by the District Commission's order) + Respondent (the other party / parties before the District Commission)
limitation: 45 days from the date of the order of the District Commission (Section 41); condonation under the proviso for sufficient cause
pre_deposit: where the appeal is against an order requiring the appellant to pay any amount — 50% of that amount or ₹25,000, whichever is less (verify against current notification); separate waiver application may be moved
statutory_opening: "This First Appeal is filed under Section 41 of the Consumer Protection Act 2019 against the order dated ____ of the District Consumer Disputes Redressal Commission, [Place], in Consumer Complaint No. ____ of ____."
ground_clauses:
  - "Erroneous appreciation of facts — the District Commission has erred in [particulars by paragraph reference to the impugned order]."
  - "Misapplication of law — the District Commission has misapplied [Section / Rule / Regulation] in that [particulars]."
  - "Procedural irregularity — the District Commission has [refused cross-examination / declined to consider an annexure / decided on a ground not pleaded / failed to consider an interim order / etc.]."
  - "Quantum miscalculation — the District Commission has [under-awarded compensation contrary to the pleaded heads / over-awarded compensation without basis / wrongly computed interest / etc.]."
  - "Limitation / jurisdiction — the District Commission has [wrongly held the complaint barred by limitation under Section 69 / wrongly assumed pecuniary or territorial jurisdiction]."
  - "Inconsistent finding — the District Commission has [recorded a finding inconsistent with its own earlier finding / inconsistent with the documentary evidence]."
prayer_clauses:
  - "(a) Set aside the impugned order dated ____ of the District Consumer Disputes Redressal Commission, [Place], in Consumer Complaint No. ____ of ____;"
  - "(b) Pass such further order in the Consumer Complaint No. ____ as this Hon'ble State Commission deems fit and proper, including (where the appellant is the Complainant) granting the reliefs originally claimed in the Complaint;"
  - "(c) Stay the operation of the impugned order pending disposal of this Appeal;"
  - "(d) Award costs of these proceedings to the Appellant;"
mandatory_annexures:
  - certified_copy_of_the_impugned_order_dated_____of_the_district_commission
  - copy_of_the_consumer_complaint_filed_before_the_district_commission
  - copy_of_the_written_version_or_reply_filed_by_the_opposite_party_before_the_district_commission
  - copies_of_documentary_evidence_filed_before_the_district_commission
  - copies_of_pleadings_or_evidence_recorded_in_the_district_commission_proceedings_where_relevant_to_the_grounds
  - pre_deposit_proof_where_pre_deposit_obligation_is_engaged
  - power_of_attorney_or_authorisation_letter
accompanying_applications:
  - "I.A. for stay of operation of the impugned order pending disposal of the Appeal"
  - "I.A. for condonation of delay under the proviso to Section 41 (where filed beyond 45 days; sufficient cause particularised)"
  - "I.A. for waiver / reduction of pre-deposit under the proviso (where the pre-deposit obligation is engaged and the appellant seeks waiver on grounds of financial hardship / merit of the appeal / etc.)"
  - "I.A. for exemption from filing certified copies of certain documents"
  - "I.A. for urgent listing where stay of impugned order is necessary to prevent irreversible prejudice"
filing_fee: "Appeal fee under the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 — typically a fixed slab; verify against current notification. The Drafter computes the fee."
```

## Section 41 appeal — structural discipline

The Memorandum of First Appeal is shorter and tighter than an original Complaint. The Drafter follows this structure:

1. Cause Title — State Commission, with case-number prefix *"F.A. No. ____ of 2026"*; Appellant vs Respondent block (with the Appellant's status as the Complainant or the Opposite Party in the original Complaint identified).
2. Appellate-jurisdiction statement — *"This appeal arises out of the order dated ____ of the District Consumer Disputes Redressal Commission, [Place], in Consumer Complaint No. ____ of ____. The instant appeal is filed under Section 41 of the Consumer Protection Act 2019 within the limitation prescribed therein."*
3. Brief facts of the original Complaint — 1-2 paragraphs summarising the original Complaint.
4. Brief findings of the District Commission — paragraph-by-paragraph reference to the impugned order with the operative findings cited.
5. Grounds of Appeal — numbered grounds, each anchored to a specific finding of the District Commission and a specific basis for impugnment.
6. Prayer.
7. Verification + Affidavit-in-support.
8. Annexures (with the certified copy of the impugned order as Annexure A — mandatory; subsequent annexures as required).

## Pre-deposit computation rule

Where the appeal is against an order requiring the appellant to pay any amount, Section 41 (proviso) requires the appellant to deposit 50% of that amount or ₹25,000, whichever is less (verify against current notification before drafting). The Drafter computes:

- Amount the appellant was directed to pay (from the impugned order)
- 50% of that amount
- ₹25,000
- Pre-deposit = lesser of the above two

The pre-deposit proof (challan / online-payment receipt) is annexed. Where waiver is sought, a separate application with grounds is moved.

## Limitation discipline

Section 41 limitation = 45 days from the date of the order of the District Commission. The Drafter computes:

- Date of the impugned order
- Date of filing of the appeal
- Days elapsed
- Within / beyond limitation
- Where beyond — condonation grounds with the Collector v. Mst. Katiji line on liberal construction of *sufficient cause*, anchored to the specific factual cause for the delay
