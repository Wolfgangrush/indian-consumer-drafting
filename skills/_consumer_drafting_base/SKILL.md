---
name: _consumer_drafting_base
description: Universal Indian consumer-pleading skeleton. Shared base for all 10 case-type drafting skills. Holds the standard structure (Cause Title -> Memo of Parties -> Statutory Opening -> List of Dates -> Facts -> Deficiency / Defect / UTP / Product-Liability / Medical-Negligence pleadings -> Cause of Action -> Pecuniary and Territorial Jurisdiction -> Section 69 Limitation -> Prayer -> Verification -> Affidavit-in-support -> Index -> List of Documents -> accompanying applications). NOT invoked directly — extended by every case-type skill in this plugin.
allowed-tools: Read
---

# `_consumer_drafting_base` — universal Indian consumer-pleading skeleton

This base skill defines the **structural shape** of any consumer / medical-negligence / product-liability / unfair-trade-practice / consumer-appeal pleading drafted by the plugin. Case-type skills extend this base with case-type-specific statutory openings, fact-sequences, deficiency-pleading particulars, prayer clauses, and accompanying applications.

## Universal skeleton

```
1. CAUSE TITLE
   {{commission.name}}  ({{commission.tier}})
   {{case_type.case_number_prefix}} No. ____ of {{year}}

   {{memo_of_parties_block}}
   {{complainant_or_appellant_party}} ... {{complainant_role}}
                                  Versus
   {{opposite_party_or_respondent}} ... {{opposite_party_role}}

2. MEMO OF PARTIES
   For each party (Complainant + each Opposite Party): full name,
   age, occupation, address (residential / registered office /
   branch office / clinic / hospital), capacity (individual consumer
   / class of consumers / authorised representative / service
   provider / treating doctor / hospital / clinical establishment
   / product manufacturer / product service provider / product
   seller / e-commerce entity / statutory authority), authorised
   signatory designation (where the party is a body corporate or
   association).

3. STATUTORY OPENING
   {{case_type.statutory_opening}}

4. LIST OF DATES
   Chronological table from the first transaction to the date of
   filing:
   - Date of transaction / purchase / service engagement
   - Date of consideration paid
   - Date of first manifestation of deficiency / defect / harm
   - Date of pre-complaint notice (where issued)
   - Date of opposite-party reply (where received)
   - Date of expert-medical opinion (medical-negligence cases)
   - Date of cause of action
   - Date of filing

5. FACTS (numbered narrative paragraphs)
   5.1 Status of complainant — *consumer* under Section 2(7) of the
       Consumer Protection Act 2019; description of the transaction;
       confirmation that the goods or services were NOT purchased
       for commercial purpose (with the *"earning livelihood by
       means of self-employment"* exception where applicable per
       the Explanation to Section 2(7)) (refer Annexure A).
   5.2 Transaction — date of purchase / service engagement;
       consideration paid; mode of payment; invoice / receipt /
       admission card; warranty / undertaking by opposite party
       (refer Annexure B).
   5.3 Performance of opposite party — date-by-date narrative of
       the service rendered / product delivered (refer Annexure C).
   5.4 Deficiency / defect / harm event — date and particulars
       of the first manifestation; immediate response by the
       complainant (refer Annexure D).
   5.5 Pre-complaint correspondence — notices issued to the
       opposite party demanding rectification / refund / replacement
       / compensation; opposite-party response (or absence)
       (refer Annexure E).
   5.6 Expert opinion / inspection report (where applicable —
       medical-negligence cases; defective-goods cases requiring
       technical inspection) (refer Annexure F).
   5.7 Crystallisation of cause of action — the specific event
       that crystallised the present cause of action (e.g. final
       refusal by opposite party to refund / replace / compensate;
       discharge of the patient with sequelae; etc.).
   5.8 Continuing cause of action (where the deficiency persists
       and the cause of action is continuing).

6. DEFICIENCY / DEFECT / UTP / PRODUCT-LIABILITY /
   MEDICAL-NEGLIGENCE PLEADINGS (case-type-specific)
   {{case_type.deficiency_pleading}}
   (Each ingredient particularised with anchor to the Act / Rules
    and the supporting annexure.)

7. CAUSE OF ACTION
   Short paragraph identifying when the cause of action arose
   (with continuing-cause-of-action declaration where applicable),
   anchored to the date in `case-config.md`.

8. PECUNIARY JURISDICTION
   Paragraph stating the value of consideration paid as goods or
   services together with the compensation claimed, mapping to the
   Section 34 / 47 / 58 tier (per the Consumer Protection
   (Jurisdiction of the District Commission, the State Commission
   and the National Commission) Rules 2021 — verify current
   notification), and asserting that this Hon'ble Commission has
   the requisite pecuniary jurisdiction.

9. TERRITORIAL JURISDICTION
   Paragraph anchored to Section 34(2) / 47(4) / 58(2): the
   Commission has territorial jurisdiction by reason of
   (a) opposite-party residence / business / branch office, OR
   (b) cause of action wholly or in part arising within local
       limits, OR
   (c) complainant residence / personal work for gain (Section
       34(2) ONLY — District Commission enlargement under the
       2019 Act; NOT available at State / NCDRC tiers).

10. LIMITATION
    Section 69 — two years from cause-of-action date. Cause-of-
    action date: ____. Date of filing: ____. Days within limitation:
    ____. (Where filed beyond two years — proviso to Section 69
    invoked for condonation with sufficient cause; separate
    application annexed.)

11. PRAYER
    {{case_type.prayer_clauses}}

    And for such further and other reliefs as this Hon'ble
    Commission may deem fit and proper.

12. VERIFICATION
    I, [Complainant / Authorised Signatory], being the Complainant
    / the duly authorised signatory of the Complainant herein, do
    hereby verify that the contents of paragraphs ___ to ___ of
    the {{case_type.pleading_type}} are true to my personal
    knowledge and the contents of paragraphs ___ to ___ are true
    on the basis of information received and believed to be true.
    No part of this verification is false and nothing material has
    been concealed therefrom.

    Verified at [Place] on this __ day of [Month, Year].

                                       [Complainant / Authorised
                                        Signatory]

13. AFFIDAVIT-IN-SUPPORT
    I, [Complainant / Authorised Signatory], aged ___ years,
    occupation ___, residing at / having office at ___, do hereby
    solemnly affirm on oath and state as under:
    1. That I am the Complainant herein / the duly authorised
       signatory of the Complainant under [Board Resolution dated
       ____ at Annexure ___] [Power-of-Attorney dated ____ at
       Annexure ___], and am acquainted with the facts and
       circumstances of the case from personal knowledge / from
       the records.
    2. That I have read and understood the contents of the
       {{case_type.pleading_type}} comprising paragraphs 1 to ___
       and the same are true and correct.
    3. That the documents annexed are true copies / certified true
       copies of the originals available with the Complainant.

    Affirmed at [Place] on this __ day of [Month, Year].

                                       [Complainant / Authorised
                                        Signatory]

    Solemnly affirmed before me on solemn affirmation under the
    Bharatiya Sakshya Adhiniyam 2023.

                                       [Notary Public / Oath
                                        Commissioner / Commission
                                        Officer]

14. INDEX
    (Running paragraph-anchored index — paragraph numbers, content
    summary, annexure references.)

15. LIST OF DOCUMENTS / ANNEXURES
    Annexure A — Identity / address proof of the Complainant
    Annexure B — Invoice / receipt / admission card / contract
                  for service dated ____
    Annexure C — Warranty / undertaking by the opposite party
    Annexure D — Particulars of deficiency / defect / harm event
    Annexure E — Pre-complaint correspondence / notice issued to
                  the opposite party with proof of service
    Annexure F — Opposite-party reply (where received)
    Annexure G — Expert opinion / inspection report (where
                  applicable)
    Annexure H — Medical records / discharge summary / prescription
                  trail (medical-negligence cases)
    Annexure I — Billing statements / payment receipts
    Annexure J — Power-of-attorney / Board Resolution authorising
                  the filing (where applicable)
    Annexure K — Index of dates and events
    ... (further case-type-specific annexures)

16. ACCOMPANYING APPLICATIONS
    {{case_type.accompanying_applications}}
    (Common examples: application for interim relief under
    Section 38(9) of the Consumer Protection Act 2019; application
    for condonation of delay under the proviso to Section 69 with
    sufficient-cause grounds; application for exemption from filing
    certified copies; application for urgent listing; application
    for reference to mediation under Section 37; application for
    ex-parte adjudication where the opposite party fails to appear
    under Section 38(3); application for waiver of pre-deposit (in
    Section 41 / 51 appeals); application for stay of operation of
    the impugned order (in appeals).)
```

