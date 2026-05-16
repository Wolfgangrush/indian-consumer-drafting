---
name: district-commission-complaint-section-35-draft
description: Draft a Consumer Complaint before the District Consumer Disputes Redressal Commission under Section 35 of the Consumer Protection Act 2019. For an individual consumer / class of consumers (with leave under Section 35(1)(c)) / authorised consumer association seeking refund / replacement / compensation against a service provider / manufacturer / seller for deficiency in service / defective goods / unfair trade practice where the value of the consideration paid as goods or services does not exceed the District-Commission pecuniary limit (originally ₹1 crore under the 2019 Act; reduced to ₹50 lakh by the Consumer Protection (Jurisdiction of the District Commission, the State Commission and the National Commission) Rules 2021 — verify against latest notification). Encodes the Section 34 jurisdictional scheme (including the 2019 enlargement of complainant-residence ground at the District tier), the Section 35 manner-of-filing discipline, the Section 38 procedure-on-admission framework, and the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 procedural discipline. Auto-fires on "draft District Commission complaint", "draft consumer complaint District", "draft Section 35 complaint", "draft CC District Commission", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# District Commission Complaint (Section 35) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: CONSUMER COMPLAINT UNDER SECTION 35 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: DC_COMPLAINT
case_number_prefix: C.C.
pleading_type: Consumer Complaint
typical_forum: District Consumer Disputes Redressal Commission (territorial jurisdiction per Section 34(2) — opposite-party residence / cause of action / complainant residence)
typical_pecuniary_tier: value of consideration paid does not exceed the District-Commission limit (₹50 lakh per the 2021 Rules; verify current notification)
typical_parties: Complainant (individual consumer / class of consumers under Section 35(1)(c) / authorised consumer association) + Opposite Party No. 1 (service provider / manufacturer / seller) + further Opposite Parties as the deficiency chain requires
statutory_opening: "This Consumer Complaint is filed under Section 35 read with Section 34 of the Consumer Protection Act 2019 and the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020, for refund / replacement / compensation / costs against the Opposite Parties named above for the deficiency in service / defective goods / unfair trade practice particularised hereinafter."
deficiency_pleading_options:
  - "Deficiency of service under Section 2(11) — fault, imperfection, shortcoming, inadequacy in the quality, nature, manner of performance which is required to be maintained by or under any law in force or undertaken to be performed in pursuance of a contract, including any act of negligence, omission, commission, deliberate withholding of information."
  - "Defect in goods under Section 2(10) — fault, imperfection, shortcoming in the quality, quantity, potency, purity, standard which is required to be maintained."
  - "Unfair trade practice under Section 2(47) — pleaded by category (one of the eight categories), each ingredient particularised."
ground_clauses:
  - "Status as consumer — the Complainant is a 'consumer' within the meaning of Section 2(7) of the Consumer Protection Act 2019; the goods or services were purchased / hired for self-use and not for any commercial purpose (with the *earning livelihood by means of self-employment* exception per the Explanation, where applicable)."
  - "Pecuniary jurisdiction — the value of consideration paid as goods or services is ₹___; this is within the pecuniary jurisdiction of this Hon'ble District Commission per Section 34 read with the Consumer Protection (Jurisdiction) Rules 2021."
  - "Territorial jurisdiction — this Hon'ble Commission has territorial jurisdiction under Section 34(2) by reason of (a) the Opposite Parties / each Opposite Party residing or carrying on business or having a branch office within the local limits, OR (b) the cause of action wholly or in part arising within the local limits, OR (c) the Complainant residing or personally working for gain within the local limits (2019-Act enlargement at the District tier)."
  - "Cause of action crystallised on ____; specific event — final refusal by the Opposite Party to refund / replace / compensate / rectify (refer Annexure ___)."
  - "Limitation — the present Complaint is filed within two years from the date of cause of action per Section 69 of the Act."
prayer_clauses:
  - "(a) Direct the Opposite Parties to refund the consideration of ₹___ paid by the Complainant together with interest at ___% per annum from ____ till date of realisation;"
  - "(b) Direct the Opposite Parties to replace / repair the defective goods / re-render the deficient service to the Complainant's satisfaction;"
  - "(c) Direct the Opposite Parties to pay compensation of ₹___ to the Complainant under each head of pecuniary loss and non-pecuniary loss (mental agony, harassment, inconvenience, loss of opportunity) for the deficiency / defect / unfair trade practice;"
  - "(d) Direct the Opposite Parties to discontinue the unfair trade practice and not to repeat the same (where UTP is engaged), under Section 39(1)(b) of the Act;"
  - "(e) Award costs of ₹___ for these proceedings to the Complainant;"
mandatory_annexures:
  - identity_address_proof_of_complainant
  - invoice_or_receipt_or_admission_card_or_service_contract
  - warranty_or_undertaking_by_opposite_party_where_applicable
  - particulars_of_deficiency_defect_or_harm_event
  - pre_complaint_correspondence_with_proof_of_service
  - opposite_party_reply_where_received
  - expert_opinion_or_inspection_report_where_applicable
  - photographs_or_screenshots_of_defective_goods_or_service_evidence
  - bank_statements_or_payment_receipts_evidencing_consideration_paid
  - power_of_attorney_or_authorisation_letter_where_complainant_acts_through_an_agent
accompanying_applications:
  - "I.A. for interim relief under Section 38(9) of the Consumer Protection Act 2019 (where ad-interim direction is sought)"
  - "I.A. for condonation of delay under the proviso to Section 69 (where filed beyond two years; sufficient cause grounds to be particularised)"
  - "I.A. for exemption from filing certified copies"
  - "I.A. for urgent listing (where the deficiency is continuing and immediate relief is necessary)"
  - "I.A. for reference to mediation under Section 37 (optional, at the Complainant's election)"
  - "I.A. for ex-parte adjudication where the Opposite Party fails to appear despite service under Section 38(3)"
filing_fee: "Tiered fee under the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 — nil up to ₹5 lakh; ₹200 — ₹400 for ₹5 lakh — ₹50 lakh tier (verify against current notification). The Drafter computes the fee from `case-config.md` and reflects it in the Complaint."
```

## Section 35(1) filing-manner discipline

Section 35(1) of the 2019 Act permits filing by:

(a) The consumer to whom the goods are sold / delivered / agreed to be sold / delivered, OR to whom the services are rendered / agreed to be rendered;
(b) Any recognised consumer association — whether or not the consumer concerned is a member of that association;
(c) One or more consumers, where numerous consumers have the same interest, with the permission of the District Commission, on behalf of, or for the benefit of, all consumers so interested;
(d) The Central Government, the Central Authority, or the State Government;
(e) The legal heir or legal representative of the deceased consumer (in case of the death of a consumer).

The Drafter pleads the filing capacity (a)-(e) explicitly in the opening paragraph of Facts.

## Online-filing discipline (e-Daakhil)

The District Commissions accept online filing through the e-Daakhil portal (where operational in the State / Union Territory). The Drafter notes the filing mode in the case-config but the structural skeleton of the Complaint remains identical.

## Commercial-purpose firewall

Section 2(7) of the 2019 Act excludes from the definition of *consumer* any person who obtains goods or hires services for resale or for any commercial purpose. The Explanation carves out the *"earning livelihood by means of self-employment"* exception. The Drafter pleads the non-commercial-purpose anchor in the Facts paragraph on status, and where the exception is engaged, particularises the self-employment livelihood narrative with supporting annexures (registration / GST / income evidence at appropriate scale).
