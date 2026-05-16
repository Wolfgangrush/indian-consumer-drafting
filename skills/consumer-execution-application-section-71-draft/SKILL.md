---
name: consumer-execution-application-section-71-draft
description: Draft an Execution Application before the Consumer Disputes Redressal Commission (the Commission that passed the order) under Section 71 of the Consumer Protection Act 2019 for enforcement of the Commission's order as if it were a decree or order made by a court in a suit pending before it. Includes the alternative / additional remedy under Section 72 of the Act — penalty for non-compliance (imprisonment up to 3 years / fine ₹25,000 — ₹1 lakh / both) where the non-compliance is wilful. Uses the modes of execution prescribed by the Code of Civil Procedure 1908 (Section 51 + Order 21 — arrest and detention / attachment and sale / appointment of receiver / partition / specific delivery / cross-decree set-off / etc.) read with the proviso to Section 71(1) of the Consumer Protection Act 2019 (the Commission may forward the order for execution to the court within the local limits of whose jurisdiction the judgment-debtor resides or carries on business). Auto-fires on "draft consumer execution", "draft Section 71 execution", "draft consumer EA", "draft execution petition consumer", "draft consumer decree enforcement", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Consumer Execution Application (Section 71) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: EXECUTION APPLICATION UNDER SECTION 71 READ WITH SECTION 72 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: EXEC_APPLICATION
case_number_prefix: E.A.
pleading_type: Execution Application
typical_forum: The Consumer Disputes Redressal Commission (District / State / NCDRC) that passed the order being executed, OR the civil court to which the Commission has forwarded the order under the proviso to Section 71(1)
typical_parties: Decree-Holder (the party in whose favour the original Commission order was passed — typically the original Complainant) + Judgment-Debtor (the party against whom the original order was passed — typically the original Opposite Party)
statutory_opening: "This Execution Application is filed under Section 71 read with Section 72 of the Consumer Protection Act 2019, for execution of the order dated ____ of this Hon'ble Commission in [Consumer Complaint / First Appeal / Revision Petition] No. ____ of ____. The said order is enforceable as a decree of civil court per Section 71(1); the modes of execution are those prescribed by Section 51 and Order 21 of the Code of Civil Procedure 1908."
ground_clauses:
  - "Order being executed — the order dated ____ of this Hon'ble Commission directed the Judgment-Debtor to [refund / replace / compensate / discontinue / pay ₹___ / etc.] within ____ days of the order (refer Annexure A — certified copy of the impugned order)."
  - "Time for compliance has elapsed — ____ days from the date of the order have elapsed; the Judgment-Debtor has not complied (refer Annexure B — proof of service of the order + Annexure C — pre-execution notice issued to the Judgment-Debtor + Annexure D — Judgment-Debtor's reply or proof of non-reply)."
  - "Enforcement as decree — Section 71(1) — every order made by a District / State / National Commission may be enforced by it in the same manner as if it were a decree made by a court in a suit pending therein."
  - "Modes of execution — Section 51 read with Order 21 of the CPC 1908 — (a) delivery of any property specifically decreed; (b) attachment and sale or by sale without attachment of any property; (c) arrest and detention of the Judgment-Debtor in civil prison; (d) appointment of a Receiver; (e) such other manner as the nature of the relief granted may require."
  - "Wilful non-compliance and Section 72 — where the non-compliance is wilful, the Judgment-Debtor is liable under Section 72 to imprisonment for a term up to three years / fine of ₹25,000 — ₹1 lakh / both. [Particulars of wilfulness — if pleaded — service of notice / opportunity to comply / financial means demonstrated / pattern of non-compliance.]"
prayer_clauses:
  - "(a) Issue process under Section 71 read with the Code of Civil Procedure 1908 (Section 51 and Order 21) for execution of the order dated ____ of this Hon'ble Commission in [case number];"
  - "(b) Direct attachment of the bank accounts / movable assets / immovable property of the Judgment-Debtor particularised in Annexure ___ for satisfaction of the [refund / compensation / cost] amount of ₹___;"
  - "(c) After attachment, direct sale of the attached property and apply the sale proceeds to satisfaction of the amount executed;"
  - "(d) Where the Judgment-Debtor has wilfully disobeyed the order, initiate proceedings under Section 72 of the Consumer Protection Act 2019 and impose the penalty (imprisonment up to 3 years / fine ₹25,000 — ₹1 lakh / both);"
  - "(e) Where the relief executed is non-monetary (e.g. specific replacement / discontinuance of unfair trade practice), direct the Judgment-Debtor to perform the relief within a fixed time, with arrest-and-detention prayer in default;"
  - "(f) Award interest at ___% per annum on the amount executed from the date of the original order till date of realisation;"
  - "(g) Award costs of these execution proceedings to the Decree-Holder;"
