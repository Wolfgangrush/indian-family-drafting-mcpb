---
name: _family_pleading_base
description: Universal Indian family-law / matrimonial-jurisdiction pleading skeleton. Shared base for all 8 family-law case-type skills (divorce / judicial separation / restitution of conjugal rights / nullity / maintenance / custody / DV Act / adoption). Holds the standard structure (Cause Title -> Parties block -> Statutory Opening -> Marriage Particulars block -> Domestic Chronology -> Children block (where applicable) -> Property block (where applicable) -> Grounds -> Prayer -> Reconciliation/ADR averment -> Verification -> Supporting Affidavit -> List of Documents -> Accompanying Applications). NOT invoked directly — extended by every case-type skill in this plugin.
allowed-tools: Read
---

# `_family_pleading_base` — universal Family-Court pleading skeleton

This base skill defines the **structural shape** of any family-law pleading. Case-type skills (`divorce-petition-draft`, `maintenance-application-draft`, etc.) extend this base with case-type-specific Grounds, Prayer, and accompanying-application clauses.

## Universal skeleton

```
1. CAUSE TITLE
   {{family_config.court_designation}}
   {{case_type.proceeding_designation_line}} (e.g. "PETITION NO. ___ OF 20__")
   IN THE MATTER OF:
   [Petitioner's full name, age, occupation, address]                ... PETITIONER
                                       Versus
   [Respondent's full name, age, occupation, address]               ... RESPONDENT

2. STATUTORY OPENING
   PETITION UNDER {{case_type.statutory_opening_clause}}
   (e.g. "SECTION 13(1)(ia) OF THE HINDU MARRIAGE ACT, 1955 FOR
   DISSOLUTION OF MARRIAGE BY DECREE OF DIVORCE ON THE GROUND OF
   CRUELTY")

3. PRELUDE / SALUTATION
   MOST RESPECTFULLY SHEWETH:

4. INTRODUCTION / PARTIES
   The Petitioner and the Respondent are husband and wife, having
   solemnised their marriage on [date] at [place] according to
   [Hindu rites and ceremonies / Special Marriage Act registration /
   Christian religious ceremony / Muslim Nikah / Parsi Marriage and
   Divorce Act ceremony — as applicable].

5. MARRIAGE PARTICULARS
   - Date of marriage
   - Place of marriage
   - Form of marriage (rites / registration)
   - Witnesses (where solemnised)
   - Marriage registration particulars (if registered)
   - Children of the marriage (names, DOBs, current custody position)

6. DOMESTIC CHRONOLOGY
   - Date of commencement of cohabitation
   - Last date of cohabitation
   - Date of separation (if any)
   - Period of stay-together
   - Place of last residence as husband and wife (relevant for Section
     19 HMA / Section 31 SMA territorial jurisdiction)

7. GRIEVANCE NARRATIVE (case-type-specific)
   Chronological narrative of the events constituting the ground
   invoked. Each event with date, place, and (where applicable) the
   document evidencing it.

8. JURISDICTION
   This Hon'ble Court has jurisdiction to try and entertain this
   Petition under Section [19 HMA / 31 SMA / 7 FCA / 27 SMA / etc.]
   because [last cohabitation place / petitioner's residence /
   place where the marriage was solemnised / where the cause of
   action arose — per the applicable statute's territorial-
   jurisdiction clause].

9. PRIOR PROCEEDINGS
   - DV Act proceedings (if any)
   - Section 125 BNSS proceedings (if any)
   - Mediation reports (if any)
   - Police complaints (if any)
   - Prior matrimonial proceedings (if any)

10. GROUNDS
    {{case_type.grounds_structure}}

11. RECONCILIATION / ADR AVERMENT
    [For Family Courts under FCA 1984:] The Petitioner is / is not
    willing to attempt reconciliation, and submits that reconciliation
    is / is not possible on the facts pleaded above (Section 9 Family
    Courts Act 1984).
    [For District Courts in States without Family Courts:] The
    Petitioner is willing to participate in any ADR process the Court
    may refer the matter to (Section 89 CPC).

12. PRAYER
    {{case_type.primary_relief_clauses}}
    + interim reliefs (interim maintenance under Section 24 HMA /
      Section 36 SMA, interim custody, restraining order, where
      applicable)
    + costs

13. VERIFICATION
    I, [Petitioner's name], the Petitioner above-named, do hereby
    verify that the contents of paragraphs ___ to ___ are true to my
    personal knowledge and the contents of paragraphs ___ to ___ are
    based on information received by me and believed by me to be true.

    Verified at [place] on this __ day of [month, year].

                                                   PETITIONER

14. SUPPORTING AFFIDAVIT
    [Per the Family Court Rules of the applicable State]

15. LIST OF DOCUMENTS
    A. Marriage certificate / marriage registration extract
    B. Birth certificates of the children
    C. [Case-type-specific documents]

16. ADVOCATE'S SIGNATURE BLOCK
                                COUNSEL FOR THE PETITIONER
                                [Name]
                                Advocate
                                BCI Enrolment No: [Bar Council number]

17. ACCOMPANYING APPLICATIONS
    [As required by the case-type — interim maintenance application,
    interim custody application, etc.]
```

## Section-by-section reference

- **Section 19 HMA 1955** — territorial jurisdiction for HMA petitions
- **Section 31 SMA 1954** — territorial jurisdiction for SMA petitions
- **Section 7 Family Courts Act 1984** — Family Court subject-matter jurisdiction
- **Section 9 Family Courts Act 1984** — mandatory reconciliation in Family Court proceedings
- **Section 89 CPC** — ADR reference in District Court proceedings
- **Order VI Rule 15 CPC** — verification form (modified for Family Court Rules)

