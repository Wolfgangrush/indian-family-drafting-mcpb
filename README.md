# Wolfgang Rush — Indian Family Court Drafting

**MCPB Desktop Extension** for drafting pleadings before Indian Family Courts and the matrimonial-jurisdiction tier of District Courts.

Personal-law-aware: covers Hindu Marriage Act, Special Marriage Act, Indian Divorce Act, Parsi Marriage and Divorce Act, Muslim personal law, Domestic Violence Act 2005, Guardians and Wards Act, HAMA, JJ Act / CARA. Designed for Indian advocates using **Claude Desktop App**. Local-execution. Zero data collection.

> *Also available as a Claude Code Plugin (for developers using the Claude Code CLI):*
> *[github.com/Wolfgangrush/indian-family-drafting-litigation](https://github.com/Wolfgangrush/indian-family-drafting-litigation)*

---

## Case types

| Case type | Statutory anchor |
|---|---|
| Divorce petition | HMA Section 13 / SMA Section 27 / Indian Divorce Section 10 / Muslim PL |
| Judicial separation | HMA Section 10 / SMA Section 23 |
| Nullity petition | HMA Sections 11 / 12 / SMA Sections 24 / 25 |
| Restitution of conjugal rights | HMA Section 9 / SMA Section 22 |
| Maintenance application | Section 125 CrPC / 144 BNSS / HMA Section 24 / HAMA |
| Custody petition | Guardians and Wards Act 1890 |
| Adoption petition | HAMA 1956 / JJ Act 2015 / CARA regulations |
| DV Act application | Domestic Violence Act 2005 (Sections 12, 18-23) |

## Install

1. Open **Claude Desktop App**
2. **Settings → Extensions → Install Extension**
3. Select `wolfgang-indian-family-drafting.mcpb`
4. Enable

## System requirements

- Claude Desktop App ≥ 0.10.0 · Python ≥ 3.10 (uv runtime auto-bundled)
- `pandoc` for .docx · `pdftotext` for PDF case-files

## Tools

| Tool | Purpose |
|---|---|
| `list_case_types` | Discover 8 available Family case types |
| `get_case_type_format` | Retrieve drafting template for a case type |
| `get_agent_instructions` | Retrieve six-agent pipeline stage instructions |
| `get_pleading_base` | Retrieve universal Family pleading skeleton |
| `read_case_folder` | Read case folder for fact extraction |
| `save_draft_as_docx` | Render markdown → filing-grade .docx |

## Privacy

Zero data collection. Three-layer privacy firewall (L1 substitution → L2 LLM-blind → L3 re-substitution).

Canonical privacy policy: **<https://wolfgangrush.github.io/privacy/>**

## Confidentiality

Case content may attract privilege under **Section 132 BSA 2023** / **Section 126 IEA 1872**. The user remains professionally responsible.


## ⚠️ AI verification disclaimer · 🔒 Pseudonymisation procedure

> **⚠️ AI can make mistakes — please verify the information before filing.**
> Every draft produced by this connector is a STARTING POINT. The Verifier
> agent runs an anti-hallucination firewall and the Overseer agent runs an
> opposing-counsel review, but neither replaces an advocate's independent
> verification of statutory references, citation accuracy, factual fidelity,
> and Registry-formatting compliance with the user's High Court / forum.
> The advocate filing the pleading remains responsible for the contents.
>
> **🔒 Protected by pseudonymisation procedure.** The Reader agent applies a
> domain-specific privacy firewall as the first step of the pipeline — party
> names, addresses, identifying numbers (FIR / CR / Crime / Suit / Diary /
> SLP / lower-court case numbers), PAN / Aadhaar references, financial
> figures, witness names, and statutory-notice references are substituted
> with structural placeholders BEFORE any downstream agent sees the facts.
> The Drafter, Verifier, Refiner, and Overseer agents process placeholders
> only. Real values are re-substituted at the final docx render step on the
> user's local machine. No real identifying data leaves the case folder.

## License

MIT.

## Publisher

**Rushikesh R. Mahajan**, Advocate, Bombay HC Nagpur, publishing as **Wolfgang Rush**. advrushikeshravindramahajan@gmail.com

## Source

<https://github.com/Wolfgangrush/indian-family-drafting-mcpb>

## Sample cases

See `SAMPLE-CASES/`.
