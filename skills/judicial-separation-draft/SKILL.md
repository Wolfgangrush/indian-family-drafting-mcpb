---
name: judicial-separation-draft
description: Draft a petition for judicial separation under Section 10 of the Hindu Marriage Act 1955 / Section 23 of the Special Marriage Act 1954 / Section 22 of the Indian Divorce Act 1869 / equivalent personal-law provisions. Judicial separation suspends the obligation of cohabitation without dissolving the marriage and is often filed (a) as a precursor to divorce on the ground of non-resumption-of-cohabitation, or (b) where the petitioner is religiously or personally averse to dissolution but seeks formal separation. Personal law is sourced from family-config.md. Produces complete petition with marriage particulars, grievance narrative, grounds (same grounds as divorce under each personal law), prayer, verification, supporting affidavit, list of documents, and interim-maintenance application. Auto-fires on "draft judicial separation", "draft JS petition", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Judicial Separation Petition Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: PETITION FOR JUDICIAL SEPARATION
case_short_code: JS
statutory_opening:
  HMA: "PETITION UNDER SECTION 10 OF THE HINDU MARRIAGE ACT, 1955 FOR JUDICIAL SEPARATION"
  SMA: "PETITION UNDER SECTION 23 OF THE SPECIAL MARRIAGE ACT, 1954 FOR JUDICIAL SEPARATION"
  IDA: "PETITION UNDER SECTION 22 OF THE INDIAN DIVORCE ACT, 1869 FOR JUDICIAL SEPARATION"
grounds_structure:
  - "1. The Petitioner is entitled to a decree of judicial separation on the ground of [cruelty / desertion / adultery / etc.] established by the events narrated in paragraphs ___ to ___."
  - "2. Cohabitation between the parties is no longer possible / desirable."
primary_relief_clauses:
  - "(a) Decree of judicial separation;"
  - "(b) Maintenance for the Petitioner / Respondent and the minor children;"
  - "(c) Custody of the minor children;"
  - "(d) Costs;"
  - "(e) Such further relief as this Hon'ble Court may deem just."
accompanying_applications:
  - interim_maintenance_application
  - interim_custody_application
```

## Forward-load notes

- Judicial separation is a precursor to divorce under HMA Section 13(1A)(i) / SMA Section 27(2)(i) / IDA Section 10(1)(ix): non-resumption of cohabitation for one year after the JS decree is itself a ground for divorce.
- JS does not dissolve the marriage; the parties remain husband and wife and the marriage bond subsists.
- Same grounds as divorce under each personal law.
