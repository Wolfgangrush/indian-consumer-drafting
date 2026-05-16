---
name: medical-negligence-complaint-draft
description: Draft a medical-negligence complaint before the appropriate Consumer Disputes Redressal Commission (District / State / NCDRC per the pecuniary tier of the compensation claimed) alleging deficiency of medical service under Section 2(11) of the Consumer Protection Act 2019 read with Section 2(42) (service definition that includes medical service per Indian Medical Association v. V.P. Shantha (1995) 6 SCC 651) and the Indian Medical Council (Professional Conduct, Etiquette and Ethics) Regulations 2002. For a patient (or legal heir of a deceased patient) seeking compensation against a treating doctor / hospital / clinical establishment / anaesthetist / surgeon / nursing-home / diagnostic centre / consulting physician for medical negligence causing harm, sequelae, prolonged morbidity, or death. Encodes the Jacob Mathew v. State of Punjab (2005) 6 SCC 1 modified-Bolam standard, the Martin F. D'Souza v. Mohd. Ishfaq (2009) 3 SCC 1 expert-opinion safeguard at the threshold, the Kusum Sharma v. Batra Hospital (2010) 3 SCC 480 balanced-standard caution, the V.P. Shantha service-character anchor, the Spring Meadows Hospital v. Harjol Ahluwalia (1998) 4 SCC 39 vicarious-liability anchor for hospitals, the Achutrao Haribhau Khodwa v. State of Maharashtra (1996) 2 SCC 634 res ipsa loquitur discipline, the IMC Regulations 2002 informed-consent / confidentiality / records anchors, the NHRC / MoHFW Charter of Patients' Rights (2018 / 2021) substantive list of rights, the Common Cause v. Union of India (2018) 5 SCC 1 Advance Medical Directives doctrine where end-of-life is in issue, and the New Drugs and Clinical Trials Rules 2019 where clinical-trial consent is in issue. Auto-fires on "draft medical negligence complaint", "draft medical neg complaint", "draft medical malpractice consumer", "draft hospital negligence", "draft doctor negligence", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Medical-Negligence Complaint Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: COMPLAINT FOR MEDICAL NEGLIGENCE / DEFICIENCY IN MEDICAL SERVICE UNDER SECTION 2(11) READ WITH SECTION 2(42) OF THE CONSUMER PROTECTION ACT 2019
case_short_code: MED_NEG_COMPLAINT
case_number_prefix: C.C.
pleading_type: Consumer Complaint
typical_forum: District / State Commission / NCDRC (selected by reference to the pecuniary tier of the compensation claimed — see _drafting_common pecuniary-tier rule)
typical_parties: Complainant (patient or legal heir of deceased patient) + Opposite Party No. 1 (treating doctor / surgeon / anaesthetist / consulting physician) + Opposite Party No. 2 (hospital / clinical establishment) + Opposite Party No. 3 (insurer of the hospital / professional-indemnity insurer of the doctor — where impleaded)
statutory_opening: "This Consumer Complaint for medical negligence is filed under Section 35 / 47 / 58 (per pecuniary tier) of the Consumer Protection Act 2019 read with Section 2(11) (deficiency) and Section 2(42) (service — which includes medical service rendered for consideration per Indian Medical Association v. V.P. Shantha (1995) 6 SCC 651) of the Act, and read with the Indian Medical Council (Professional Conduct, Etiquette and Ethics) Regulations 2002, for compensation against the Opposite Parties for the medical negligence / deficiency in medical service / breach of the standard of care particularised hereinafter."
ground_clauses:
  - "Status as consumer — Section 2(7); medical service for consideration is *service* under Section 2(42); the patient (or the patient's relative on behalf of the patient) paid consideration to the Opposite Parties; the V.P. Shantha (1995) inclusion of paid medical service within the Act."
  - "Pecuniary jurisdiction — value of consideration paid for medical service together with the compensation claimed is ₹___; this is within the [District / State / National] Commission tier."
  - "Territorial jurisdiction — Section 34(2) / 47(4) / 58(2) — by reason of (a) the Opposite Parties / any Opposite Party residing or carrying on business at the place where the medical procedure was performed, OR (b) the cause of action wholly or in part arising at the place of the procedure."
  - "Doctor-patient relationship and standard of care — the Opposite Party No. 1 (treating doctor) owed a duty of care to the Complainant patient; the standard of care is that which a medical professional of ordinary skill and competence in the same field would have exercised in similar circumstances; the Jacob Mathew v. State of Punjab (2005) 6 SCC 1 modified-Bolam standard."
  - "Breach of the standard of care — the Opposite Party No. 1 departed from the standard of care by [particulars — pre-procedure assessment failure / informed-consent failure / surgical technique failure / post-procedure monitoring failure / drug-dosage / drug-interaction failure / failure to obtain second opinion in serious cases / failure to refer / records-maintenance failure / etc.] (refer Annexures ___)."
  - "Expert medical opinion supporting the alleged breach — the Complainant has obtained expert medical opinion from [Expert-Opinion-Placeholder] (refer Annexure ___) per the Martin F. D'Souza v. Mohd. Ishfaq (2009) 3 SCC 1 threshold safeguard. (Where no expert opinion is supplied, the alternative anchor is res ipsa loquitur per Achutrao Haribhau Khodwa v. State of Maharashtra (1996) 2 SCC 634 — pleaded only where the facts permit.)"
  - "Causation — the breach proximately caused the harm / sequelae / prolonged morbidity / death of the patient. The Complainant pleads each link in the causation chain with the supporting medical record."
  - "Informed-consent deficit (where applicable) — the consent obtained was not informed in the sense of IMC Regulations 2002 Clause 7.16 read with the Supreme Court's Samira Kohli v. Prabha Manchanda (2008) 2 SCC 1 line on informed consent."
  - "Vicarious liability of the hospital (where the Opposite Party No. 2 hospital is impleaded) — Spring Meadows Hospital v. Harjol Ahluwalia (1998) 4 SCC 39 holds that a hospital is vicariously liable for the negligence of its nurses, junior doctors, and ancillary staff acting in the course of employment."
  - "Records-maintenance failure (where in issue) — IMC Regulations 2002 Clause 1.3.2 requires maintenance of medical records for 3 years from last entry; failure to produce records on demand is a deficiency in itself."
  - "Compensation under multiple heads — pecuniary loss (medical expenses already incurred, expected future medical expenses, loss of earning capacity, special damages) and non-pecuniary loss (pain and suffering, loss of amenities of life, mental agony of the patient and the family, loss of consortium where applicable, loss of expectation of life where the patient has died). Quantum calibrated per the Sarla Verma v. DTC (2009) 6 SCC 121 + Pranay Sethi v. Reshma (2017) 16 SCC 680 multiplier method (adapted from motor-vehicle jurisprudence for the loss-of-income head) and per the standing NCDRC line on non-pecuniary compensation in medical-negligence cases."
  - "Limitation — within two years from the date of cause of action per Section 69. Cause of action — date of discharge with sequelae / date of death of the patient / date of refusal to refund + compensate by the hospital, whichever is later (with continuing-cause-of-action declaration where applicable)."
