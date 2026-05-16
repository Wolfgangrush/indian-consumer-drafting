---
name: ncdrc-complaint-section-58-draft
description: Draft an original Consumer Complaint before the National Consumer Disputes Redressal Commission (NCDRC) under Section 58 of the Consumer Protection Act 2019. For an individual consumer / class of consumers / authorised consumer association seeking refund / replacement / compensation where the value of the consideration paid as goods or services exceeds the State-Commission pecuniary limit (originally ₹10 crore under the 2019 Act; reduced to ₹2 crore by the Consumer Protection (Jurisdiction) Rules 2021 — verify against latest notification). Encodes the Section 58 jurisdictional scheme (original + appellate + revisional), the NCDRC (Practice and Procedure) Regulations procedural discipline (Memo of Parties on a separate sheet, Index with running paragraph anchors, List of Dates immediately following the Cause Title), and the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 procedural discipline. Auto-fires on "draft NCDRC complaint", "draft NCDRC original complaint", "draft Section 58 complaint", "draft national commission complaint", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# NCDRC Original Complaint (Section 58) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: ORIGINAL CONSUMER COMPLAINT UNDER SECTION 58 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: NCDRC_ORIGINAL_COMPLAINT
case_number_prefix: C.C.
pleading_type: Consumer Complaint
typical_forum: National Consumer Disputes Redressal Commission, New Delhi (territorial jurisdiction per Section 58(2) — opposite-party residence / cause of action; NO complainant-residence ground at this tier)
typical_pecuniary_tier: value of consideration paid exceeds the State-Commission pecuniary limit (₹2 crore per the 2021 Rules) — verify against current notification
typical_parties: Complainant (typically a high-value individual consumer / class action of consumers / authorised consumer association) + Opposite Parties (typically a national or multi-State manufacturer / national builder / national service provider / national insurer / multi-State e-commerce entity)
statutory_opening: "This Consumer Complaint is filed under Section 58 of the Consumer Protection Act 2019 read with the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 and the National Consumer Disputes Redressal Commission (Practice and Procedure) Regulations, the value of the consideration paid as goods or services together with the compensation claimed exceeding the State-Commission pecuniary limit, for refund / replacement / compensation / costs against the Opposite Parties named above for the deficiency in service / defective goods / unfair trade practice particularised hereinafter."
ground_clauses:
  - "Status as consumer — Section 2(7); non-commercial purpose."
  - "Pecuniary jurisdiction — value of consideration paid as goods or services together with the compensation claimed is ₹___; this is within the original pecuniary jurisdiction of this Hon'ble National Commission per Section 58(1)(a)(i) read with the Consumer Protection (Jurisdiction) Rules 2021."
  - "Territorial jurisdiction — Section 58(2) — by reason of (a) the Opposite Parties / any Opposite Party residing or carrying on business or having a branch office in India, OR (b) the cause of action wholly or in part arising in India. (The complainant-residence ground is District-Commission-specific.)"
  - "Cause of action crystallised on ____."
  - "Limitation — within two years from cause of action per Section 69."
prayer_clauses:
  - "(a) Direct the Opposite Parties to refund the consideration of ₹___ together with interest at ___% per annum;"
  - "(b) Direct the Opposite Parties to replace / repair / re-render the deficient service;"
  - "(c) Direct the Opposite Parties to pay compensation of ₹___ under each head of pecuniary and non-pecuniary loss;"
  - "(d) Direct the Opposite Parties to discontinue the unfair trade practice (where UTP), under Section 59(1)(b); issue corrective advertisement under Section 59(1)(g); pay punitive damages under Section 59(1)(e) where appropriate;"
  - "(e) Award costs of ₹___;"
mandatory_annexures:
  - identity_address_proof_of_complainant
  - invoice_or_receipt_or_service_contract
  - warranty_or_undertaking_by_opposite_party
  - particulars_of_deficiency_defect_or_harm_event
  - pre_complaint_correspondence_with_proof_of_service
  - opposite_party_reply_where_received
  - expert_opinion_or_inspection_report_where_applicable
  - bank_statements_or_payment_receipts
  - power_of_attorney_or_authorisation_letter_where_applicable
  - regulator_correspondence_where_a_sectoral_regulator_is_involved
  - class_action_permission_application_where_Section_38_11_applies
accompanying_applications:
  - "I.A. for interim relief under Section 38(9) read with Section 59(1)(a)"
  - "I.A. for permission to maintain class action under Section 38(11) read with Section 35(1)(c)"
  - "I.A. for condonation of delay under the proviso to Section 69"
  - "I.A. for exemption from filing certified copies"
  - "I.A. for urgent listing"
  - "I.A. for reference to mediation under Section 37"
  - "I.A. for ex-parte adjudication where Opposite Party fails to appear despite service"
filing_fee: "Fee under Rule 7 of the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 (verify against current notification — typical NCDRC fee for above ₹2 crore tier is in the higher slab). The Drafter computes the fee from `case-config.md`."
```

## NCDRC Practice Direction discipline

The NCDRC (Practice and Procedure) Regulations require the following structural conventions:

- **Memo of Parties on a separate sheet** — listing every party in serial order with full address; failure leads to Registry return.
- **Index with running paragraph anchors** — every annexure marker in the body must correspond to an entry in the Index.
- **List of Dates immediately following the Cause Title** — chronological table from first transaction to date of filing.
- **Verification on a separate signed sheet** by the Complainant or authorised signatory.
- **Affidavit-in-support on a separate notarised sheet**.

The Format agent pre-applies these conventions to the format-shell.

## Section 59 — National Commission powers

Section 59 enumerates the powers of the National Commission on a finding of deficiency / defect / unfair trade practice (parallel to Section 49 for the State Commission). The prayer block engages the relevant sub-clauses.

## Cross-references to Section 67 revisional jurisdiction

The NCDRC also exercises revisional jurisdiction under Section 67 over orders of the State Commissions — see `${CLAUDE_PLUGIN_ROOT}/skills/consumer-revisional-application-section-67-draft/SKILL.md`. Section 58 covers ORIGINAL jurisdiction (where the pecuniary tier is engaged at the NCDRC level); Section 67 covers REVISIONAL jurisdiction (where the State Commission has acted with jurisdictional / illegality / material-irregularity defect). The skills are distinct.

## Class-action discipline (Section 38(11) read with Section 35(1)(c))

Where the Complaint is filed on behalf of a numerous class of consumers having the same interest, the Complainant must obtain the permission of the NCDRC under Section 38(11) read with Section 35(1)(c). A separate application for permission is moved with the Complaint, identifying:

- The class of consumers
- The commonality of interest
- The representative character of the Complainant
- Notice to the class (if directed by the Commission)

The Drafter pleads the class-action character in the opening Facts paragraph and annexes the permission application.
