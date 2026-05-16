---
name: consumer-revisional-application-section-67-draft
description: Draft a Revisional Application before the National Consumer Disputes Redressal Commission (NCDRC) under Section 67 of the Consumer Protection Act 2019, calling for the records of a State Commission and passing such order as the NCDRC thinks fit, where the State Commission has (a) exercised jurisdiction not vested in it by law, OR (b) failed to exercise jurisdiction vested in it, OR (c) acted in exercise of its jurisdiction illegally or with material irregularity. The revisional jurisdiction is supervisory in nature (Article 227-type discipline), distinct from the appellate jurisdiction under Section 51 (which goes to the merits). Use case — where the order being challenged is an interlocutory order from which an appeal does not lie, OR where the State Commission has committed a jurisdictional / illegality / material-irregularity defect that calls for supervisory rather than appellate intervention. Auto-fires on "draft NCDRC revisional", "draft Section 67 revision", "draft revision petition NCDRC", "draft RP NCDRC", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Consumer Revisional Application (Section 67) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: REVISIONAL APPLICATION UNDER SECTION 67 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: NCDRC_REVISIONAL
case_number_prefix: R.P.
pleading_type: Revision Petition
typical_forum: National Consumer Disputes Redressal Commission (revisional jurisdiction per Section 58 read with Section 67)
typical_parties: Petitioner (party aggrieved by the impugned order of the State Commission) + Respondent (the other party / parties before the State Commission)
revisional_grounds: limited to (a) State Commission has exercised jurisdiction not vested in it by law; OR (b) State Commission has failed to exercise jurisdiction vested in it; OR (c) State Commission has acted in exercise of its jurisdiction illegally or with material irregularity (Article 227-type discipline)
statutory_opening: "This Revisional Application is filed under Section 67 of the Consumer Protection Act 2019 against the order dated ____ of the State Consumer Disputes Redressal Commission, [State], in [Consumer Complaint / First Appeal / Application] No. ____ of ____."
ground_clauses:
  - "Section 67(a) — exercise of jurisdiction not vested — [particulars: e.g., the State Commission has assumed pecuniary jurisdiction over a matter that falls within the NCDRC tier per Section 58 / has assumed territorial jurisdiction not vested in it per Section 47(4) / has exercised appellate jurisdiction over an order from which no appeal lies]."
  - "Section 67(b) — failure to exercise jurisdiction vested — [particulars: e.g., the State Commission has refused to entertain an application under Section 38(9) for interim relief notwithstanding the statutory mandate / has refused to hear a class-action permission application]."
  - "Section 67(c) — exercise of jurisdiction illegally or with material irregularity — [particulars: e.g., the State Commission has decided the matter without considering the documentary evidence on record / has recorded a finding inconsistent with its own earlier finding without recording reasons / has refused cross-examination / has decided on a ground not pleaded by either party / has not given an opportunity of hearing on a material issue]."
  - "Distinction from appellate jurisdiction — the present Petition is filed in the revisional jurisdiction of this Hon'ble National Commission and is confined to the three jurisdictional grounds under Section 67. The Petitioner does not seek a re-appreciation of evidence or a merits review (which would lie in an appeal under Section 51 if the order were appellable)."
prayer_clauses:
  - "(a) Call for the records of [Consumer Complaint / First Appeal] No. ____ of ____ from the State Consumer Disputes Redressal Commission, [State];"
  - "(b) After examination of the records, set aside the impugned order dated ____ on the ground that the State Commission has exercised jurisdiction not vested in it / failed to exercise jurisdiction vested in it / acted in exercise of its jurisdiction illegally or with material irregularity;"
  - "(c) Remit the matter to the State Commission for fresh adjudication on merits in accordance with law (where appropriate) / Pass such further order as this Hon'ble National Commission deems fit (where the revisional intervention itself disposes of the underlying lis);"
  - "(d) Stay the operation of the impugned order pending disposal of this Revisional Application;"
  - "(e) Award costs of these proceedings to the Petitioner;"
mandatory_annexures:
  - certified_copy_of_the_impugned_order_dated_____of_the_state_commission
  - copy_of_the_original_pleadings_filed_before_the_state_commission
  - copy_of_the_orders_relevant_to_the_revisional_grounds_being_invoked
  - documentary_evidence_relevant_to_the_jurisdictional_or_illegality_or_irregularity_ground
  - power_of_attorney_or_authorisation_letter
accompanying_applications:
  - "I.A. for stay of operation of the impugned order pending disposal of the Revisional Application"
  - "I.A. for condonation of delay (where filed beyond a reasonable time; Section 67 itself does not prescribe a fixed limitation — but the NCDRC has applied a reasonable-time discipline)"
  - "I.A. for exemption from filing certified copies of certain documents"
  - "I.A. for urgent listing"
filing_fee: "Per NCDRC (Practice and Procedure) Regulations fee schedule; verify against current notification."
```

## Section 67 — the three grounds, no more, no less

Section 67 confines the NCDRC's revisional jurisdiction to three grounds — drawn from the same conceptual well as Article 227 of the Constitution and Section 115 of the CPC 1908:

(a) **Exercise of jurisdiction not vested** — the State Commission has decided a matter that was beyond its competence. Examples — assuming pecuniary jurisdiction over a matter falling within the NCDRC tier; assuming territorial jurisdiction not anchored to Section 47(4); deciding an appeal from an order from which no appeal lay.

(b) **Failure to exercise jurisdiction vested** — the State Commission has refused to entertain a matter that fell within its competence. Examples — refusing to entertain an interim-relief application under Section 38(9); refusing to hear a class-action permission application.

(c) **Acting in exercise of jurisdiction illegally or with material irregularity** — the State Commission has decided a matter within its competence but the manner of decision is vitiated by illegality / material irregularity. Examples — failing to consider documentary evidence; recording inconsistent findings without reasons; refusing cross-examination; deciding on a ground not pleaded; failure to give opportunity of hearing.

Re-appreciation of evidence does NOT fall within Section 67 — that lies in an appeal under Section 51 (where the order is appellable). The Drafter does not blur this distinction.

## Limitation discipline

Section 67 itself does not prescribe a fixed limitation period. The NCDRC has, in a standing line of decisions, applied a reasonable-time discipline (typically 90 days from the date of the impugned order, mirroring the CPC Article 124 limitation for a revision petition). Where the Revisional Application is filed beyond this reasonable time, a condonation-of-delay application is moved with sufficient cause.

## Practical note

Where the matter falls within both Section 51 (appellate) and Section 67 (revisional) — e.g., a final order of a State Commission in original jurisdiction that is appellable — the Petitioner ordinarily chooses Section 51. Section 67 is invoked where Section 51 is unavailable (interlocutory order; non-appellable matter) OR where the defect in the order is squarely jurisdictional / illegality-grade and the Petitioner does not seek a merits re-appreciation.
