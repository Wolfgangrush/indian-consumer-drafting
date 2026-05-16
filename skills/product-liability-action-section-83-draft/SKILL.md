---
name: product-liability-action-section-83-draft
description: Draft a Product Liability Action under Section 83 read with Sections 82, 84, 85, 86 and 87 of the Consumer Protection Act 2019. For a consumer who has suffered harm by reason of a defective product, against the product manufacturer (Section 84 strand) / product service provider (Section 85 strand) / product seller (Section 86 strand), seeking compensation for the harm and corrective relief. Encodes the Section 82 application scope (any person who is harmed; including any user of the product even where not the buyer); the Section 83 institution-of-action mechanism (any harmed person + Section 35 / 47 / 58 forum jurisdiction); the Section 84 manufacturer strand (manufacturing defect / design defect / non-conformity with express warranty / failure to contain adequate instructions / inadequate warnings); the Section 85 product service provider strand (faulty / imperfect / deficient service / act of omission or commission or negligence / failure to issue adequate instructions or warnings); the Section 86 product seller strand (substantial control over design / testing / manufacturing / packaging / labelling / alteration / express warranty / unknown-manufacturer fallback / failure to exercise reasonable care in assembling / inspecting / maintaining); the Section 87 exception map (misuse / alteration / discontinued product / employer-use / non-end-user); the Section 2(33) (harm) / 2(34) (manufacturer) / 2(35) (product) / 2(36) (product liability) / 2(37) (product seller) / 2(38) (product service provider) definitional anchors. Auto-fires on "draft product liability action", "draft Section 83 CPA", "draft product liability complaint", "draft defective product complaint", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Product Liability Action (Section 83) Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_consumer_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: PRODUCT LIABILITY ACTION UNDER SECTION 83 READ WITH SECTIONS 82, 84, 85, 86 AND 87 OF THE CONSUMER PROTECTION ACT 2019
case_short_code: PROD_LIAB_ACTION
case_number_prefix: C.C.
pleading_type: Product Liability Action
typical_forum: District / State Commission / NCDRC (per pecuniary tier of compensation claimed)
typical_parties: Complainant (harmed person — buyer or end-user) + Opposite Party No. 1 (Product Manufacturer — Section 84 strand) + Opposite Party No. 2 (Product Service Provider — Section 85 strand, where engaged) + Opposite Party No. 3 (Product Seller — Section 86 strand)
statutory_opening: "This Product Liability Action is filed under Section 83 read with Sections 82, 84, 85, 86 and 87 of the Consumer Protection Act 2019, against the Product Manufacturer / Product Service Provider / Product Seller for compensation in respect of the harm caused to the Complainant by the defective product particularised hereinafter."
ground_clauses:
  - "Status as harmed person — Section 82 read with Section 2(33) (harm = damage to property other than the product itself; personal injury, illness or death; mental agony; loss of consortium; loss of services). The Complainant is a person who has been harmed by the defective product, irrespective of whether the Complainant is the buyer or the end-user (Section 82's application scope extends to any harmed person)."
  - "Product description — Section 2(35) — the product is [Product-Placeholder] manufactured by Opposite Party No. 1, sold through Opposite Party No. 3, with after-sale service by Opposite Party No. 2 (refer Annexure ___)."
  - "Defect particulars — [manufacturing defect — deviation from design specifications / design defect / non-conformity with express warranty / failure to contain adequate instructions / inadequate warnings — particulars of each engaged limb]."
  - "Section 84 manufacturer-liability strand (where engaged) — Opposite Party No. 1 is liable as the product manufacturer because [limb particulars]. (a) the product contains a manufacturing defect; (b) the product is defective in design; (c) deviation from manufacturing specifications; (d) non-conformity with express warranty; (e) failure to contain adequate instructions; (f) inadequate warnings."
  - "Section 85 product-service-provider strand (where engaged) — Opposite Party No. 2 is liable as the product service provider because [limb particulars]. (a) faulty / imperfect / deficient service; (b) act of omission or commission or negligence; (c) failure to issue adequate instructions or warnings to prevent harm."
  - "Section 86 product-seller strand (where engaged) — Opposite Party No. 3 is liable as the product seller because [limb particulars]. (a) exercise of substantial control over the design / testing / manufacturing / packaging / labelling; (b) alteration / modification after sale; (c) express warranty made by the seller distinct from the manufacturer's warranty; (d) the identity of the manufacturer is not known and the seller has not exercised reasonable care to ascertain the manufacturer; (e) failure to exercise reasonable care in assembling / inspecting / maintaining the product; (f) failure to pass on warnings or instructions from the manufacturer to the end-user."
  - "Section 87 exceptions pre-empted — the Complainant pleads (where the facts permit) that none of the Section 87 exceptions apply: (a) the product was not misused; (b) the product was not altered / modified by the Complainant; (c) the harm is not the consequence of an inherent characteristic that could not reasonably be avoided; (d) the Complainant did not fail to follow adequate instructions / heed adequate warnings; (e) the use was as an end-user, not as an employer in respect of which the Workmen's Compensation regime would apply."
  - "Harm causation chain — the defect proximately caused the harm; each link in the chain (defect → exposure → harm) is pleaded with the supporting annexure (medical records for personal injury; valuation report for property damage; financial records for consequential loss)."
  - "Pecuniary and territorial jurisdiction — per the Section 34 / 47 / 58 tier and the Section 34(2) / 47(4) / 58(2) territorial-jurisdiction anchor."
  - "Limitation — within two years from date of cause of action per Section 69."