mandatory_annexures:
  - certified_copy_of_the_order_being_executed
  - proof_of_service_of_the_order_on_the_judgment_debtor
  - pre_execution_notice_to_the_judgment_debtor_with_proof_of_service
  - judgment_debtor_reply_where_received_or_proof_of_non_reply
  - particulars_of_the_judgment_debtors_attachable_property_or_bank_accounts_where_known
  - bank_statements_of_the_decree_holder_evidencing_non_receipt_of_payment
  - power_of_attorney_or_authorisation_letter
accompanying_applications:
  - "I.A. for attachment before judgment under Order 38 of the CPC 1908 (where there is reasonable apprehension that the Judgment-Debtor may dissipate or alienate property)"
  - "I.A. for arrest and detention of the Judgment-Debtor under Order 21 Rule 37 of the CPC 1908 (in cases of wilful non-compliance)"
  - "I.A. for appointment of a Receiver under Order 40 of the CPC 1908 (where the property to be sold requires preservation)"
  - "I.A. for sale of attached property by public auction under Order 21 Rule 64 onwards"
  - "I.A. for transfer of the execution to the civil court within whose jurisdiction the Judgment-Debtor resides or carries on business under the proviso to Section 71(1)"
  - "I.A. for examination of the Judgment-Debtor under Order 21 Rule 41 of the CPC 1908 as to their property and means of satisfaction"
  - "I.A. for issuance of warrant of attachment / arrest"
filing_fee: "No separate filing fee under the Consumer Protection Act 2019 for an execution application before the Commission that passed the order. Where the order is forwarded to the civil court under the proviso to Section 71(1), the applicable State Court-Fees Act applies."
```

## Section 71 — execution as decree

Section 71(1) of the Consumer Protection Act 2019 makes every order of a District / State / National Commission enforceable as if it were a decree or order made by a court in a suit pending before it. The proviso permits the Commission to forward the order for execution to the court within the local limits of whose jurisdiction the Judgment-Debtor resides or carries on business (i.e., the civil court of competent territorial jurisdiction over the Judgment-Debtor).

Two execution paths are therefore available:

1. **Execution by the Commission itself** — the Decree-Holder files the Execution Application directly before the Commission that passed the order; the Commission applies Section 51 and Order 21 of the CPC 1908.
2. **Execution by transfer to a civil court** — where the Judgment-Debtor's assets are within the territorial jurisdiction of a different civil court, the Commission may forward the order to that court for execution.

The Drafter selects the path based on the location of the Judgment-Debtor's attachable assets.

## Section 72 — penalty for wilful non-compliance

Section 72 supplements the execution remedy with a penalty for wilful disobedience:

- Imprisonment for a term up to three years
- Fine of ₹25,000 — ₹1 lakh
- Both

The penalty is invoked where the non-compliance is *wilful*. The Drafter pleads wilfulness with particulars — typically: service of the order on the Judgment-Debtor; lapse of the time for compliance; pre-execution notice; financial means of the Judgment-Debtor demonstrating ability to comply; pattern of non-compliance across the Commission's directions.

## CPC modes of execution (Section 51 + Order 21)

The CPC modes of execution — applied by reference under Section 71(1) — are:

(a) **Delivery of property** — specific delivery of the property decreed (e.g., specific replacement of defective goods);
(b) **Attachment and sale** — attachment of the Judgment-Debtor's movable / immovable property and sale by public auction;
(c) **Arrest and detention** — civil-prison detention of the Judgment-Debtor (Order 21 Rule 37 onwards; safeguards under Section 51 proviso — the court must be satisfied that the Judgment-Debtor has the means to pay but is wilfully refusing);
(d) **Appointment of Receiver** — Order 40 CPC — where the property requires preservation pending execution;
(e) **Such other manner as the nature of the relief requires** — for non-monetary reliefs (discontinuance of unfair trade practice; corrective advertisement; recall of defective product), tailored execution directions.

The Drafter selects the appropriate modes and prays for them in the prayer block.

## Limitation discipline

Section 71 does not prescribe a separate limitation for execution. Article 136 of the Schedule to the Limitation Act 1963 (which prescribes 12 years for execution of any decree other than a decree for mandatory injunction) applies to the execution of a Commission's order. The Drafter computes the limitation from the date the order became enforceable (typically date of the original order, OR date of the appellate / revisional order if the order was carried in appeal / revision and the appellate / revisional order became final).