## Statute references the plugin handles

- Consumer Protection Act 2019 (CPA 2019)
- Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020
- Consumer Protection (Jurisdiction of the District Commission, the State Commission and the National Commission) Rules 2021
- Consumer Protection (E-Commerce) Rules 2020
- Consumer Protection (Direct Selling) Rules 2021
- Consumer Protection (Mediation) Rules 2020
- Guidelines for Prevention and Regulation of Dark Patterns 2023 (issued by the Central Consumer Protection Authority under Section 18)
- NCDRC (Practice and Procedure) Regulations
- Sale of Goods Act 1930 (cross-cited for defect-in-goods)
- Indian Contract Act 1872 (cross-cited for misrepresentation / breach of warranty)
- Indian Medical Council (Professional Conduct, Etiquette and Ethics) Regulations 2002 (medical-negligence cases)
- National Medical Commission Act 2019 (regulator framework)
- New Drugs and Clinical Trials Rules 2019 (clinical-trial consent)
- Clinical Establishments (Registration and Regulation) Act 2010 (where applicable in the State)
- NHRC / MoHFW Charter of Patients' Rights (2018 / 2021)
- Legal Metrology (Packaged Commodities) Rules 2011 (labelling compliance — product liability)
- Bharatiya Nagarik Suraksha Sanhita 2023 (procedural cross-citation)
- Bharatiya Nyaya Sanhita 2023 (perjury cross-citation Section 229)
- Bharatiya Sakshya Adhiniyam 2023 (electronic-records admissibility — Section 63 — for billing-statement printouts, e-commerce screenshots, email correspondence)
- Limitation Act 1963 (Article 136 for execution; cross-citation only)
- Code of Civil Procedure 1908 (Order 21 cross-citation for execution)
- Companies Act 2013 (registered-office / authorised-signatory references for body-corporate parties)
- Information Technology Act 2000 (cross-citation for e-commerce / electronic-records disputes)
- Specific-statute references for sector-specific consumer disputes (e.g. Real Estate (Regulation and Development) Act 2016 / Insurance Act 1938 / Electricity Act 2003 / Telecom Regulatory Authority of India Act 1997) — cited where the deficiency arises in a regulated-sector service