prayer_clauses:
  - "(a) Direct the Opposite Parties (Manufacturer / Product Service Provider / Product Seller) jointly and severally to pay compensation of ₹___ to the Complainant for the harm caused, under each head of pecuniary and non-pecuniary loss;"
  - "(b) Direct interest at ___% per annum from ____ till date of realisation;"
  - "(c) Direct withdrawal of the defective product from the market under Section 19 of the Consumer Protection Act 2019 (with Central Consumer Protection Authority intervention if directed by the Commission);"
  - "(d) Direct issuance of corrective advertisement under Section 18(2)(f) read with Section 49(1)(g) / Section 59(1)(g) of the Act;"
  - "(e) Award costs of ₹___;"
mandatory_annexures:
  - identity_address_proof_of_complainant
  - invoice_or_receipt_of_purchase
  - product_specimen_photographs_or_the_defective_product_itself_where_preservable
  - product_packaging_and_labelling
  - product_instructions_and_warnings_supplied_with_the_product
  - express_warranty_card_where_applicable
  - service_records_for_after_sale_service_engagement_where_section_85_strand_engaged
  - particulars_of_defect_with_independent_inspection_or_expert_report
  - medical_records_where_personal_injury_is_in_issue
  - valuation_report_where_property_damage_is_in_issue
  - financial_records_evidencing_consequential_loss
  - pre_complaint_correspondence_to_manufacturer_seller_with_proof_of_service
  - opposite_party_reply_where_received
accompanying_applications:
  - "I.A. for interim relief under Section 38(9) — including direction to the Opposite Party to preserve the defective product / similar batch products pending adjudication, and direction to suspend sale of the impugned batch"
  - "I.A. for appointment of an independent technical / regulatory expert to opine on the defect under Section 38(2)(c)"
  - "I.A. for joinder of further Opposite Parties (e.g., a separate component manufacturer) as the inquiry surfaces them"
  - "I.A. for condonation of delay under the proviso to Section 69"
  - "I.A. for exemption from filing certified copies"
  - "I.A. for urgent listing"
  - "I.A. for class-action permission under Section 38(11) where harm is widespread across consumers of the same batch / product line"
filing_fee: "Computed per the pecuniary tier."
```

## Section 82 — application scope

Section 82 makes Chapter VI (Product Liability) applicable to every claim for compensation under a product liability action by a complainant for any harm caused by a defective product manufactured by a product manufacturer or serviced by a product service provider or sold by a product seller. The Section is the gateway — Section 83 is the action-institution mechanism — Sections 84 to 87 carry the substantive liability map.

## Section 83 — action institution

Section 83 permits a person to bring a product liability action against a product manufacturer / product service provider / product seller for any harm caused to him on account of a defective product. The action is filed before the District / State / National Commission per the pecuniary tier (the same Section 34 / 47 / 58 architecture that governs deficiency / defect / UTP complaints).

## Strand-mapping discipline

A product-liability action may engage one, two, or all three strands. The Drafter pleads each engaged strand with the specific limb-particulars under that section:

- **Single strand** — e.g., a manufacturing defect in a self-manufactured-self-sold product engages Section 84 only (against the manufacturer-seller).
- **Two strands** — e.g., a design defect in a product sold through an independent retailer engages Section 84 (against the manufacturer) and Section 86 (against the retailer where the (d) unknown-manufacturer or (e) failure-to-inspect limb applies).
- **Three strands** — e.g., a defective product with deficient after-sale service that caused additional harm engages Section 84 (manufacturer for the original defect), Section 85 (after-sale service provider for the deficient service), and Section 86 (seller for the pass-through-warning failure).

The Section 87 exceptions are pleaded as a pre-emption block — anticipating the manufacturer's / seller's defence.

## Definitional anchors (Section 2)

- **Section 2(10) — defect** (in goods) — fault, imperfection, shortcoming in quality, quantity, potency, purity, standard
- **Section 2(33) — harm** — damage to property other than the product; personal injury, illness, death; mental agony / emotional distress + consequential loss; loss of consortium / services
- **Section 2(34) — manufacturer** — person who (a) makes the product or any part thereof; or (b) assembles the product; or (c) puts his own mark on the product made by some other person
- **Section 2(35) — product** — any article or goods or substance or raw material or any extended cycle of such product, manufactured or otherwise (with certain exclusions — see proviso)
- **Section 2(36) — product liability** — the responsibility of a product manufacturer / seller of any product or service / product service provider to compensate for any harm caused to a consumer by such defective product / by deficiency in services relating thereto
- **Section 2(37) — product seller** — person who, in the course of business, imports, sells, distributes, leases, installs, prepares, packages, labels, markets, repairs, maintains, or otherwise is involved in placing the product for commercial purpose (excludes seller of immovable property; provider of professional services that involve a learned intermediary; informal sale at a flea market / second-hand sale)
- **Section 2(38) — product service provider** — person who provides any service in respect of the product

These definitions anchor every product-liability pleading.

## Cross-references

- **Section 18(2)(f)** — Central Consumer Protection Authority power to direct corrective advertising — cited where the prayer seeks corrective advertising.
- **Section 19** — power of the Central Authority to recall a defective product / direct discontinuance — cited where the prayer seeks recall.
- **Legal Metrology (Packaged Commodities) Rules 2011** — labelling compliance — cited where the defect involves labelling.
- **Bureau of Indian Standards Act 2016 + sector-specific BIS Standards** — where the product is required to conform to a mandatory BIS standard.
