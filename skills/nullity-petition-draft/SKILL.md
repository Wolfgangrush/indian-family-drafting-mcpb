---
name: nullity-petition-draft
description: Draft a petition for nullity of marriage under Section 11 (void marriages) or Section 12 (voidable marriages) of the Hindu Marriage Act 1955 / Section 24 and Section 25 of the Special Marriage Act 1954 / Section 18 and Section 19 of the Indian Divorce Act 1869 / equivalent personal-law provisions. Void marriages are void ab initio (bigamy, prohibited degrees of consanguinity / affinity, marriage with a person already married, ceremony not performed). Voidable marriages can be annulled at the option of one party (impotence, consent obtained by fraud or force, pregnancy of bride by third party at time of marriage unknown to husband, mental incapacity). Personal law sourced from family-config.md. Auto-fires on "draft nullity", "draft annulment", "draft void marriage", "draft voidable marriage", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Nullity Petition Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: PETITION FOR DECREE OF NULLITY OF MARRIAGE
case_short_code: NULLITY
statutory_opening:
  HMA_void: "PETITION UNDER SECTION 11 OF THE HINDU MARRIAGE ACT, 1955 FOR DECREE OF NULLITY OF MARRIAGE (VOID MARRIAGE)"
  HMA_voidable: "PETITION UNDER SECTION 12 OF THE HINDU MARRIAGE ACT, 1955 FOR DECREE OF NULLITY OF MARRIAGE (VOIDABLE MARRIAGE)"
  SMA_void: "PETITION UNDER SECTION 24 OF THE SPECIAL MARRIAGE ACT, 1954 FOR DECREE OF NULLITY OF MARRIAGE (VOID MARRIAGE)"
  SMA_voidable: "PETITION UNDER SECTION 25 OF THE SPECIAL MARRIAGE ACT, 1954 FOR DECREE OF NULLITY OF MARRIAGE (VOIDABLE MARRIAGE)"
  IDA: "PETITION UNDER SECTION 18 / SECTION 19 OF THE INDIAN DIVORCE ACT, 1869 FOR DECREE OF NULLITY OF MARRIAGE"
grounds_structure:
  void:
    - "1. The marriage between the parties is void ab initio because [bigamy / prohibited consanguinity / etc. — case-specific]."
  voidable:
    - "1. The marriage between the parties is voidable at the instance of the Petitioner because [impotence / fraud / force / pregnancy / mental incapacity — case-specific]."
    - "2. The Petitioner has not, with knowledge of the facts, condoned the conduct."
    - "3. The petition is filed within the limitation period prescribed."
primary_relief_clauses:
  - "(a) Decree declaring the marriage between the parties null and void / annulled;"
  - "(b) Custody of any child of the parties (children of void marriages are legitimate under Section 16 HMA — preserved);"
  - "(c) Maintenance to any party / child entitled;"
  - "(d) Costs;"
  - "(e) Such further relief as this Hon'ble Court may deem just."
```

## Strategic notes

- Void vs voidable: void marriages are void from inception; voidable marriages are valid until annulled. The legal consequences (children's legitimacy, property rights, maintenance) differ.
- Section 16 HMA expressly legitimises children of void marriages — the Drafter does not write the children out of legitimacy.
- Limitation: Section 12(2) HMA prescribes specific limitation windows for voidable-marriage grounds (e.g. one year from cessation of force / discovery of fraud).
