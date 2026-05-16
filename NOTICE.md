# NOTICE — Provenance and Privilege Statement

This document is part of the public release of the `indian-consumer-drafting` plugin (v0.1.0-alpha and onwards). It declares the provenance of the plugin's content, in order to address any question about advocate-client privilege, client confidentiality, professional ethics, personal-data protection, and commercial confidentiality that may be raised by any reader, complainant, regulator, or Bar Council disciplinary authority.

The plugin is **case-config-aware**: the universal structural skeleton of any Indian consumer-forum pleading is uniform, and the parties' chosen Commission tier (District Consumer Disputes Redressal Commission for claims up to ₹1 crore, State Consumer Disputes Redressal Commission for claims of ₹1 crore to ₹10 crore, National Consumer Disputes Redressal Commission for claims exceeding ₹10 crore), pecuniary jurisdiction, territorial jurisdiction, the deficiency-of-service / defect-in-goods / unfair-trade-practice / product-liability / medical-negligence character of the dispute, the limitation anchor under Section 69 of the Consumer Protection Act 2019, and the accompanying-application set are supplied by the user via a `case-config.md` file in the case folder.

This NOTICE is published in plain language so that any reader — practising advocate, judge, Bar Council officer, regulator, member of the public, fellow developer — can understand the position without ambiguity.

---

## 1. What this plugin contains

This plugin contains the following categories of content, and **only** the following categories of content:

(a) **Universal consumer-pleading skeleton** — the structural shape of any Indian Consumer Disputes Redressal Commission complaint, appeal, revisional application, or execution application (Cause Title with correct Commission nomenclature under the Consumer Protection Act 2019, Memo of Parties, Statutory Opening invoking the operative section, List of Dates, Facts, Deficiency / Defect / Unfair-Trade-Practice / Product-Liability / Medical-Negligence pleadings, Cause of Action, Pecuniary and Territorial Jurisdiction, Limitation, Prayer, Verification, Affidavit-in-support, Index, List of Documents, accompanying applications).

(b) **Formatting conventions** — text-formatting conventions for pleadings before the District Consumer Disputes Redressal Commissions, the State Consumer Disputes Redressal Commissions, and the National Consumer Disputes Redressal Commission, as prescribed by the Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020 and the NCDRC (Practice and Procedure) Regulations.

