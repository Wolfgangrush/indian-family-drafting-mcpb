---
name: divorce-petition-draft
description: Draft a divorce petition under any applicable Indian personal law — Hindu Marriage Act 1955 Section 13 (cruelty / desertion / adultery / conversion / unsoundness of mind / venereal disease / renunciation / presumption of death / non-resumption of cohabitation after JS / non-compliance with RCR), Special Marriage Act 1954 Section 27 (same grounds, secular), Indian Divorce Act 1869 Section 10 (Christian — adultery / desertion / cruelty / conversion / unsoundness of mind / etc., post-2001 amendments), Parsi Marriage and Divorce Act 1936 Section 32, Muslim Personal Law (Dissolution of Muslim Marriages Act 1939 — for the wife) / Talaq (for the husband, subject to Muslim Women (Protection of Rights on Marriage) Act 2019). The personal law is sourced from the user's family-config.md — NOT hardcoded. Produces a complete divorce petition with Marriage Particulars + Domestic Chronology + Grievance Narrative + Grounds + Prayer + Verification + Supporting Affidavit + List of Documents + accompanying applications (interim maintenance / custody where children exist). Auto-fires on "draft divorce", "draft HMA divorce", "draft SMA divorce", "Christian divorce", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Divorce Petition Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: PETITION FOR DISSOLUTION OF MARRIAGE BY DECREE OF DIVORCE
case_short_code: DIVORCE
proceeding_designation_line: "HMA PETITION NO. ___ OF 20__" | "SMA PETITION NO. ___ OF 20__" | "M.P. NO. ___ OF 20__" (per family-config)
statutory_opening:
  HMA: "PETITION UNDER SECTION 13(1) OF THE HINDU MARRIAGE ACT, 1955 FOR DISSOLUTION OF MARRIAGE BY DECREE OF DIVORCE"
  HMA_mutual: "PETITION UNDER SECTION 13B OF THE HINDU MARRIAGE ACT, 1955 FOR DISSOLUTION OF MARRIAGE BY MUTUAL CONSENT"
  SMA: "PETITION UNDER SECTION 27 OF THE SPECIAL MARRIAGE ACT, 1954 FOR DISSOLUTION OF MARRIAGE BY DECREE OF DIVORCE"
  SMA_mutual: "PETITION UNDER SECTION 28 OF THE SPECIAL MARRIAGE ACT, 1954 FOR DISSOLUTION OF MARRIAGE BY MUTUAL CONSENT"
  IDA: "PETITION UNDER SECTION 10 OF THE INDIAN DIVORCE ACT, 1869 FOR DISSOLUTION OF MARRIAGE"
  IDA_mutual: "PETITION UNDER SECTION 10A OF THE INDIAN DIVORCE ACT, 1869 FOR DISSOLUTION OF MARRIAGE BY MUTUAL CONSENT"
  Parsi: "PETITION UNDER SECTION 32 OF THE PARSI MARRIAGE AND DIVORCE ACT, 1936"
  Muslim_DMMA: "PETITION UNDER SECTION 2 OF THE DISSOLUTION OF MUSLIM MARRIAGES ACT, 1939 FOR A DECREE OF DISSOLUTION OF MARRIAGE"
grounds_structure:
  - "1. The Petitioner has been treated with cruelty by the Respondent / has been deserted by the Respondent / has been subjected to adultery / [other ground per applicable personal law]."
  - "2. The cruelty / desertion / adultery / [other ground] is established by the events narrated in paragraphs ___ to ___ above."
  - "3. The marriage between the parties has, in any event, irretrievably broken down within the meaning of [Shilpa Sailesh v. Varun Sreenivasan]."
primary_relief_clauses:
  - "(a) Decree of divorce dissolving the marriage between the Petitioner and the Respondent;"
  - "(b) Custody of the minor child(ren) of the marriage be granted to the Petitioner / Respondent, with [visitation / vacation arrangements per the welfare-of-child principle];"
  - "(c) Permanent alimony / maintenance under Section 25 HMA / Section 37 SMA / Section 37 IDA;"
  - "(d) Costs of and incidental to this Petition;"
  - "(e) Such further and other relief as this Hon'ble Court may deem just and proper."
accompanying_applications:
  - interim_maintenance_application  # Section 24 HMA / Section 36 SMA / Section 36 IDA
  - interim_custody_application       # where children exist
  - mediation_consent_form            # for FCA-1984 Family Courts
typical_annexure_order:
  - "A: Marriage certificate / marriage registration extract"
  - "B: Birth certificates of children"
  - "C: Documentary evidence of cruelty / desertion / adultery (medical records, police complaints, communications, etc.)"
  - "D: Income / financial-disclosure documents (Rajnesh v. Neha affidavit)"
  - "E: Prior proceedings (DV Act / Section 125 BNSS / etc.)"
```

## Facts the skill asks for

See `format-from-user.md` for the full intake questionnaire. In summary:

- Parties (full name, age, religion, occupation, current address)
- Marriage particulars (date, place, ceremony / registration)
- Cohabitation chronology
- Children of the marriage
- The ground invoked (cruelty / desertion / adultery / mutual consent / etc.) + the facts establishing it
- Prior proceedings (DV Act, Section 125 BNSS, mediation, police complaints)
- Income / financial-disclosure data (mandatory under *Rajnesh v. Neha (2021) 2 SCC 324*)
- Property held by each party (matrimonial home, streedhan, jointly-acquired assets)

## Pipeline behaviour

The Drafter writes a complete divorce petition + Supporting Affidavit + List of Documents + interim-maintenance / interim-custody applications as required. The Verifier enforces the Section 9 FCA 1984 reconciliation averment (for Family Courts), the personal-law applicability check, and the *Rajnesh v. Neha* financial-disclosure framework. The Refiner enforces State-specific Family-Court Rules formatting. The Overseer flags any vulnerability in the chronology, jurisdiction, grounds, or relief.
