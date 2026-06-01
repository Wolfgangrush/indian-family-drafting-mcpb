---
name: custody-petition-draft
description: Draft a petition for custody / guardianship of a minor child under the Guardians and Wards Act 1890 (the secular, all-religion-applicable guardianship statute) read with the Hindu Minority and Guardianship Act 1956 (where the child is Hindu) and the welfare-of-the-child principle as laid down in *Gaurav Nagpal v. Sumedha Nagpal (2009) 1 SCC 42*, *Yashita Sahu v. State of Rajasthan (2020) 3 SCC 67*, and *Tejaswini Gaud v. Shekhar Jagdish Prasad Tewari (2019) 7 SCC 42*. Covers permanent custody, visitation, vacation custody, education / medical decision-making authority, and international parental child-removal scenarios. Auto-fires on "draft custody petition", "draft guardianship", "draft G&W petition", "draft custody application", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Custody Petition Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: PETITION FOR APPOINTMENT OF GUARDIAN AND CUSTODY OF MINOR
case_short_code: CUSTODY
statutory_opening:
  GW_Act: "PETITION UNDER SECTION 7 / SECTION 25 OF THE GUARDIANS AND WARDS ACT, 1890 READ WITH SECTION 6 OF THE HINDU MINORITY AND GUARDIANSHIP ACT, 1956 FOR APPOINTMENT OF GUARDIAN AND CUSTODY OF THE MINOR CHILD"
grounds_structure:
  - "1. The welfare of the minor child is the paramount consideration (*Gaurav Nagpal v. Sumedha Nagpal*)."
  - "2. The petitioner is the natural guardian / suitable guardian for the welfare of the minor on the following grounds: [education / stability / emotional bond / health / safety / education / financial capacity — case-specific]."
  - "3. The petitioner is fit and proper to be appointed guardian."
primary_relief_clauses:
  - "(a) The Petitioner be appointed guardian of the person and property of the minor child(ren) [name];"
  - "(b) Custody of the minor child(ren) be granted to the Petitioner;"
  - "(c) The Respondent be granted visitation on [schedule];"
  - "(d) Vacation custody on [schedule];"
  - "(e) Education and medical decisions be made by the Petitioner / jointly;"
  - "(f) The Respondent be restrained from removing the minor from the territorial limits of the jurisdiction without prior leave of this Hon'ble Court;"
  - "(g) Costs;"
  - "(h) Such further relief as this Hon'ble Court may deem just."
```

## Special considerations

- **Welfare-of-the-child principle:** the touchstone for every custody decision, not the parents' rights. *Gaurav Nagpal*: welfare includes physical, intellectual, moral, and spiritual welfare.
- **International parental child-removal:** where the minor has been removed to / retained in India from another country, or vice versa, the *Hague Convention on Civil Aspects of International Child Abduction* analysis (India is not a signatory but Indian courts apply the *Yashita Sahu* doctrine) and the *Surya Vadanan v. State of Tamil Nadu (2015) 5 SCC 450* parens-patriae jurisdiction analysis apply.
- **Habeas corpus alternative:** in cases of forcible removal of the child, a writ of habeas corpus under Article 226 (HC plugin) or under Article 32 (SC plugin) is often filed alongside the G&W petition. Where applicable, the Drafter cross-references the writ remedy.
- **Mediation:** Section 9 Family Courts Act 1984 mandates reconciliation; for custody, the Family Court frequently refers parents to in-house counselling / mediation before deciding on custody.