(c) **Statutory references** — citations to public statutes (Consumer Protection Act 2019, Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020, Consumer Protection (E-Commerce) Rules 2020, Sale of Goods Act 1930, Indian Contract Act 1872, Indian Medical Council (Professional Conduct, Etiquette and Ethics) Regulations 2002, New Drugs and Clinical Trials Rules 2019, Clinical Establishments (Registration and Regulation) Act 2010, NHRC / MoHFW Charter of Patients' Rights 2018-2021, Bharatiya Nagarik Suraksha Sanhita 2023, Bharatiya Sakshya Adhiniyam 2023, Limitation Act 1963, Code of Civil Procedure 1908, applicable State Court-Fees Acts).

(d) **Procedural rule references** — citations to public rules (Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020, Consumer Protection (Salary, Allowances and other Terms and Conditions of Service of President and Members of the State Commission and District Commission) Rules 2020, Consumer Protection (E-Commerce) Rules 2020, Consumer Protection (Direct Selling) Rules 2021, Consumer Protection (Mediation) Rules 2020, NCDRC (Practice and Procedure) Regulations, and any further Regulations issued under Section 75 of the Act).

(e) **Generic placeholders** — every variable in every template is a placeholder (`[Complainant]`, `[Opposite Party No. 1 — Service Provider]`, `[Opposite Party No. 2 — Manufacturer]`, `[Opposite Party No. 3 — Treating Doctor]`, `[Opposite Party No. 4 — Hospital]`, `[Date of Purchase]`, `[Invoice No.]`, `[Product Description]`, `[Cause of Action Date]`, `[Date of Medical Procedure]`, `[Discharge Summary Date]`, `[Compensation Claimed]`). No placeholder is filled with any specific complainant, service-provider, manufacturer, doctor, hospital, patient, product, invoice particulars, medical-procedure particulars, or any other identifying information.

(f) **Anti-hallucination and privacy-firewall workflow** — six agents (Reader, Format, Drafter, Verifier, Refiner, Overseer) that operate on a case folder supplied by the user. The plugin itself contains no case folder. The Reader substitutes every party name, every key person (treating doctor, attending nurse, hospital administrator), every product name, every invoice number, every claim figure, and every complaint reference number with placeholders before downstream AI processing.

---

## 2. What this plugin does NOT contain

This plugin does **not** contain any of the following, and has never contained any of the following at any point in any committed version:

(a) **No specific client matter or consumer case.** No client of the author, and no specific consumer dispute or medical-negligence proceeding handled by the author or any client, appears in the plugin — by name, by complaint number, by invoice reference, by product identifier, by hospital name, by treating-doctor name, by patient name, by claim quantum, or by any other identifying signature.

(b) **No client communications.** No oral or written communication made to the author by or on behalf of any client (whether a complainant consumer, an opposite-party service provider, a manufacturer, a hospital, a treating doctor, or any other party) appears in the plugin in any form.

(c) **No client documents.** No document or instrument with which the author has become acquainted in the course of professional employment as an advocate appears in the plugin, in original, in redacted, in summary, in extract, or in pattern. This includes — but is not limited to — purchase invoices, warranty cards, service contracts, hospital admission forms, discharge summaries, medical records, prescriptions, clinical-trial consent forms, billing statements, refund notices, replacement notices, expert opinions, and inter-party correspondence in any specific consumer matter.

(d) **No personal data of any data principal.** The plugin processes no personal data, collects no personal data, stores no personal data. The Reader's privacy firewall ensures that any personal data in the user's local case folder is substituted with placeholders before downstream AI processing.

(e) **No specific power-of-attorney, no specific authorisation letter** of any specific complainant, service provider, manufacturer, hospital, or doctor handled by the author or any other advocate.

(f) **No client list, no panel-counsel list of any insurer, no chamber list, no associate list, no opposing-counsel list, no Member-specific intelligence of any District or State Commission or the NCDRC.**

(g) **No tracking, no telemetry, no analytics, no opt-in error reporting, no login, no account, no cloud sync.** The plugin runs entirely on the user's machine. The author receives no information about who installs the plugin, who uses it, on what cases, with what consideration, with what outcomes.

---

## 3. The legal distinction

Indian law has long recognised a clear distinction between two categories:

(i) **Specific client communications and documents** — protected under Section 132 of the Bharatiya Sakshya Adhiniyam 2023 (formerly Section 126 of the Indian Evidence Act 1872) and under Rule 17 of the Bar Council of India Standards of Professional Conduct and Etiquette. This category is privileged and confidential.

(ii) **General professional knowledge of consumer-protection law, medical-negligence jurisprudence, and pleading craft** — an advocate's accumulated knowledge of how a complaint under Section 35 of the Consumer Protection Act 2019 is structured, how a medical-negligence complaint is pleaded to survive the *Jacob Mathew v. State of Punjab* (2005) 6 SCC 1 / *Martin F. D'Souza v. Mohd. Ishfaq* (2009) 3 SCC 1 / *Kusum Sharma v. Batra Hospital* (2010) 3 SCC 480 threshold, what *Indian Medical Association v. V.P. Shantha* (1995) 6 SCC 651 holds about medical service as "service" under the Act, what the product-liability scheme under Sections 82 to 87 of the 2019 Act prescribes, how the limitation under Section 69 is computed, what the pecuniary-jurisdiction tier under Sections 34 / 47 / 58 of the 2019 Act prescribes (as amended by the Consumer Protection (Jurisdiction of the District Commission, the State Commission and the National Commission) Rules 2021 — verify the current threshold). This category is the advocate's own professional knowledge. It is not the property of any specific client. It is not privileged.

This plugin operates **entirely within category (ii)**.

Every Indian advocate accumulates this knowledge through years of practice, through study of Avtar Singh's *Law of Consumer Protection*, Universal's *Consumer Protection Law and Practice*, the standard commentaries on the Consumer Protection Act 2019, the NCDRC's published precedent and Practice Directions, and the case-law of the Supreme Court and the High Courts on consumer disputes, medical negligence, and product liability. The plugin codifies that accumulated procedural knowledge into machine-readable form. It does not codify any client's confidential information.

The plugin is, in this respect, identical in legal character to a published consumer-protection-law textbook, a continuing legal education handout, or a senior advocate's drafting-style lecture. The medium is software. The content is procedural knowledge.

---

## 4. The author's professional position

The author is **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa, practising before the Bombay High Court, Nagpur Bench. The plugin is published under the open-source brand **Wolfgang Rush**, which is the author's publishing handle for legal-technology infrastructure; the real-identity accountability declared in this section attaches to the author personally and is not displaced by the use of a publishing handle.

The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961, the Bar Council of India Rules, and the Standards of Professional Conduct and Etiquette.

The plugin is published as a personal contribution to the open-source legal-technology ecosystem. It is published without any commercial channel, without any solicitation of professional work, without any advertisement of professional services, and without any acceptance of work through this repository. **No commercial engagement is offered through this repository.**

This NOTICE is filed of record in this open-source repository so that any person who reads, reviews, audits, or assesses this plugin has full transparency about its provenance and its scope from the moment of release.

---

## 5. Verification of clean provenance

The repository owner shall maintain, on a private offline record, a build log demonstrating that every line of every file in the plugin was either:

(a) authored from scratch as procedural skeleton, OR
(b) derived from public statute, public rule, public judgment, or public consumer-protection-law textbook, OR
(c) derived from the author's own original procedural knowledge as a practitioner.

No line of any file was, at any stage, copied from, paraphrased from, summarised from, or pattern-matched against any specific client matter, consumer case, client communication, or client document.

This NOTICE is the author's signed declaration of that position.

---

## 6. Reporting concerns

If any reader, regulator, fellow advocate, or member of the public believes any specific content in this plugin is derived from a specific client matter or specific confidential communication, the reader is requested to:

(a) identify the file and line at issue in the plugin,
(b) identify the specific client matter or communication believed to be the source,
(c) explain the basis of the belief,

and raise the concern via a GitHub Issue on this repository.

Concerns raised with these particulars will be investigated and the file or line will be removed or rewritten if the concern is well-founded. Concerns raised without these particulars cannot be acted upon.

---

## 7. Standing instruction to forks and derivatives

Any fork, derivative, downstream redistribution, or commercial integration of this plugin or its content shall preserve this NOTICE in unmodified form, and shall extend the same provenance discipline to any content added in the fork or derivative.

This NOTICE travels with the code under the same MIT licence that governs the source.

---

*Signed and dated by way of public commit history on the repository. The author stands by every line of this notice.*
