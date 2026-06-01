# Divorce petition — facts needed from the user

The Reader extracts most of the facts below from the documents in `<case-folder>/facts/`. Anything the Reader cannot extract from documents, the advocate supplies in `<case-folder>/notes.md` or in a Claude session.

## Parties

- **Petitioner:** full name, age, religion, occupation, current address
- **Respondent:** full name, age, religion, occupation, current address (or "address not known" if the Respondent's whereabouts are unknown — Reader will flag for substituted service)

## Personal-law selection

The applicable personal law for the divorce is declared in `family-config.md`:

- **Hindu Marriage Act 1955** — both parties are Hindu, Buddhist, Jain, or Sikh by religion (or were so at the time of marriage)
- **Special Marriage Act 1954** — marriage was registered under SMA, regardless of the parties' personal religion
- **Indian Divorce Act 1869** — both parties are Christian
- **Parsi Marriage and Divorce Act 1936** — both parties are Parsi Zoroastrian
- **Muslim Personal Law** — both parties are Muslim (the wife's remedy is under the Dissolution of Muslim Marriages Act 1939; the husband's *talaq* is regulated by the Muslim Women (Protection of Rights on Marriage) Act 2019 in respect of triple talaq)

The Verifier flags any mismatch between the declared personal law and the parties' religion in the case-facts.

## Marriage particulars

- Date of marriage
- Place of marriage
- Form of marriage (Hindu ceremony / SMA registration / Christian religious ceremony / Muslim Nikah / Parsi ceremony)
- Witnesses to the marriage (for HMA / Christian / Parsi)
- Whether the marriage is registered (HMA registration is generally optional, SMA registration is mandatory, Christian registration is mandatory under the Indian Christian Marriage Act 1872)
- Marriage certificate annexure

## Domestic timeline

- Date cohabitation commenced
- Last date of cohabitation
- Date of separation (if separated)
- Place of last residence as husband and wife (Section 19 HMA / Section 31 SMA territorial jurisdiction)
- Periods of separation and reunion (if any)

## Children of the marriage

For each child:

- Name
- Date of birth
- Current age
- Current custody / living arrangement
- School / education status

## Ground invoked

One of (per the applicable personal law):

- **Cruelty** (mental / physical / financial) — facts establishing the conduct
- **Desertion** — date of desertion, period, factual matrix
- **Adultery** — facts of the adultery, identity (if known) of the co-respondent
- **Conversion** — date of the Respondent's conversion, religious denomination converted to
- **Mental disorder / unsoundness of mind** — medical diagnosis, period
- **Venereal disease** — medical diagnosis, period
- **Renunciation** — date of renunciation, sect entered
- **Presumption of death** — period of unheard absence
- **Non-resumption of cohabitation after judicial separation** — decree date, period elapsed
- **Non-compliance with restitution-of-conjugal-rights decree** — decree date, period elapsed
- **Mutual consent** — date of separation, period (>1 year for HMA Section 13B / SMA Section 28; >2 years for IDA Section 10A)

## Prior proceedings

- DV Act application — case number, status, outcome
- Section 125 BNSS / Section 125 CrPC application — case number, status, outcome
- Section 24 HMA / Section 36 SMA interim maintenance — case number, status, outcome
- Mediation report (if any)
- Police complaint (if any) — FIR number, status

## Financial disclosure (Rajnesh v. Neha framework)

The *Rajnesh v. Neha (2021) 2 SCC 324* affidavit-of-disclosure is mandatory in every matrimonial application involving maintenance. Both parties' income, assets, liabilities, lifestyle markers, and dependants must be disclosed. The Reader extracts this from salary slips / ITRs / bank statements / property documents supplied in `facts/`.

## Permanent alimony / maintenance sought

Quantum proposed by the Petitioner + the income / lifestyle / dependant basis for the quantum.

## Property reliefs sought

- Matrimonial home (return of possession / partition / use)
- Streedhan return
- Jointly-acquired assets

## Custody reliefs sought (where children exist)

- Permanent custody to which parent
- Visitation arrangements for the non-custodial parent
- Vacation arrangements
- Education / medical decision-making authority
- Welfare-of-the-child basis (per *Gaurav Nagpal v. Sumedha Nagpal (2009) 1 SCC 42*)