prayer_clauses:
  - "(a) Direct the Opposite Parties jointly and severally to pay compensation of ₹___ to the Complainant under each of the following heads, particularised in Schedule A to the Complaint: (i) medical expenses already incurred — ₹___; (ii) expected future medical expenses — ₹___; (iii) loss of earning capacity — ₹___ (computed on the multiplier method); (iv) pain and suffering — ₹___; (v) loss of amenities — ₹___; (vi) mental agony — ₹___; (vii) loss of consortium (where applicable) — ₹___; (viii) loss of expectation of life (where the patient has died) — ₹___;"
  - "(b) Direct the Opposite Parties to pay interest at ___% per annum on the compensation amount from ____ till date of realisation;"
  - "(c) Direct the Opposite Parties to refund the consideration of ₹___ paid for the medical service that was deficient;"
  - "(d) Award costs of ₹___ for these proceedings;"
mandatory_annexures:
  - identity_address_proof_of_complainant
  - relationship_proof_where_complainant_is_legal_heir_of_deceased_patient
  - hospital_admission_card_with_admission_date
  - consent_form_for_procedure_with_signature_pages
  - operative_notes_or_procedure_notes_for_the_procedure
  - anaesthesia_record_where_applicable
  - discharge_summary_with_diagnosis_and_treatment_summary
  - prescription_trail
  - drug_administration_records
  - lab_test_reports_and_imaging_reports
  - billing_statements_and_payment_receipts
  - second_opinion_or_subsequent_treating_doctor_opinion_where_obtained
  - expert_medical_opinion_supporting_negligence_claim_per_martin_d_souza_safeguard
  - pre_complaint_correspondence_to_hospital_or_treating_doctor_with_proof_of_service
  - hospital_reply_where_received
  - death_certificate_where_patient_has_died
  - post_mortem_report_where_obtained
  - power_of_attorney_where_complainant_acts_through_agent
accompanying_applications:
  - "I.A. for interim relief under Section 38(9) — interim compensation pending adjudication, where the medical condition of the Complainant warrants urgent financial support"
  - "I.A. for production of medical records of the hospital under Section 38(2)(c) where the hospital has refused to release records"
  - "I.A. for appointment of an independent medical expert / medical board to opine on the standard of care under Section 38(2)(c)"
  - "I.A. for condonation of delay under the proviso to Section 69 (where filed beyond two years; common in medical-negligence cases due to prolonged treatment and emergence of sequelae)"
  - "I.A. for exemption from filing certified copies"
  - "I.A. for urgent listing"
  - "I.A. for reference to mediation under Section 37 (rarely opted in medical-negligence cases; the medical-negligence question typically requires adjudication on expert evidence)"