---

## v0.2.1 RENDER DISCIPLINE (load-bearing — Drafter must follow)

**Pandoc + reference.docx + post-pandoc fix script.** The Drafter writes Markdown using the heading discipline below. Pandoc converts the Markdown to `.docx` using the SHIPPED reference.docx at `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/reference.docx` — pre-customised with locked Word styles matching the filing-grade Bombay HC convention (extracted from an actual filed Second Appeal pleading):

- **Body (Normal)** — TNR 14pt, 1.5 line spacing, justified, 0.5cm first-line indent
- **Heading 1** — TNR 14pt **bold + centered** (NOT underlined) — for the Court / Forum / Tribunal header line and the case-number line
- **Heading 2** — TNR 14pt **bold + UNDERLINED + centered + letter-spacing** — for spaced section headers (`F A C T S`, `G R O U N D S`, `P R A Y E R`, `I N D E X`, `S Y N O P S I S`, `L I S T   O F   A N N E X U R E S`, `V E R I F I C A T I O N`)
- **Heading 3** — TNR 14pt **bold + UNDERLINED + centered** — for unspaced section headers (`SUBSTANTIAL QUESTIONS OF LAW`, `ACTS & RULES`, `CITATIONS`) and statutory opening (`WRIT PETITION UNDER ARTICLE 226 …`)
- **Heading 4** — TNR 14pt **bold + UNDERLINED + left-aligned** — for left-anchored bold-underlined headings (`MOST RESPECTFULLY SHEWETH:`)
- **Tables** — `tblLayout = fixed`; first row bold centered; cell margins locked

