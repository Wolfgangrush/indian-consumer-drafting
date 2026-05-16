---
name: unfair-trade-practice-complaint-draft
description: Draft an Unfair Trade Practice (UTP) complaint before the appropriate Consumer Disputes Redressal Commission (District / State / NCDRC per pecuniary tier of compensation claimed and consideration paid) under Section 2(47) of the Consumer Protection Act 2019 read with Sections 49 (State Commission discontinuance power) and 59 (National Commission discontinuance power). Covers all eight Section 2(47) UTP categories — false representation (standard / quality / quantity / grade / composition / style / model), false representation of sponsorship / approval / performance, bargain-price falsity, gifts-or-prizes-with-intent-of-not-providing, contests / lotteries / games-of-chance for promotion, manufacture-of-spurious-goods, permitting-publication-of-false-or-misleading-advertisement, and sale-of-non-conforming-goods. Where the impugned conduct is in an e-commerce setting, read with the Consumer Protection (E-Commerce) Rules 2020 + Guidelines for Prevention and Regulation of Dark Patterns 2023 issued by the Central Consumer Protection Authority under Section 18. Auto-fires on "draft unfair trade practice complaint", "draft UTP complaint", "draft Section 2(47) complaint", "draft misleading advertisement complaint", "draft dark pattern complaint", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Unfair Trade Practice Complaint Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: COMPLAINT FOR UNFAIR TRADE PRACTICE UNDER SECTION 2(47) READ WITH SECTION 49 / 59 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: UTP_COMPLAINT
case_number_prefix: C.C.
pleading_type: Consumer Complaint (UTP)
typical_forum: District / State Commission / NCDRC (per pecuniary tier)
typical_parties: Complainant (individual consumer / class of consumers / authorised consumer association) + Opposite Party No. 1 (the entity adopting the UTP — manufacturer / service provider / seller / e-commerce platform / digital service provider) + further Opposite Parties (advertiser / publisher / endorser per Section 21 read with the CCPA's misleading-advertisement-endorser regime)
statutory_opening: "This Consumer Complaint is filed under Section 35 / 47 / 58 (per pecuniary tier) of the Consumer Protection Act 2019 read with Section 2(47) (definition of *unfair trade practice*) and Section 49(1)(b) / Section 59(1)(b) (power to direct discontinuance of unfair trade practice) of the Act, for compensation and corrective relief in respect of the unfair trade practice particularised hereinafter."
ground_clauses:
  - "Status as consumer — Section 2(7); non-commercial purpose."
  - "Category of UTP engaged — one of the eight categories under Section 2(47): [(i) false representation as to standard, quality, quantity, grade, composition, style, model / (ii) false representation that goods or services have sponsorship, approval, performance, characteristics, accessories, uses, or benefits which they do not have / (iii) bargain-price falsity / (iv) offering gifts, prizes, or other items with the intention of not providing them / (v) conduct of contests, lotteries, games of chance for promoting goods or services / (vi) manufacture of spurious goods or false grading / (vii) permitting publication of any advertisement of goods or services that is false or misleading / (viii) sale of goods that do not comply with mandatory standards]."
  - "Particulars of the impugned conduct — [particulars by date, by representation made, by the medium of representation, by the loss caused to the Complainant] (refer Annexure ___)."
  - "Where misleading advertisement engaged — particulars of the advertisement: date of publication, medium (print / television / radio / digital / out-of-home / direct mail / e-commerce platform), endorser identity (where the misleading-advertisement-endorser regime under Section 21 read with the CCPA Guidelines is engaged), the impugned representation, the comparator with the truth."
  - "Where e-commerce / dark-pattern engaged — particulars of the e-commerce platform; the impugned interface (sale-pressure pattern / forced action / interface interference / hidden cost / drip pricing / basket sneaking / confirm shaming / nagging / trick wording / SaaS billing / false urgency / disguised advertisement / bait-and-switch); the date of the interaction; the harm caused. Read with the Consumer Protection (E-Commerce) Rules 2020 + the Guidelines for Prevention and Regulation of Dark Patterns 2023."
  - "Causation — the impugned representation / conduct induced the Complainant to part with consideration / forgo a better alternative / suffer loss."
  - "Pecuniary and territorial jurisdiction — per the Section 34 / 47 / 58 tier and the territorial-jurisdiction anchor."
  - "Limitation — within two years from cause-of-action per Section 69."
prayer_clauses:
  - "(a) Direct the Opposite Parties to discontinue the unfair trade practice particularised hereinabove and not to repeat the same, under Section 39(1)(b) (District Commission) / Section 49(1)(b) (State Commission) / Section 59(1)(b) (National Commission);"
  - "(b) Direct the Opposite Parties to issue corrective advertisement under Section 18(2)(f) read with Section 49(1)(g) / Section 59(1)(g), at the expense of the Opposite Parties, in the same medium / scope / frequency as the impugned advertisement, for the period as this Hon'ble Commission directs;"
  - "(c) Direct the Opposite Parties to refund the consideration of ₹___ paid by the Complainant pursuant to the impugned representation, together with interest;"
  - "(d) Direct the Opposite Parties to pay compensation of ₹___ to the Complainant for the loss / injury suffered by reason of the impugned conduct, under Section 39(1)(d) / Section 49(1)(d) / Section 59(1)(d);"
  - "(e) Direct the Opposite Parties to pay punitive damages of ₹___ under Section 59(1)(e) (NCDRC only) where the unfair conduct was deliberate / repeated / against a numerous class of consumers;"
  - "(f) Award costs of ₹___;"
mandatory_annexures:
  - identity_address_proof_of_complainant
  - the_impugned_representation_or_advertisement_specimen
  - publication_proof_or_screenshot_with_date_and_timestamp_metadata
  - invoice_or_receipt_evidencing_consideration_paid_pursuant_to_the_representation
  - comparator_evidence_showing_the_truth_against_the_representation
  - independent_test_or_inspection_report_where_quality_or_conformity_is_in_issue
  - regulator_correspondence_or_compliant_filed_with_sectoral_regulator_where_applicable
  - pre_complaint_correspondence_with_the_opposite_party
  - opposite_party_reply_where_received
  - power_of_attorney_where_applicable
accompanying_applications:
  - "I.A. for interim relief under Section 38(9) — including direction to the Opposite Party to suspend the impugned advertisement / impugned interface / impugned offer pending adjudication"
  - "I.A. for joinder of additional Opposite Parties (publisher / endorser / e-commerce platform / payment gateway) under Section 38(2)(c)"
  - "I.A. for class-action permission under Section 38(11) where the impugned UTP affects a numerous class of consumers"
  - "I.A. for production of internal records of the Opposite Party (advertising contracts, endorser contracts, complaint-handling logs) under Section 38(2)(c)"
  - "I.A. for condonation of delay under the proviso to Section 69"
  - "I.A. for exemption from filing certified copies"
  - "I.A. for urgent listing"
filing_fee: "Per pecuniary tier."
```

## The eight UTP categories under Section 2(47)

| Cat. | Description | Typical evidence |
|---|---|---|
| (i) | False representation as to standard / quality / quantity / grade / composition / style / model | Specimen advertisement + comparator (independent test report / BIS specification / manufacturer's actual catalogue) |
| (ii) | False representation of sponsorship / approval / performance / characteristics / accessories / uses / benefits | Specimen advertisement + denial from purported sponsor / approver |
| (iii) | Bargain-price falsity | Advertisement claiming bargain price + the actual price at which the Opposite Party generally sells |
| (iv) | Gifts / prizes with intent of not providing | Promotional material + records of non-delivery to the Complainant / class |
| (v) | Contests / lotteries / games of chance for promotion | Contest rules + the Lotteries (Regulation) Act 1998 compliance shortfall where applicable |
| (vi) | Manufacture of spurious goods or false grading | Independent test report; BIS test certificate; sectoral-regulator confirmation |
| (vii) | Permitting publication of false / misleading advertisement | Specimen advertisement + comparator + (where endorser is impleaded) endorser identity and contract |
| (viii) | Sale of goods not conforming to mandatory standards | Sectoral-regulator notification of mandatory standard + non-conformity test report |

## E-commerce / dark-pattern overlay

For e-commerce UTP, read Section 2(47) with:

- **Consumer Protection (E-Commerce) Rules 2020** — duties of inventory / marketplace e-commerce entities; grievance-redressal officer requirement; flash-sale prohibition; price-manipulation prohibition; mandatory disclosures
- **Guidelines for Prevention and Regulation of Dark Patterns 2023** issued by the Central Consumer Protection Authority under Section 18 of the 2019 Act — defines 13 categories of dark pattern (false urgency / basket sneaking / confirm shaming / forced action / subscription trap / interface interference / bait and switch / drip pricing / disguised advertisement / nagging / trick question / SaaS billing / rogue malwares)
- **Information Technology Act 2000** — Section 43 (penalty for damage to computer) and Section 79 (intermediary safe harbour and its limits)
- The Drafter pleads the specific dark-pattern category engaged with screenshot evidence and time-stamp metadata.

## Misleading-advertisement-endorser regime

Section 21 of the Consumer Protection Act 2019 read with the CCPA Guidelines for Prevention of Misleading Advertisements and Endorsements 2022 makes endorsers liable for misleading endorsements where due-diligence was not exercised. Where the Complaint impleads an endorser, the Drafter pleads:

- The endorser's identity
- The endorser's representation in the advertisement
- The basis on which the endorser's representation was misleading
- The absence of due-diligence by the endorser
