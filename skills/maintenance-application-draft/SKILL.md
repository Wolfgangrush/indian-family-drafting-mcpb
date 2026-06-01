---
name: maintenance-application-draft
description: Draft a maintenance application under any of the multiple Indian maintenance regimes — Section 125 BNSS (corresponding to Section 125 CrPC, secular, summary, before the Magistrate / Family Court) / Section 24 of the Hindu Marriage Act 1955 (interim, between spouses pending matrimonial proceedings) / Section 25 HMA (permanent alimony, post-decree) / Section 18 of the Hindu Adoptions and Maintenance Act 1956 (Hindu wife's substantive right against husband) / Section 20 of the Protection of Women from Domestic Violence Act 2005 (under DV Act) / Section 36 SMA / Section 37 SMA / Section 36 Indian Divorce Act 1869 / Section 37 IDA / Section 23 Maintenance and Welfare of Parents and Senior Citizens Act 2007 (for parents). The applicable provision is sourced from family-config.md based on the relationship and the relief framework chosen. Drafts the application with the mandatory Rajnesh v. Neha (2021) 2 SCC 324 affidavit-of-disclosure (income / assets / liabilities / lifestyle / dependants) for both parties, the quantum proposed with arithmetic basis, and the procedural prayer. Auto-fires on "draft maintenance", "draft 125", "draft Section 125 application", "draft interim maintenance", "draft Section 24 HMA", "draft DV maintenance", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Maintenance Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION FOR MAINTENANCE
case_short_code: MAINT
statutory_opening:
  Section_125_BNSS: "APPLICATION UNDER SECTION 125 OF THE BHARATIYA NAGARIK SURAKSHA SANHITA, 2023 (CORRESPONDING TO SECTION 125 OF THE CODE OF CRIMINAL PROCEDURE, 1973) FOR MAINTENANCE"
  Section_24_HMA: "APPLICATION UNDER SECTION 24 OF THE HINDU MARRIAGE ACT, 1955 FOR INTERIM MAINTENANCE AND LITIGATION EXPENSES"
  Section_25_HMA: "PETITION UNDER SECTION 25 OF THE HINDU MARRIAGE ACT, 1955 FOR PERMANENT ALIMONY AND MAINTENANCE"
  Section_18_HAMA: "SUIT UNDER SECTION 18 OF THE HINDU ADOPTIONS AND MAINTENANCE ACT, 1956 FOR MAINTENANCE"
  Section_20_DVAct: "APPLICATION UNDER SECTION 20 OF THE PROTECTION OF WOMEN FROM DOMESTIC VIOLENCE ACT, 2005 FOR MONETARY RELIEFS INCLUDING MAINTENANCE"
  Section_36_SMA: "APPLICATION UNDER SECTION 36 OF THE SPECIAL MARRIAGE ACT, 1954 FOR INTERIM MAINTENANCE"
  Section_37_SMA: "PETITION UNDER SECTION 37 OF THE SPECIAL MARRIAGE ACT, 1954 FOR PERMANENT ALIMONY"
  Section_23_Senior_Citizens: "APPLICATION UNDER SECTION 23 OF THE MAINTENANCE AND WELFARE OF PARENTS AND SENIOR CITIZENS ACT, 2007"
grounds_structure:
  - "1. The Petitioner / Applicant has no independent income sufficient to maintain herself / himself and the minor child(ren)."
  - "2. The Respondent has sufficient means to maintain the Petitioner and the children."
  - "3. The Respondent has neglected / refused to maintain the Petitioner and the children."
  - "4. The quantum claimed is based on the Respondent's income (paragraph __), the Petitioner's necessary expenses (paragraph __), and the dependent children's needs (paragraph __) — the arithmetic is set out in the schedule attached at Annexure ___."
primary_relief_clauses:
  - "(a) The Respondent be directed to pay maintenance at the rate of Rs. ___ per month for the Petitioner and Rs. ___ per month per minor child, from the date of this application;"
  - "(b) The Respondent be directed to pay litigation expenses of Rs. ___;"
  - "(c) Costs;"
  - "(d) Such further relief as this Hon'ble Court may deem just."
accompanying_applications:
  - rajnesh_v_neha_disclosure_affidavit_petitioner
  - rajnesh_v_neha_disclosure_affidavit_respondent_template
```

## Mandatory disclosures

The *Rajnesh v. Neha (2021) 2 SCC 324* directions are mandatory in every maintenance application. Both the applicant and the respondent must file affidavits disclosing:

1. Personal information (name, age, occupation, qualifications)
2. Income from all sources (salary, business, rent, dividends, interest)
3. Assets (immovable property, vehicles, jewellery, investments)
4. Liabilities (loans, EMIs, dependants' costs)
5. Lifestyle markers (residence, clubs, travel, education of children)
6. Dependants (number, relationship, age)

The Verifier checks that the applicant's affidavit conforms to the *Rajnesh v. Neha* template and that the maintenance quantum cross-foots against the disclosed numbers.
