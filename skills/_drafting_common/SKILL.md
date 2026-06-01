---
name: _drafting_common
description: Shared reference for all family-law drafting skills (divorce / judicial separation / restitution of conjugal rights / nullity / maintenance / custody / DV Act / adoption). Holds the anti-pollution rules, the privacy firewall protocol (placeholder substitution for party names, minor identifiers, and intimate-partner details before any AI processing; real-name re-substitution only on the user's local machine in the Refiner step), the AI-style-marker blacklist, citation-discipline rules, and the family-law-specific risk constraints. NOT invoked directly — referenced from every case-type skill in this plugin.
allowed-tools: Read
---

# `_drafting_common` — shared family-law drafting infrastructure

## Privacy firewall

Family-law cases routinely contain the most sensitive personal data in any pleading the plugin will encounter — minor children's names and DOBs, intimate-partner conduct allegations, mental-health disclosures, financial disclosures of both spouses, religious affiliation, and (in DV Act matters) shared-household particulars. The plugin's privacy discipline is therefore stricter for family-law than for any sibling plugin.

**Discipline:**

1. **Reader** substitutes every party name, every minor's name, every intimate-partner detail with structural placeholders (`[Petitioner]`, `[Respondent]`, `[Minor-Child-1]`, `[Minor-Child-2]`, etc.) and stores the placeholder → real-name mapping in the *header section* of `case-facts.md` on the user's local machine only.
2. **Format / Drafter / Verifier / Overseer** operate **only** on the placeholder-substituted content. The underlying AI runtime never holds the real names.
3. **Refiner** is the only agent that touches the placeholder → real-name re-substitution, and it does so by reading the local-only mapping in `case-facts.md` and replacing placeholders in the final `.docx` — strictly on the user's machine.
4. The mapping itself never leaves `case-facts.md`. The plugin's `.gitignore` explicitly excludes `case-facts.md` so it cannot be committed accidentally.

## AI-style-marker blacklist

The Refiner strips the following AI-tell patterns from every draft before output:

- Em-dash (`—`) used as a sentence-internal pause (replaced with semicolon or proper comma-bounded clause)
- Sentence-final *thereby* / *hereby* / *whereby* without a verb attached
- *Moreover*, *furthermore*, *additionally*, *in addition* as sentence-openers
- *Navigate* (used metaphorically), *delve* (used metaphorically), *foster* (used metaphorically), *robust*, *seamless*
- *It is important to note that*, *it should be noted that*, *worthy of note* — replaced with direct prose
- Bullet-list-style structure in Statement of Facts (Statement of Facts must be a chronological narrative, not a list)
- Three-em-dash separators inside the pleading body

## Citation discipline

The Drafter does **not** generate case names + citations from training memory. Every case citation must trace to a user-supplied source in `<case-folder>/laws/` (PDF of the judgment) or `<case-folder>/notes.md` (advocate's existing citation list). Untraceable citations are written as `[CITATION NEEDED]` placeholders for the advocate to fill manually before filing.

The family-law domain has well-known headline cases that the AI's training memory may misquote with confident-sounding but wrong citations:

- *Shilpa Sailesh v. Varun Sreenivasan* — divorce by mutual consent, irretrievable breakdown
- *Joseph Shine v. Union of India* — adultery decriminalisation
- *Vishaka v. State of Rajasthan* — sexual harassment workplace
- *Indra Sarma v. V.K.V. Sarma* — DV Act, live-in relationships
- *Rajnesh v. Neha* — maintenance computation framework
- *Gaurav Nagpal v. Sumedha Nagpal* — custody, welfare-of-child
- *Yashita Sahu v. State of Rajasthan* — custody, international parental child-removal

The Verifier specifically flags any citation to these (or any other) case names whose accompanying year / volume / SCC / SCC-page reference cannot be verified against a user-supplied source.

## Family-law forum awareness

The Drafter respects the State-specific forum architecture:

- **States with Family Courts established under the Family Courts Act 1984** (Maharashtra, Karnataka, Andhra Pradesh, Telangana, Gujarat, Tamil Nadu, Kerala, Madhya Pradesh, Bihar, Rajasthan, Uttar Pradesh, etc.) — matrimonial petitions are filed before the Family Court; cause-title says *IN THE COURT OF THE PRINCIPAL JUDGE, FAMILY COURT AT [PLACE]* or *IN THE COURT OF THE FAMILY JUDGE AT [PLACE]*.
- **States / districts without Family Courts** — matrimonial petitions are filed before the District Court / District Judge; cause-title says *IN THE COURT OF THE DISTRICT JUDGE AT [PLACE]*.

The user's `family-config.md` declares the State and the specific court; the Format agent substitutes accordingly.

## Section 9 Family Courts Act 1984 — mandatory reconciliation

Where the Family Court has jurisdiction, Section 9 of the Family Courts Act 1984 makes reconciliation a mandatory preliminary step. Pleadings filed before the Family Court must aver that the petitioner is willing to attempt reconciliation, or has attempted reconciliation, or that reconciliation is not possible on the facts pleaded. The Drafter includes this averment automatically when `family-config.md` declares the forum is a Family Court under FCA 1984; the Overseer flags any draft that omits the averment.

## Section 89 CPC ADR-reference

For pleadings filed before the District Court (in States without Family Courts), Section 89 CPC requires the Court to attempt ADR — the Drafter includes the averment that the petitioner is willing to participate in ADR (mediation / conciliation / Lok Adalat / arbitration) when ADR is consistent with the relief sought.

## Personal-law applicability check

The Drafter does **not** assume which personal law applies. The user's `family-config.md` carries an explicit `applicable_personal_law` field — Hindu Marriage Act 1955 / Special Marriage Act 1954 / Indian Divorce Act 1869 (Christians) / Parsi Marriage and Divorce Act 1936 / Muslim Personal Law (Shariat) Application Act 1937 + Dissolution of Muslim Marriages Act 1939 / Family Courts Act 1984 (procedural) / Hindu Adoptions and Maintenance Act 1956 / Section 125 BNSS (secular maintenance) / DV Act 2005 (secular). The Verifier checks the parties' religion in `case-facts.md` against the declared applicable law; an HMA divorce filed where one party is Muslim, or an IDA divorce filed where neither party is Christian, gets flagged at Verifier stage and corrected at Refiner.


---

## v0.2.1 RENDER DISCIPLINE (load-bearing — Drafter must follow)

**Pandoc + reference.docx + post-pandoc fix script.** The Drafter writes Markdown using the heading discipline below. Pandoc converts the Markdown to `.docx` using the SHIPPED reference.docx at `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/reference.docx` — pre-customised with locked Word styles matching the filing-grade Bombay HC Nagpur convention (extracted from an actual filed Second Appeal pleading):

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


---

## v0.2.2 OUTPUT-PAIRING DISCIPLINE (load-bearing — every agent must follow)

**Every `.md` output artifact MUST be paired with a `.docx`.** Advocates do not natively read Markdown — they read Word. Every pipeline output (case-facts.md from Reader, format-shell.md from Format, draft-v1.md from Drafter, verification-report.md from Verifier, draft-v2.md from Refiner, opposing-notes.md from Overseer) must have a corresponding `.docx` rendered with the same locked Word styles.

**This plugin produces pleadings** — the shipped reference.docx is the pleading variant (TNR 14pt 1.5 spacing, Heading 2 bold + UNDERLINED + centered with letter-spacing for the spaced `F A C T S` effect).

### How to produce the paired `.docx`

Every agent runs the shipped helper script as its final post-`.md`-write step:

```bash
bash "${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/pair_md_to_docx.sh" <output.md>
```

The helper:
1. Resolves the reference.docx in `${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/reference.docx`
2. Runs pandoc with `--reference-doc` and `--from=markdown+pipe_tables+raw_tex` to produce the `.docx`
3. Runs the shipped `fix_docx_tables.py` to force column widths on every table

For overriding (e.g., a per-case-folder reference.docx), pass the reference.docx as the second argument:

```bash
bash "${CLAUDE_PLUGIN_ROOT}/skills/_family_pleading_base/pair_md_to_docx.sh" \
    <output.md> <case-folder>/reference.docx
```

### Per-agent output-pairing map

| Agent | `.md` output | Paired `.docx` |
|---|---|---|
| Reader | `case-facts.md` | `case-facts.docx` |
| Format | `format-shell.md` | `format-shell.docx` |
| Drafter | `draft-v1.md` | `draft-v1.docx` |
| Verifier | `verification-report.md` | `verification-report.docx` |
| Refiner | `draft-v2.md` | `draft-v2.docx` |
| Overseer | `opposing-notes.md` + `final-draft.md` | `opposing-notes.docx` + `final-draft.docx` |

Every agent calls `pair_md_to_docx.sh` once for each `.md` it writes. Skipping this step leaves the advocate with `.md` files that cannot be opened natively in Word.
