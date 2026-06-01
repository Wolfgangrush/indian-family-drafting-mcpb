# Case Facts Background — Divorce petition under HMA § 13(1)(ia) and 13(1)(ib)

All party names, addresses, monetary figures, dates beyond documented dates, and witness identities are fictional placeholders.

## Parties

- **Petitioner / Wife:** [Wife-A], aged about [Wife-Current-Age-Placeholder] years, daughter of [Wife-Father-Placeholder], presently residing at [Wife-Parental-Address-Placeholder]. Employed at [Wife-Employer-Placeholder] earning Rs. [Wife-Salary-Placeholder]/- per month.
- **Respondent / Husband:** [Husband-B], aged about [Husband-Current-Age-Placeholder] years, son of [Husband-Father-Placeholder], residing at [Matrimonial-Home-Address-Placeholder]. Employed at [Husband-Employer-Placeholder] earning approximately Rs. [Husband-Salary-Placeholder]/- per month.

## Marriage

- Date of marriage: 10 December 2019
- Place: [Marriage-Venue-Placeholder]
- Rites: Hindu rites and customs
- Marriage certificate: see `01-marriage-certificate-extract.docx`
- Issue from marriage: NIL

## Grounds — cruelty + desertion

### Cruelty (HMA § 13(1)(ia))

Sustained pattern from January 2022 to 05 August 2024 — see contemporaneous record at `02-petitioner-cruelty-incident-diary.docx`:

- **Verbal abuse + physical assault** — entries 1, 2, 4, 5 (March 2023), (September 2023), (April 2024), and culminating incident on 05 August 2024.
- **Confinement** — three-day episode 15-18 July 2022 (Entry 3).
- **Financial coercion** — sustained demand for control over petitioner's salary; insistence on joint account he controls.
- **Social isolation** — denied contact with parental family beyond 5-minute calls.
- **Recent reference to Samar Ghosh v. Jaya Ghosh (2007) 4 SCC 511 cruelty categories — verbal cruelty, physical cruelty, mental cruelty, and social isolation all engaged.**

### Desertion (HMA § 13(1)(ib))

- Date of separation: 05 August 2024
- Period of continuous separation as on date of filing: 18+ months (well over the 2-year statutory minimum at the date the petition will be filed — petition contemplates filing on or after 05 August 2026).
- Animus deserendi: established by the husband's open declarations to common acquaintances (Entry 20).
- No reconciliation attempt: established by the unanswered mediation letter dated 15 September 2024 (see `03-mediation-request-letter-2024-09-15.docx`).

## Forum and case type

- **Forum:** Family Court at [Family-Court-Location-Placeholder] (territorial jurisdiction — place of last residence together OR place where wife is presently residing per Section 19 HMA).
- **Case type:** `divorce-petition`.
- **Statutory anchors:** Sections 13(1)(ia), 13(1)(ib), 25 (permanent alimony), 26 (custody — not applicable, no issue), 23(1)(a) (no collusion), 23(2) (attempt at reconciliation).

## Reliefs sought

1. Decree of dissolution of marriage by way of divorce under Sections 13(1)(ia) and 13(1)(ib) of the Hindu Marriage Act, 1955.
2. Permanent alimony / maintenance under Section 25 of the HMA — quantified at Rs. [Permanent-Alimony-Placeholder]/- (one-time) OR Rs. [Monthly-Maintenance-Placeholder]/- per month, having regard to (a) the respondent's income, (b) his standard of living, (c) the petitioner's own income and lifestyle erosion, (d) no other dependents on the petitioner.
3. Streedhan and personal effects (list at `[List-of-Streedhan-Placeholder]`) to be returned by the respondent to the petitioner — direction under Section 27 of the HMA.
4. Costs throughout.

## Procedural safeguards (Verifier-stage)

- ✅ Section 9 / 13B not applicable (this is contested, not mutual).
- ✅ Reasonable attempt at reconciliation — mediation letter on record, husband's non-response constitutes proven refusal under Section 23(2).
- ✅ No collusion — Section 23(1)(a) — petitioner and respondent have not colluded; respondent is opposing.
- ✅ No condonation — petitioner left within reasonable time of last cruelty incident (Entry 19, 05 August 2024).
- ✅ No undue delay — petition filed within 2 years of cause of action; not barred by Section 23(1)(d).

## How to use this fixture

1. Point `read_case_folder(path)` at this directory.
2. Reader extracts facts from the 3 `.docx` files plus this `case-facts-background.md`.
3. Call `get_case_type_format("divorce-petition")`.
4. The remaining 5 agents (Format → Drafter → Verifier → Refiner → Overseer) run end-to-end to produce `final-draft.docx` containing the divorce petition (Cause Title, Parties, Statement of Facts, Grounds, Prayer, Verification, List of Documents, Affidavit).