### Markdown heading mapping

| Markdown | Rendered as | Used for |
|---|---|---|
| `# Heading 1` | Bold centered (no underline) | Court header line; case-number line; cover-page anchors |
| `## Heading 2` | Bold centered UNDERLINED with letter-spacing | Spaced section headers (`## F A C T S`, `## G R O U N D S`, `## P R A Y E R`, `## I N D E X`, `## S Y N O P S I S`, `## L I S T   O F   A N N E X U R E S`, `## V E R I F I C A T I O N`) |
| `### Heading 3` | Bold centered UNDERLINED | Unspaced section headers + statutory opening |
| `#### Heading 4` | Bold left UNDERLINED | `#### MOST RESPECTFULLY SHEWETH:` |
| Body paragraph | TNR 14pt justified 1.5 spacing 0.5cm first-line indent | Everything else |
| `**Bold inline**` | Bold | Property descriptors / annexure markers / key terms inline within Facts narrative |

### Bold-number paragraph convention

Facts and Grounds paragraphs use **BOLD NUMBERS**: `**1.**`, `**2.**`, `**3.**` followed by a tab + body. Renders as the gold-standard pleading layout.

### Two-step pandoc command (Step 2 is NON-NEGOTIABLE)

```bash
# Step 1 — pandoc → .docx with locked Word styles
pandoc draft-v1.md -o draft-v1.docx \
  --reference-doc="${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/reference.docx" \
  --from=markdown+pipe_tables+raw_tex

# Step 2 — force table column widths
python3 "${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/fix_docx_tables.py" draft-v1.docx
```

Step 2 forces column widths on every table — 5-col (Sr.No / Annx / Particulars / Date / Pgs) = 8/8/60/14/10; 4-col = 10/10/65/15; 3-col = 10/75/15; 2-col Dates–Events = 18/82. Locks first-row bold + centered + vertically-centered cells. **Skipping the fix script reproduces the v0.2.0 Index-table defect (Sr.No / Annx columns stacking vertically).**

Do NOT auto-generate a fresh reference.docx in the case folder. Use the shipped one or a `<case-folder>/reference.docx` override.

### Cover-page discipline

INDEX, SYNOPSIS, LIST OF ANNEXURES each begin on a new page (`\newpage` in Markdown) and carry ONLY: forum header (`#`) + case-number line (`#`) + short cause-title (Petitioner short name `///VERSUS///` Respondent short name) + section header (`##`) + table + Counsel block. DO NOT repeat the full party address block on cover pages.

### Pipeline-optionality (advocate-cost discipline)

The full 6-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) is **NOT** mandatory. Only the first three stages are required to produce a filing-grade draft. Stages 4–6 are OPTIONAL QC layers the advocate explicitly invokes. Default exit point is here, after Drafter (~280K tokens). Full pipeline ~600K tokens — disproportionate for routine pleadings.

When `draft-v1.docx` is written, the Drafter's job is complete. The advocate decides whether to invoke the QC stages.
