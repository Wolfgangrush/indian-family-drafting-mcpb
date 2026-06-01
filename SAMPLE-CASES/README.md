# Sample Cases — Reviewer Examples

Three anonymised Family Court fact patterns. All party names are placeholders.

## Example 1 — Divorce under HMA Section 13(1)(ia) + 13(1)(ib)

> *"Draft a divorce petition under Section 13(1)(ia) and 13(1)(ib) HMA on grounds of cruelty and desertion. Petitioner [W], respondent [H], marriage solemnised 2019-12-10 at [VENUE], cohabitation ended 2024-08-05 after sustained pattern of mental and physical cruelty. No reconciliation possible. Prayer: dissolution + permanent alimony under Section 25 HMA."*

Tool sequence: list_case_types → get_case_type_format("divorce-petition") → get_pleading_base → draft → save_draft_as_docx

## Example 2 — Maintenance under Section 125 CrPC / 144 BNSS

> *"Draft a maintenance application under Section 125 CrPC / 144 BNSS for [WIFE] and one minor child against [HUSBAND] before the JMFC at [LOCATION]. Husband earning ₹[SUM-X] per month, refusing to pay since [DATE]. Wife unemployed homemaker, child aged 7. Prayer: interim and final maintenance + costs."*

Tool sequence: list_case_types → get_case_type_format("maintenance-application") → get_pleading_base → draft → save_draft_as_docx

## Example 3 — Custody under Guardians and Wards Act

> *"Draft a custody application under the Guardians and Wards Act 1890 before the District Judge at [LOCATION] for a 7-year-old minor [CHILD]. Petitioner-father [F] is the natural guardian; respondent-mother [M] has retained the child since 2025-09-01 without consent. Welfare-of-child framework — petitioner has stable employment, age-appropriate schooling arranged, extended family support. Prayer: custody + visitation regime."*

Tool sequence: list_case_types → get_case_type_format("custody-petition") → get_pleading_base → draft → save_draft_as_docx

## Notes for the reviewer

- All examples use placeholders (`[W]`, `[H]`, `[F]`, `[M]`, `[CHILD]`, `[SUM-X]`, `[VENUE]`, `[LOCATION]`, `[DATE]`).
- No external API keys / accounts required.
- `save_draft_as_docx` requires `pandoc`.
- Three-layer privacy firewall applies throughout.