filing_fee: "Computed per the pecuniary tier — see District / State / NCDRC skill files."
```

## The Jacob Mathew / Martin F. D'Souza / Kusum Sharma threshold stack

A medical-negligence complaint must clear THREE threshold tests at the pleading stage (any of which, if unmet, will lead the Commission to dismiss / return the complaint at admission):

1. **Standard of care (Jacob Mathew)** — the standard is "ordinary skill of an ordinary competent man exercising that particular art". A mere error of judgment is not negligence. The doctor is not liable for failing to deliver the highest possible standard — only for failing to deliver ordinary competent skill.
2. **Expert opinion at threshold (Martin F. D'Souza)** — before issuing notice on a medical-negligence complaint, the Commission ought to obtain expert medical opinion supporting the negligence allegation. Practical implication — the Complainant should procure expert opinion BEFORE filing wherever the facts permit; the Drafter inserts a conspicuous note in the head of the deficiency-pleading section if `case-facts.md` records `expert_opinion_supplied: false`.
3. **Balanced standard (Kusum Sharma)** — Commissions must not second-guess medical judgment on a debatable question; the question is deviation from the standard of care, not the outcome.

The Drafter pleads each of these explicitly in the Grounds.

## Vicarious-liability anchor (Spring Meadows)

Where the hospital is impleaded, the doctrine of vicarious liability under Spring Meadows Hospital v. Harjol Ahluwalia (1998) 4 SCC 39 anchors the proposition that the hospital is liable for the negligence of nurses, junior doctors, anaesthetists, and ancillary staff acting in the course of employment. The Drafter pleads the employment relationship (employee / consultant) and the act-in-the-course-of-employment narrative.

## Res ipsa loquitur (Achutrao Haribhau Khodwa)

Where the facts are such that they speak for themselves — classic example: a foreign body (mop / instrument / suture material) left inside the patient post-operation — the doctrine of res ipsa loquitur shifts the burden to the defendant doctor / hospital to explain. Achutrao Haribhau Khodwa v. State of Maharashtra (1996) 2 SCC 634 is the anchor. The Drafter pleads res ipsa as a fallback / additional ground where the facts permit; res ipsa is NOT a substitute for the Martin F. D'Souza expert-opinion safeguard in marginal cases.

## Informed-consent doctrine (IMC 2002 + Samira Kohli)

Informed consent under IMC Regulations 2002 Clause 7.16 read with Samira Kohli v. Prabha Manchanda (2008) 2 SCC 1 requires that the patient be informed of:

- The diagnosis
- The nature and purpose of the proposed procedure
- The risks and benefits of the procedure
- Alternative treatments and their risks and benefits
- The consequences of not undergoing the procedure

A blank consent form is not informed consent. A consent obtained under duress (e.g., immediately before the procedure when the patient is sedated) is not informed consent. The Drafter pleads informed-consent deficit with particulars.

## Quantum calibration

For the loss-of-income head, the multiplier method from Sarla Verma v. DTC (2009) 6 SCC 121 and Pranay Sethi v. Reshma (2017) 16 SCC 680 (motor-vehicle compensation jurisprudence) is the established framework, adapted to medical-negligence cases. The Drafter presents the multiplier calculation in a Schedule A to the Complaint:

- Age of the patient at the time of injury / death
- Multiplier applicable (per Sarla Verma table)
- Annual income (with deduction for personal expenses where the patient has died — Pranay Sethi formula)
- Future-prospects increment per Pranay Sethi
- Resulting loss-of-income figure

For the non-pecuniary heads (pain and suffering, loss of amenities, mental agony, loss of consortium, loss of expectation of life), the NCDRC has developed a standing line of decisions; the Drafter cites the closest comparable decision from `<case-folder>/laws/`.

## Advance Medical Directives (Common Cause)

Where the medical-negligence complaint touches on end-of-life decisions, withdrawal of life-prolonging treatment, or non-honouring of a Living Will, Common Cause v. Union of India (2018) 5 SCC 1 is the anchor with the procedural-safeguard regime. The Drafter pleads the existence of the Living Will (where one exists) and the breach of the Common Cause safeguards.

## Clinical-trial consent (New Drugs and Clinical Trials Rules 2019)

Where the patient was enrolled in a clinical trial and consent is in issue, the operative regulation is the New Drugs and Clinical Trials Rules 2019 (Chapter V — Clinical Trial; Chapter VI — Bio-availability and Bio-equivalence Studies). The Drafter cites the 2019 Rules — NOT the legacy Schedule Y of the Drugs and Cosmetics Rules 1945, which has been substantially carried into the 2019 Rules.
