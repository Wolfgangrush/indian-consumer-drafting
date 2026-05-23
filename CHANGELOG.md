# Changelog

All notable changes to the `indian-consumer-drafting` plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/) and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [0.2.1-alpha] — 2026-05-24

### Filing-grade render-defect repair + pipeline-optionality

The v0.1.0 render path produced filing-grade Markdown but the pandoc → `.docx` conversion failed Bombay HC / equivalent Registry expectations on multiple counts (title not bold, section headers left-aligned, Index table column-headers wrapping vertically, party block leaking onto cover pages, ~6,200-word bloat). This release repairs the render path, calibrated against an actual filed Bombay HC Nagpur Second Appeal pleading the author supplied as the filing-grade reference. Inherits the v0.2.1 fixes from `indian-hc-drafting-litigation`.

### Added

- **Pre-customised `reference.docx`** in the plugin's base-skill folder with locked Word styles (TNR 14pt body, 1.5 line spacing, 4cm left / 2.5cm right-top-bottom margins, Heading 1 bold centered, Heading 2 bold + UNDERLINED + centered + letter-spacing for the spaced `F A C T S` effect, Heading 3 bold + UNDERLINED + centered for unspaced section headers, Heading 4 bold + UNDERLINED + left for `MOST RESPECTFULLY SHEWETH:` style anchors, fixed table layout).
- **`build_reference_docx.py`** — reproducible python-docx build script for the shipped reference.docx.
- **`fix_docx_tables.py`** — post-pandoc Python script that forces column widths on every table (5-col 8/8/60/14/10; 4-col 10/10/65/15; 3-col 10/75/15; 2-col 18/82). Locks first-row bold + centered + vertically-centered cells. Drafter runs this as the final post-pandoc step.
- **MARKDOWN HEADING DISCIPLINE** in the Drafter prompt + base SKILL.md (Heading 1 / Heading 2 / Heading 3 / Heading 4 mapping for court header / spaced section headers / unspaced section headers / left-anchored headings).
- **VERBOSITY DISCIPLINE** with per-case-type word-count targets and hard ceilings.
- **PIPELINE-OPTIONALITY** — Verifier / Refiner / Overseer now OPTIONAL QC layers. Default exit point is after Stage 3 (Drafter).
- **COVER-PAGE DISCIPLINE** — INDEX / SYNOPSIS / LIST OF ANNEXURES each begin on `\newpage` with short cause-title only.
- **Bold-number paragraph convention** — Facts and Grounds paragraphs use `**1.** **2.** **3.**`.
- **Inline-bold highlighting convention** for property descriptors / annexure markers / key terms within Facts narrative.

### Changed

- **Drafter pandoc command** is now TWO steps (pandoc → .docx, then `fix_docx_tables.py`). Step 2 is non-negotiable; skipping it reproduces the v0.2.0 stacking-column defect.

### Cost / token-budget note

Running the full 6-agent pipeline burns approximately 600K tokens per draft, which can exhaust an advocate's Claude session limit. v0.2.1 makes Stages 4–6 OPTIONAL so a baseline Reader → Format → Drafter run (~280K tokens) is sufficient for routine pleadings. The optional QC stages remain available for high-stakes matters.

---

## [0.1.0-alpha] — 2026-05-16 (initial release)

### Added

- **Plugin scaffolding** — `.claude-plugin/plugin.json` manifest · MIT `LICENSE` · `NOTICE.md` provenance and privilege statement · `.gitignore` · this `CHANGELOG.md` · comprehensive `README.md`.
- **Six-agent drafting pipeline** — Reader → Format → Drafter → Verifier → Refiner → Overseer. Each agent is a markdown file under `agents/<name>/<name>.md` with YAML frontmatter declaring `name`, `description`, and `allowed-tools`.
- **Shared infrastructure skills:**
  - `_drafting_common` — anti-pollution rules, encoding standards, language conventions, AI-style-marker blacklist, consumer-specific privacy firewall, citation discipline, and statutory-currency rules (Consumer Protection Act 2019 — with the *Indian Medical Association v. V.P. Shantha* line on medical service inclusion — Consumer Protection (Consumer Disputes Redressal Commissions) Rules 2020, Consumer Protection (E-Commerce) Rules 2020, Sale of Goods Act 1930, Indian Contract Act 1872, Indian Medical Council (Professional Conduct, Etiquette and Ethics) Regulations 2002, New Drugs and Clinical Trials Rules 2019, Clinical Establishments (Registration and Regulation) Act 2010, Bharatiya Nagarik Suraksha Sanhita 2023, Bharatiya Sakshya Adhiniyam 2023, Limitation Act 1963, and applicable State Court-Fees Act). **Legacy-detection rule:** the Verifier flags any reference to the Consumer Protection Act 1986 (repealed by the 2019 Act) as a legacy mis-citation; *Forum* is auto-flagged as the legacy term that the 2019 Act replaced with *Commission*.
  - `_consumer_drafting_base` — universal Indian consumer-pleading skeleton (Cause Title with correct Commission nomenclature · Memo of Parties · Statutory Opening invoking the operative section · List of Dates · Facts · Deficiency / Defect / Unfair-Trade-Practice / Product-Liability / Medical-Negligence pleadings · Cause of Action · Pecuniary and Territorial Jurisdiction paragraphs · Limitation paragraph · Prayer · Verification · Affidavit-in-support · Index · List of Documents · accompanying applications).
