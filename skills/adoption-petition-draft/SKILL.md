---
name: adoption-petition-draft
description: Draft a petition for adoption of a child under (a) the Hindu Adoptions and Maintenance Act 1956 (HAMA — applies where both adoptive parents and the adopted child are Hindu, Buddhist, Jain, or Sikh) or (b) the Juvenile Justice (Care and Protection of Children) Act 2015 read with the Adoption Regulations 2022 framed under it (applies regardless of the religion of the parties — the secular, CARA-mediated route, for orphan / abandoned / surrendered children). Drafts the petition with the parties' eligibility under the applicable statute, the welfare-of-the-child basis, the absence of consideration (HAMA Section 17 prohibits payment), and the prayer. Auto-fires on "draft adoption", "draft HAMA adoption", "draft JJ Act adoption", "draft adoption petition", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Adoption Petition Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: PETITION FOR DECLARATION OF VALIDITY OF ADOPTION
case_short_code: ADOPTION
statutory_opening:
  HAMA: "PETITION UNDER THE HINDU ADOPTIONS AND MAINTENANCE ACT, 1956 FOR DECLARATION OF VALIDITY OF ADOPTION"
  JJ_Act: "PETITION UNDER SECTION 56 / SECTION 60 OF THE JUVENILE JUSTICE (CARE AND PROTECTION OF CHILDREN) ACT, 2015 READ WITH THE ADOPTION REGULATIONS, 2022 FOR DECLARATION OF VALIDITY OF ADOPTION"
grounds_structure:
  HAMA:
    - "1. The Petitioner adoptive father / adoptive mother is a Hindu / Buddhist / Jain / Sikh (HAMA Section 7 / Section 8)."
    - "2. The Petitioner has the capacity to take in adoption (HAMA Section 7 / Section 8 — age, mental competence, no living child of same gender unless permitted)."
    - "3. The natural parents / guardian have the capacity to give in adoption (HAMA Section 9)."
    - "4. The child given in adoption fulfils the conditions of Section 10 (Hindu, unmarried, under 15 years unless custom permits)."
    - "5. The adoption ceremony (HAMA Section 11) — the giving and taking ceremony — was performed."
    - "6. No payment has been received in consideration of the adoption (HAMA Section 17 — a criminal offence)."
  JJ_Act:
    - "1. The Petitioner adoptive parent(s) fulfil the eligibility criteria under Regulation 5 of the Adoption Regulations 2022."
    - "2. The child has been declared legally free for adoption by the Child Welfare Committee under Section 38 of the JJ Act 2015."
    - "3. The Home Study Report and the matching process by the Central Adoption Resource Authority (CARA) have been completed."
    - "4. The adoption is in the welfare of the child."
primary_relief_clauses:
  - "(a) Declare the adoption of the minor child [name] by the Petitioner(s) to be valid and lawful;"
  - "(b) The minor child be entitled to all rights as a natural-born child of the Petitioner(s);"
  - "(c) Costs;"
  - "(d) Such further relief as this Hon'ble Court may deem just."
```

## Statutory framework

- **HAMA 1956 — Sections 5 to 17** (capacity, ceremony, effects, prohibition of consideration)
- **JJ Act 2015 — Sections 56 to 73** (in-country and inter-country adoption procedure)
- **Adoption Regulations 2022** (framed under the JJ Act; supersedes the 2017 Regulations)
- **Central Adoption Resource Authority (CARA)** — the apex body for non-HAMA adoptions
- **Hague Convention on Inter-Country Adoption 1993** — India is a signatory; inter-country adoptions are mediated through CARA-recognised foreign adoption agencies

## Forum

- HAMA adoptions: civil court / District Court / Family Court (where Family Courts exercise this jurisdiction under FCA Section 7)
- JJ Act adoptions: District Court (Section 60 JJ Act 2015), with the CARA process mandatory pre-petition
