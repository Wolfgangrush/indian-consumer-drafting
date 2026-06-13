---
name: state-commission-complaint-section-47-draft
description: Draft an original Consumer Complaint before the State Consumer Disputes Redressal Commission under Section 47 of the Consumer Protection Act 2019. For an individual consumer / class of consumers / authorised consumer association seeking refund / replacement / compensation against a service provider / manufacturer / seller where the value of the consideration paid as goods or services exceeds the District-Commission limit but is within the State-Commission limit (originally ₹1 crore — ₹10 crore under the 2019 Act; reduced to ₹50 lakh — ₹2 crore by the Consumer Protection (Jurisdiction) Rules 2021 — verify against latest notification). Encodes the Section 47 jurisdictional scheme (original + appellate + revisional), the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 procedural discipline, and the State-Commission circuit-bench architecture where applicable. Auto-fires on "draft State Commission complaint", "draft State Commission original complaint", "draft Section 47 complaint", "draft SC complaint", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# State Commission Complaint (Section 47) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: ORIGINAL CONSUMER COMPLAINT UNDER SECTION 47 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: SC_ORIGINAL_COMPLAINT
case_number_prefix: C.C.
pleading_type: Consumer Complaint
typical_forum: State Consumer Disputes Redressal Commission (territorial jurisdiction per Section 47(4) — opposite-party residence / cause of action; NO complainant-residence ground at this tier)
typical_pecuniary_tier: value of consideration paid exceeds the District-Commission limit (₹50 lakh per the 2021 Rules) but does not exceed the State-Commission limit (₹2 crore per the 2021 Rules) — verify against current notification
typical_parties: Complainant (individual consumer / class of consumers / authorised consumer association) + Opposite Parties as the deficiency chain requires (typically a Bank / insurer / builder / large service provider / national manufacturer at this tier)
statutory_opening: "This Consumer Complaint is filed under Section 47 of the Consumer Protection Act 2019 read with the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020, the value of the consideration paid as goods or services together with the compensation claimed exceeding the District-Commission pecuniary limit but not exceeding the State-Commission pecuniary limit, for refund / replacement / compensation / costs against the Opposite Parties named above for the deficiency in service / defective goods / unfair trade practice particularised hereinafter."
ground_clauses:
  - "Status as consumer — Section 2(7); non-commercial purpose."
  - "Pecuniary jurisdiction — value of consideration paid as goods or services together with the compensation claimed is ₹___; this is within the original pecuniary jurisdiction of this Hon'ble State Commission per Section 47(1)(a)(i) read with the Consumer Protection (Jurisdiction) Rules 2021."
  - "Territorial jurisdiction — Section 47(4) — by reason of (a) the Opposite Parties / any Opposite Party residing or carrying on business or having a branch office within the local limits of this Hon'ble State, OR (b) the cause of action wholly or in part arising within the local limits of this Hon'ble State. (The complainant-residence ground under Section 34(2) is District-Commission-specific and is NOT available at the State Commission tier.)"
  - "Cause of action crystallised on ____."
  - "Limitation — within two years from cause of action per Section 69."
prayer_clauses:
  - "(a) Direct the Opposite Parties to refund the consideration of ₹___ together with interest at ___% per annum;"
  - "(b) Direct the Opposite Parties to replace / repair the defective goods / re-render the deficient service;"
  - "(c) Direct the Opposite Parties to pay compensation of ₹___ under each head of pecuniary and non-pecuniary loss;"
  - "(d) Direct the Opposite Parties to discontinue the unfair trade practice and not to repeat the same (where UTP), under Section 49(1)(b) of the Act, and to issue corrective advertisement under Section 49(1)(g);"
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
accompanying_applications:
  - "I.A. for interim relief under Section 38(9) read with Section 49(1)(a)"
  - "I.A. for condonation of delay under the proviso to Section 69"
  - "I.A. for exemption from filing certified copies"
  - "I.A. for urgent listing"
  - "I.A. for reference to mediation under Section 37"
  - "I.A. for ex-parte adjudication where Opposite Party fails to appear despite service"
filing_fee: "Tiered fee under the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 (verify against current notification — typical State-Commission fee for the ₹50 lakh — ₹2 crore tier is ₹2,000 — ₹4,000). The Drafter computes the fee from `case-config.md`."
```

## State Commission circuit-bench discipline

Several State Commissions operate through circuit benches (e.g., Maharashtra State Commission has circuit benches at Aurangabad / [bench city] / Pune in addition to the principal bench at Mumbai). The Drafter selects the circuit bench by reference to the territorial-jurisdiction anchor in `case-config.md`. Where the circuit bench is not in regular session, the Complaint is filed at the principal bench with a request for transfer to the circuit bench under Section 47(1)(c).

## Section 49 — State Commission powers

Section 49 enumerates the powers of the State Commission on a finding of deficiency / defect / unfair trade practice:

(a) Direct return of price paid + compensation
(b) Direct discontinuance of unfair / restrictive trade practice + non-repetition
(c) Direct removal of defect / deficiency
(d) Direct issuance of corrective advertisement
(e) Direct payment of punitive damages where appropriate
(f) Such further order as deemed fit

The prayer block engages the (a)-(f) menu by the specific reliefs the complainant seeks.

## Cross-references to NCDRC original jurisdiction

Where the value of consideration paid + compensation claimed exceeds the State-Commission limit, the Complaint must be filed before the NCDRC under Section 58 — see `${CLAUDE_PLUGIN_ROOT}/skills/ncdrc-complaint-section-58-draft/SKILL.md`. A pecuniary mis-alignment is a fatal defect at the filing counter.