- **Ten case-type skill scaffolds:**
  - `district-commission-complaint-section-35-draft` — complaint before the District Consumer Disputes Redressal Commission under Section 35 of the Consumer Protection Act 2019 (pecuniary jurisdiction up to ₹1 crore)
  - `state-commission-complaint-section-47-draft` — original complaint before the State Consumer Disputes Redressal Commission under Section 47 of the Consumer Protection Act 2019 (pecuniary jurisdiction above ₹1 crore and up to ₹10 crore)
  - `ncdrc-complaint-section-58-draft` — original complaint before the National Consumer Disputes Redressal Commission under Section 58 of the Consumer Protection Act 2019 (pecuniary jurisdiction above ₹10 crore)
  - `medical-negligence-complaint-draft` — complaint alleging deficiency of medical service under Section 2(11) of the Consumer Protection Act 2019 read with the Indian Medical Council (Professional Conduct, Etiquette and Ethics) Regulations 2002 and the *Jacob Mathew* / *Martin F. D'Souza* / *Kusum Sharma* / *V.P. Shantha* line on the standard of medical care
  - `product-liability-action-section-83-draft` — product-liability action under Sections 82 to 87 of the Consumer Protection Act 2019 against a product manufacturer, product service provider, or product seller
  - `unfair-trade-practice-complaint-draft` — complaint alleging unfair trade practice under Section 2(47) of the Consumer Protection Act 2019 read with Section 49 / Section 59 powers to discontinue the practice
  - `consumer-appeal-section-41-district-to-state-draft` — appeal from the District Commission to the State Commission under Section 41 of the Consumer Protection Act 2019 (45-day limitation; Section 51 of the State Commission's own appellate scheme)
  - `consumer-appeal-section-51-state-to-ncdrc-draft` — appeal from the State Commission to the NCDRC under Section 51 of the Consumer Protection Act 2019 (30-day limitation; pre-deposit under Section 51(2) and the proviso)
  - `consumer-revisional-application-section-67-draft` — revisional application before the NCDRC under Section 67 of the Consumer Protection Act 2019 (revisional jurisdiction; supervisory scope)
  - `consumer-execution-application-section-71-draft` — application for execution of the Commission's order under Sections 71 and 72 of the Consumer Protection Act 2019 (recovery of penalty and order-money; treatment as decree of civil court)
- **Forum-aware design** — the user supplies `case-config.md` declaring the chosen Commission (District / State / NCDRC), pecuniary tier, territorial-jurisdiction anchor, deficiency / defect / UTP / product-liability / medical-negligence character, limitation anchor under Section 69, compensation quantum, and accompanying-application set.

### Notes on this release

This is a **v0.1.0-alpha scaffold release**. The structural skeletons, agent pipeline, base skills, and 10 case-type skill frames are in place. Deep per-skill encoding (full pleading exemplars for each case type, full *V.P. Shantha* / *Jacob Mathew* / *Martin F. D'Souza* / *Kusum Sharma* / *Bolam* / *Lucknow Development Authority v. M.K. Gupta* line of Supreme Court precedent encoded in the Verifier, NCDRC Practice Direction discipline, and bench-specific filing-counter conventions for District / State / NCDRC) will land in v0.1.0 and onward.

### Released under

MIT License. Authored by Rushikesh R. Mahajan, Advocate, publishing under the Wolfgang Rush open-source brand for legal-tech infrastructure.