## Statute references the plugin handles

- Hindu Marriage Act 1955
- Special Marriage Act 1954
- Indian Divorce Act 1869 (Christians)
- Parsi Marriage and Divorce Act 1936
- Muslim Personal Law (Shariat) Application Act 1937
- Dissolution of Muslim Marriages Act 1939
- Family Courts Act 1984
- Hindu Adoptions and Maintenance Act 1956
- Hindu Minority and Guardianship Act 1956
- Guardians and Wards Act 1890
- Protection of Women from Domestic Violence Act 2005
- Section 125 BNSS 2023 (formerly Section 125 CrPC 1973)
- Maintenance and Welfare of Parents and Senior Citizens Act 2007
- Juvenile Justice (Care and Protection of Children) Act 2015 (for adoption)


---

## v0.2.1 RENDER DISCIPLINE (load-bearing — Drafter must follow)

**Pandoc + reference.docx + post-pandoc fix script.** The Drafter writes Markdown using the heading discipline below. Pandoc converts the Markdown to `.docx` using the SHIPPED reference.docx at `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/reference.docx` — pre-customised with locked Word styles matching the filing-grade Bombay HC convention (extracted from an actual filed Second Appeal pleading):

- **Body (Normal)** — TNR 14pt, 1.5 line spacing, justified, 0.5cm first-line indent
- **Heading 1** — TNR 14pt **bold + centered** (NOT underlined) — for the Court / Forum / Tribunal header line and the case-number line
- **Heading 2** — TNR 14pt **bold + UNDERLINED + centered + letter-spacing** — for spaced section headers (`F A C T S`, `G R O U N D S`, `P R A Y E R`, `I N D E X`, `S Y N O P S I S`, `L I S T   O F   A N N E X U R E S`, `V E R I F I C A T I O N`)
- **Heading 3** — TNR 14pt **bold + UNDERLINED + centered** — for unspaced section headers (`SUBSTANTIAL QUESTIONS OF LAW`, `ACTS & RULES`, `CITATIONS`) and statutory opening (`WRIT PETITION UNDER ARTICLE 226 …`)
- **Heading 4** — TNR 14pt **bold + UNDERLINED + left-aligned** — for left-anchored bold-underlined headings (`MOST RESPECTFULLY SHEWETH:`)
- **Tables** — `tblLayout = fixed`; first row bold centered; cell margins locked

### Markdown heading mapping

| Markdown | Rendered as | Used for |
|---|---|---|
| `# Heading 1` | Bold centered (no underline) | Court header line; case-number line; cover-page anchors |
| `## Heading 2` | Bold centered UNDERLINED with letter-spacing | Spaced section headers (`## F A C T S`, `## G R O U N D S`, `## P R A Y E R`, `## I N D E X`, `## S Y N O P S I S`, `## L I S T   O F   A N N E X U R E S`, `## V E R I F I C A T I O N`) |
| `### Heading 3` | Bold centered UNDERLINED | Unspaced section headers + statutory opening |
| `#### Heading 4` | Bold left UNDERLINED | `#### MOST RESPECTFULLY SHEWETH:` |
| Body paragraph | TNR 14pt justified 1.5 spacing 0.5cm first-line indent | Everything else |
| `**Bold inline**` | Bold | Property descriptors / annexure markers / key terms inline within Facts narrative |

### Bold-number paragraph convention

Facts and Grounds paragraphs use **BOLD NUMBERS**: `**1.**`, `**2.**`, `**3.**` followed by a tab + body. Renders as the gold-standard pleading layout.

### Two-step pandoc command (Step 2 is NON-NEGOTIABLE)

```bash
# Step 1 — pandoc → .docx with locked Word styles
pandoc draft-v1.md -o draft-v1.docx \
  --reference-doc="${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/reference.docx" \
  --from=markdown+pipe_tables+raw_tex

# Step 2 — force table column widths
python3 "${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/fix_docx_tables.py" draft-v1.docx
```

Step 2 forces column widths on every table — 5-col (Sr.No / Annx / Particulars / Date / Pgs) = 8/8/60/14/10; 4-col = 10/10/65/15; 3-col = 10/75/15; 2-col Dates–Events = 18/82. Locks first-row bold + centered + vertically-centered cells. **Skipping the fix script reproduces the v0.2.0 Index-table defect (Sr.No / Annx columns stacking vertically).**

Do NOT auto-generate a fresh reference.docx in the case folder. Use the shipped one or a `<case-folder>/reference.docx` override.

### Cover-page discipline

INDEX, SYNOPSIS, LIST OF ANNEXURES each begin on a new page (`\newpage` in Markdown) and carry ONLY: forum header (`#`) + case-number line (`#`) + short cause-title (Petitioner short name `///VERSUS///` Respondent short name) + section header (`##`) + table + Counsel block. DO NOT repeat the full party address block on cover pages.

### Pipeline-optionality (advocate-cost discipline)

The full 6-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) is **NOT** mandatory. Only the first three stages are required to produce a filing-grade draft. Stages 4–6 are OPTIONAL QC layers the advocate explicitly invokes. Default exit point is here, after Drafter (~280K tokens). Full pipeline ~600K tokens — disproportionate for routine pleadings.

When `draft-v1.docx` is written, the Drafter's job is complete. The advocate decides whether to invoke the QC stages.
