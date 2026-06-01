---
name: dv-act-application-draft
description: Draft an application for reliefs under the Protection of Women from Domestic Violence Act 2005 (DV Act), filed before the Magistrate of the First Class having jurisdiction. Covers the full menu of DV-Act reliefs — Protection Order (Section 18), Residence Order (Section 19), Monetary Relief (Section 20, including maintenance), Custody Order (Section 21), Compensation Order (Section 22), and ex parte Interim and Final Orders (Section 23). The DV Act is secular and applies to all women regardless of religion. Drafts the application with the mandatory "domestic relationship" (Section 2(f)) and "shared household" (Section 2(s)) elements pleaded clearly. The applicable case-law framework includes *Indra Sarma v. V.K.V. Sarma (2013) 15 SCC 755* (definition of domestic relationship), *S.R. Batra v. Taruna Batra (2007) 3 SCC 169* and *Satish Chander Ahuja v. Sneha Ahuja (2021) 1 SCC 414* (shared household — the latter overruled the former). Auto-fires on "draft DV application", "draft Section 12 DV", "draft domestic violence", "draft DV Act", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# DV Act Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION FOR RELIEFS UNDER THE PROTECTION OF WOMEN FROM DOMESTIC VIOLENCE ACT, 2005
case_short_code: DV
statutory_opening: "APPLICATION UNDER SECTION 12 OF THE PROTECTION OF WOMEN FROM DOMESTIC VIOLENCE ACT, 2005 FOR ORDERS UNDER SECTIONS 18, 19, 20, 21, AND 22 OF THE SAID ACT"
grounds_structure:
  - "1. The Applicant is an aggrieved person within the meaning of Section 2(a) of the DV Act, having been subjected to domestic violence by the Respondent(s)."
  - "2. The Applicant and the Respondent(s) are in a 'domestic relationship' within the meaning of Section 2(f) (relationship by consanguinity / marriage / through a relationship in the nature of marriage / through adoption / family members living together as a joint family). The case-law framework is established by *Indra Sarma v. V.K.V. Sarma (2013) 15 SCC 755*."
  - "3. The Applicant has resided in a 'shared household' within the meaning of Section 2(s) (the household where the Applicant lives or has lived in a domestic relationship). Per *Satish Chander Ahuja v. Sneha Ahuja (2021) 1 SCC 414* (which overruled *S.R. Batra v. Taruna Batra*), the shared household includes a household belonging to the joint family of which the Respondent is a member, regardless of whether the Respondent has any title / interest in it."
  - "4. The acts of domestic violence (Section 3 of the DV Act) constituting physical / sexual / verbal / emotional / economic abuse are narrated in paragraphs ___ to ___."
primary_relief_clauses:
  - "(a) Protection Order under Section 18 restraining the Respondent(s) from committing any act of domestic violence;"
  - "(b) Residence Order under Section 19 restraining the Respondent from dispossessing or disturbing the Applicant from the shared household;"
  - "(c) Monetary Relief under Section 20 including maintenance, medical expenses, loss-of-earnings, and other expenses;"
  - "(d) Custody Order under Section 21 (where minors are involved);"
  - "(e) Compensation under Section 22 for the injuries caused by the domestic violence;"
  - "(f) Ex parte Interim and Final Orders under Section 23 pending final disposal;"
  - "(g) Costs;"
  - "(h) Such further relief as this Hon'ble Court may deem just."
accompanying_applications:
  - dir_report_request  # Domestic Incident Report under Section 9 / Form I
  - ex_parte_interim_order_application  # Section 23 emergency reliefs
```

## Mandatory pleadings

- **Section 2(f) "domestic relationship"** — must be pleaded with particulars
- **Section 2(s) "shared household"** — must be pleaded with the post-*Satish Chander Ahuja* understanding
- **Section 3 "domestic violence"** — physical / sexual / verbal / emotional / economic abuse — must be pleaded with specific instances, dates, places, witnesses where available
- **Domestic Incident Report** under Section 9 / Form I — if previously filed with the Protection Officer, must be annexed
- **Mandatory respondents** — the DV Act permits action against male and (post-*Hiral P. Harsora v. Kusum Narottamdas Harsora (2016) 10 SCC 165*) female relatives of the male respondent within the shared household

## Cross-statute interaction

- DV Act maintenance (Section 20) is concurrent with Section 125 BNSS maintenance — the Applicant may seek either or both, with credit for amounts received under the other.
- DV Act remedies are concurrent with HMA / SMA / IDA matrimonial remedies — filing under DV does not preclude divorce or other matrimonial petitions.
