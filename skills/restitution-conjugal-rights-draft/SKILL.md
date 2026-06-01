---
name: restitution-conjugal-rights-draft
description: Draft a petition for restitution of conjugal rights under Section 9 of the Hindu Marriage Act 1955 / Section 22 of the Special Marriage Act 1954 / Section 32 of the Indian Divorce Act 1869 / equivalent personal-law provisions. RCR is filed where one spouse has withdrawn from the society of the other without reasonable excuse, and the petitioner seeks a decree directing the respondent to resume cohabitation. (Note the constitutional controversy around RCR — *T. Sareetha v. T. Venkata Subbaiah AIR 1983 AP 356* (struck down) versus *Harvinder Kaur v. Harmander Singh AIR 1984 Del 66* and *Saroj Rani v. Sudarshan Kumar (1984) 4 SCC 90* (upheld). The provision is currently constitutional but under review in subsequent proceedings.) Personal law sourced from family-config.md. Auto-fires on "draft RCR", "draft restitution of conjugal rights", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Restitution of Conjugal Rights Petition Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: PETITION FOR RESTITUTION OF CONJUGAL RIGHTS
case_short_code: RCR
statutory_opening:
  HMA: "PETITION UNDER SECTION 9 OF THE HINDU MARRIAGE ACT, 1955 FOR RESTITUTION OF CONJUGAL RIGHTS"
  SMA: "PETITION UNDER SECTION 22 OF THE SPECIAL MARRIAGE ACT, 1954 FOR RESTITUTION OF CONJUGAL RIGHTS"
  IDA: "PETITION UNDER SECTION 32 OF THE INDIAN DIVORCE ACT, 1869 FOR RESTITUTION OF CONJUGAL RIGHTS"
grounds_structure:
  - "1. The Respondent has, without reasonable excuse, withdrawn from the society of the Petitioner."
  - "2. The withdrawal commenced on [date] and continues to date."
  - "3. The Petitioner is and has been ready, willing, and able to resume cohabitation."
primary_relief_clauses:
  - "(a) Decree directing the Respondent to restitute conjugal rights and resume cohabitation with the Petitioner;"
  - "(b) Costs;"
  - "(c) Such further relief as this Hon'ble Court may deem just."
```

## Strategic notes

- RCR is rarely the most efficacious remedy on its own — the decree is enforced under Order XXI Rule 32 CPC (attachment of property) but the underlying obligation of cohabitation cannot be specifically enforced.
- RCR is more commonly filed as a procedural step preceding divorce — if the Respondent does not comply with the RCR decree for one year, the Petitioner can seek divorce under Section 13(1A)(ii) HMA / Section 27(2)(ii) SMA / etc.
- The Overseer flags any RCR petition that is filed without consideration of whether the petitioner's *actual* relief is divorce-after-one-year — many RCR petitions are filed for that procedural reason and should be drafted with that endpoint in view.
