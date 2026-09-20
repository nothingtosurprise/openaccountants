---
name: de-social-contributions
description: Use this skill whenever asked about German social insurance contributions (Sozialversicherungsbeitraege) for self-employed individuals, freelancers (Freiberufler), or sole proprietors (Einzelunternehmer). Trigger on phrases like "German health insurance", "Krankenversicherung", "GKV", "PKV", "Pflegeversicherung", "Rentenversicherung", "KSK", "Kuenstlersozialkasse", "Berufsgenossenschaft", "Unfallversicherung", "social contributions Germany", "Krankenkasse debit", or any question about German social insurance obligations. Also trigger when classifying bank statement transactions showing Krankenkasse debits, KSK direct debits, Berufsgenossenschaft invoices, or Deutsche Rentenversicherung payments. ALWAYS read this skill before touching any German social contribution work.
version: 2.0
jurisdiction: DE
tax_year: 2026
last_updated: 2026-09-19
review_status: pending_review
drafted_by: OpenAccountants
approved_by: pending
depends_on:
  - social-contributions-workflow-base
category: international
tier: 2
license: AGPL-3.0-or-later (code) / OpenAccountants Guide License v1.0 (content)
---

# Social insurance contributions for the self-employed in Germany (Sozialversicherungsbeiträge)

How a self-employed person in Germany is insured for health, long-term care, pension, accident and unemployment, what each contribution is charged on, when it is due, and how the debits look on a bank statement. It is for freelancers (Freiberufler), sole proprietors (Einzelunternehmer), artists and publicists insured through the Künstlersozialkasse (KSK), and businesses that owe the artists' social levy. It is not a payroll Guide: the shares of employees and employers are in `germany-payroll` and `de-payroll`. Figures are for tax year 2026. The long-term care rates have been in force since 1 January 2025; the health ministry's page, read in September 2026, prints them as the current rates. The health funds' payment rules (Beitragsverfahrensgrundsätze Selbstzahler) are the version of 1 January 2025, which the funds' association lists as the current one. Statute figures are read from the consolidated federal law pages.

## Section 1: Quick reference

**Quick reference table**

| Field | Value |
| --- | --- |
| Country | Germany (Bundesrepublik Deutschland) |
| Primary Legislation | SGB IV (general), SGB V (health), SGB VI (pension), SGB XI (care), SGB VII (accident), SGB III (unemployment), KSVG (artists) |
| Supporting Legislation | § 10 EStG (Vorsorgeaufwendungen, tax deductibility) |
| Regulatory Bodies | GKV-Spitzenverband (health), Deutsche Rentenversicherung (pension), Künstlersozialkasse (KSK), Berufsgenossenschaften (accident), Bundesagentur für Arbeit (unemployment) |
| Rate Publisher | Federal Government and BMAS (yearly Sozialversicherungsrechengrößen-Verordnung); health ministry (average additional rate) |
| Currency | EUR only |
| Who pays | A self-employed voluntary member pays the whole health and care contribution alone. There is no employer share |
| Statutory health rate | Reduced rate without sick pay, general rate with sick pay, plus the fund's own additional rate. See the health tables below |
| Contribution base, health and care | All income, not less than the minimum base and not more than the ceiling. See the tables below |
| Pension | Compulsory for some professions only. See Rule 4 |
| Care insurance | Rate depends on being a parent and on the number of children under 25. See the care table below |
| KSK levy rate (Verwerter) | See Rule 6 |
| Health and care payment due | By the 15th of the month AFTER the contribution month. See Rule 10 |
| Contributor | Open Accountants |
| Validated by | Pending. Requires sign-off by a licensed Steuerberater |
| Validation date | Pending |

Read this whole section before computing or classifying anything.

**Statutory health insurance: general rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_5/__241.html |
| General rate, for members WITH a sick pay claim. A main-occupation self-employed member has that claim only after electing it (Wahlerklärung, § 44(2) SGB V). Full rate, without the fund's additional rate | 14.6% | § 241 SGB V: "Der allgemeine Beitragssatz beträgt 14,6 Prozent der beitragspflichtigen Einnahmen" |

**Statutory health insurance: reduced rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_5/__243.html |
| Reduced rate, for members WITHOUT a sick pay claim. This is the normal case for a main-occupation self-employed member. Full rate, without the fund's additional rate | 14.0% | § 243 SGB V: "Der ermäßigte Beitragssatz beträgt 14,0 Prozent der beitragspflichtigen Einnahmen" |

**Statutory health insurance: the ministry's 2026 amounts for voluntary members**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesgesundheitsministerium.de/beitraege |
| AVERAGE additional rate for 2026, set by the health ministry. It is NOT what a given fund charges: each fund sets its own rate. The ministry uses the average for its example amounts below | 2.9% | "Für das Jahr 2026 beträgt der durchschnittliche Zusatzbeitragssatz 2,9 Prozent" |
| Minimum monthly contribution BASE of a voluntary member, the self-employed included. A lower real income is lifted to this base. It is a base, not a contribution | EUR 1,318.33 | "Mindestbemessungsgrundlage" |
| Ministry's printed MINIMUM monthly health contribution, self-employed or other voluntary member, NO sick pay claim. Includes the average additional rate, so the real amount depends on the fund. Care contribution not included | EUR 222.80 | "Mindestbeitrag für Selbstständige/sonstige freiwillig Versicherte" |
| Ministry's printed MINIMUM monthly health contribution, self-employed member WITH sick pay claim. Same caveats | EUR 230.71 | "Mindestbeitrag für Selbstständige" |
| Ministry's printed MAXIMUM monthly health contribution, self-employed or other voluntary member, NO sick pay claim (income at or above the ceiling). Same caveats | EUR 982.31 | "Höchstbeitrag für Selbstständige/sonstige freiwillig Versicherte" |
| Ministry's printed MAXIMUM monthly health contribution, self-employed member WITH sick pay claim. Same caveats | EUR 1,017.19 | "Höchstbeitrag für Selbstständige" |

**Health and care insurance: contribution ceiling**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesregierung.de/breg-de/aktuelles/beitragsgemessungsgrenzen-2386514 |
| Contribution ceiling (Beitragsbemessungsgrenze) of statutory health and care insurance, per month. Income above it carries no health or care contribution | EUR 5,812.50 | "Beitragsbemessungsgrenze 2026 auf jährlich 69.750 Euro beziehungsweise 5.812,50 Euro im Monat" |
| The same ceiling per year | EUR 69,750 | Same sentence |

**Long-term care insurance (soziale Pflegeversicherung)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesgesundheitsministerium.de/themen/pflege/online-ratgeber-pflege/die-pflegeversicherung/finanzierung |
| Base rate. Also the rate of a parent with one child, for life, whatever the child's age. Full rate: a self-employed voluntary member pays it alone | 3.6% | "Seit dem 1. Januar 2025 beträgt der Beitragssatz 3,6 Prozent der beitragspflichtigen Einnahmen" |
| Rate of a CHILDLESS member, from the month after turning 23. Full rate, printed by the ministry | 4.2% | "bei Kinderlosen sind es 4,2 Prozent" |
| The childless surcharge that is inside that childless rate | 0.6% | "Beitragszuschlag für Kinderlose in Höhe von 0,6 Prozent der beitragspflichtigen Einnahmen" |
| Parent with two children under 25. Full rate | 3.35% | Page row: "Mitglieder mit 2 Kindern" |
| Parent with three children under 25. Full rate | 3.1% | Page row: "Mitglieder mit 3 Kindern" |
| Parent with four children under 25. Full rate | 2.85% | Page row: "Mitglieder mit 4 Kindern" |
| Parent with five or more children under 25. Full rate. Not the unemployment insurance rate, which happens to be the same number | 2.6% | Page row: "Mitglieder mit 5 und mehr Kindern" |
| MINIMUM monthly care contribution of a voluntary member since 1 January 2026, before any childless surcharge or parent reduction | EUR 47.46 | "SPV-Mindestbeitrag für freiwillige Mitglieder" |
| The ministry's printed highest monthly care contribution since 1 January 2026 (page label: Höchstbeitrag Pflegeversicherung, not labelled for voluntary members), before any childless surcharge or parent reduction. A fund's notice to a member who pays alone can differ by a cent | EUR 209.26 | "Höchstbeitrag Pflegeversicherung" |

- **Who pays which care rate.** The childless rate is not charged to parents, to members born before 1 January 1940, or to the other groups named in § 55(3) SGB XI. A parent never pays the childless rate, even when all children are grown up. The lower rates for two or more children last only while those children are under 25. After that the parent is back on the base rate. The member must prove parenthood and the number of children under 25 to the care fund. See § 55(3) and (3a) SGB XI at https://www.gesetze-im-internet.de/sgb_11/__55.html Do not take the rate itself from that statute page: it still prints an older base rate, because the rise was made by regulation.
- **Employee shares on the ministry page are not for the self-employed.** The ministry's list also prints an employee share in brackets after each rate. That is the share of an employee. A self-employed voluntary member pays the full rate alone under § 59(4) SGB XI: https://www.gesetze-im-internet.de/sgb_11/__59.html

**Pension insurance: rate and the lowest and highest monthly contribution**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026 |
| Contribution rate of the general pension insurance. A self-employed payer bears the full rate alone. An artist insured through the KSK pays half to the KSK (Rule 5) | 18.6% | "Dieser beträgt 2026 weiterhin 18,6 Prozent" |
| MINIMUM monthly contribution in voluntary insurance. Form V0091 (next table) prints the same amount as the minimum for compulsorily insured self-employed persons | EUR 112.16 | "steigt ab 1. Januar 2026 auf 112,16 Euro" |
| MAXIMUM monthly contribution in voluntary insurance. Form V0091 prints the same amount as the maximum for compulsorily insured self-employed persons | EUR 1,571.70 | "Der Höchstbetrag steigt auf 1.571,70 Euro im Monat" |

**Pension insurance: contributions of compulsorily insured self-employed persons (pension insurer's form V0091 for 2026)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/SharedDocs/Formulare/DE/_pdf/V0091.pdf?__blob=publicationFile&v=4 |
| STANDARD monthly contribution (Regelbeitrag): payable when no other income is proven. One value for west and east | EUR 735.63 | Second amount in the form's row "Mindestbeitrag Regelbeitrag halber Regelbeitrag Höchstbeitrag" |
| HALF standard monthly contribution: may be chosen until the end of the third calendar year after the year the self-employed work began | EUR 367.82 | Third amount in the same row: "Bis zum Ende des 3. Kalenderjahres nach dem Jahr der Aufnahme der selbständigen Tätigkeit" |
| Minimum monthly contribution BASE for compulsory and voluntary insurance. A base, not a contribution. Sole craftspeople and midwives have other minimum bases. Not the Minijob limit, which happens to be the same number | EUR 603 | "Die Mindestbeitragsbemessungsgrundlage für die Versicherungspflicht beträgt ab 1.1.2026 monatlich 603 EUR" |

- **Which year the pension amounts are for.** Form V0091 says its values hold only for contributions paid in 2026 for 2026. Voluntary contributions for 2026 may still be paid until 31 March 2027, but the form warns that the minimum and maximum can then be different.

**Yearly reference values (Sozialversicherungsrechengrößen-Verordnung 2026)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.recht.bund.de/bgbl/1/2025/278/regelungstext.pdf?__blob=publicationFile&v=3 |
| Contribution ceiling of the general PENSION insurance, per month. It is also the unemployment insurance ceiling. NOT the health ceiling | EUR 8,450 | "umgerechnet auf den Monat ergeben sich 8 450 Euro" |
| The same pension ceiling per year | EUR 101,400 | "in der allgemeinen Rentenversicherung auf 101 400 Euro jährlich" |
| Reference amount (Bezugsgröße), per month. A base for other amounts: the standard pension contribution, the minimum health base, unemployment insurance on application. Not a ceiling and not an amount anyone pays | EUR 3,955 | "Umgerechnet auf den Monat ergeben sich 3 955 Euro" |
| Reference amount per year | EUR 47,460 | "für das Jahr 2026 beträgt 47 460 Euro" |
| General compulsory-insurance threshold (Jahresarbeitsentgeltgrenze, JAEG), yearly regular pay. For EMPLOYEES only: above it an employee may leave statutory health insurance. It is not a ceiling and it does not apply to the self-employed | EUR 77,400 | "für das Jahr 2026 auf 77 400 Euro festgesetzt" |

**Conservative defaults**

| Ambiguity | Default |
| --- | --- |
| Unknown GKV or PKV | STOP. Do not compute without this |
| Unknown additional rate (Zusatzbeitrag) | Look up the fund's own rate. Use the ministry's average in the health table only for an estimate, and say that it is an estimate |
| Unknown whether the client is a parent | Apply the childless rate in the care table and flag it |
| Unknown profession (pension obligation) | Do not assume the pension is voluntary. Check the list in Rule 4 first and flag for reviewer |
| Unknown Hauptberuflich vs Nebenberuflich | Flag for reviewer |
| Unknown income for GKV | Do not assume the minimum base. If and as long as a member does not hand in proof of income when the fund asks for it, the fund charges on the ceiling (§ 240(1) sentence 2 SGB V). Within twelve months after the fund has made that assessment known, the member can apply for a new assessment for the periods for which proof is handed in (§ 240(1) sentence 3). Ask for the latest income tax assessment notice |

## Section 2: Required inputs and refusal catalogue

### Required inputs

**Minimum viable:** health insurance type (GKV or PKV), current or expected monthly income from all sources, whether the client is a parent, and the number of children under 25.

**Recommended:** GKV fund name (for the fund's own additional rate), whether sick pay was elected, profession (for the pension obligation check), age, start date of the self-employed work, Einkommensteuerbescheid for the prior year.

**Ideal:** complete Einkommensteuererklärung, GKV contribution notice, KSK membership confirmation (if applicable), pension insurer's contribution notice, Berufsgenossenschaft invoice.

### Refusal catalogue

- **R-DE-SC-1: GKV vs PKV unknown.** Trigger: client has not confirmed insurance type. Message: "The distinction between GKV and PKV fundamentally changes the calculation. Cannot proceed without this information."
- **R-DE-SC-2: PKV premium computation.** Trigger: client asks for PKV premium calculation. Message: "PKV premiums are individual and risk-based. This Guide does not compute PKV premiums. Advise client to obtain PKV quotes."
- **R-DE-SC-3: Cross-border social security (A1).** Trigger: client works across EU borders. Message: "EU social security coordination (Regulation (EC) No 883/2004) and A1 certificates require specialist advice. Escalate to Steuerberater."
- **R-DE-SC-4: Versorgungswerk pension schemes.** Trigger: client is in a professional pension fund (Versorgungswerk). Message: "Versorgungswerk schemes have their own rate schedules. Out of scope. Escalate to Steuerberater."
- **R-DE-SC-5: Scheinselbstaendigkeit determination.** Trigger: possible false self-employment. Message: "Statusfeststellungsverfahren and Scheinselbstaendigkeit determinations involve severe financial exposure. Escalate immediately."

## Section 3: Payment pattern library

This is the deterministic pre-classifier for bank statement transactions related to German social contributions. EXCLUDE means: keep the debit out of the business profit and loss account. The owner's own contributions are dealt with in the income tax return as special expenses under § 10 EStG (Rule 9). The one open point is the owner's own accident insurance contribution (Rule 9).

### 3.1 Krankenkasse (GKV health insurance) debits

**Krankenkasse (GKV) debit patterns**

| Pattern | Treatment | Notes |
| --- | --- | --- |
| TK, TECHNIKER KRANKENKASSE | EXCLUDE: GKV contribution | Health + care combined debit |
| AOK, AOK PLUS, AOK BAYERN, AOK NORDWEST | EXCLUDE: GKV contribution | Regional AOK variants |
| BARMER, BARMER GEK | EXCLUDE: GKV contribution |  |
| DAK, DAK-GESUNDHEIT | EXCLUDE: GKV contribution |  |
| IKK, IKK CLASSIC, IKK SUEDWEST | EXCLUDE: GKV contribution |  |
| HEK, HANSEATISCHE KRANKENKASSE | EXCLUDE: GKV contribution |  |
| KKH, KAUFMAENNISCHE KRANKENKASSE | EXCLUDE: GKV contribution |  |
| KNAPPSCHAFT | EXCLUDE: GKV contribution |  |
| BKK (various: BKK MOBIL OIL, BKK FIRMUS, VIACTIV) | EXCLUDE: GKV contribution | Betriebskrankenkassen |
| KRANKENKASSE, KRANKENVERSICHERUNG | EXCLUDE: GKV contribution | Generic pattern |
| GKV, GESETZLICHE KV | EXCLUDE: GKV contribution | Generic abbreviation |

If the business has staff, a debit from a Krankenkasse can also be the employer's total social insurance contribution for employees, because that contribution is paid to the health funds as collecting agencies (§ 28h(1) SGB IV): https://www.gesetze-im-internet.de/sgb_4/__28h.html That payment belongs to payroll, not to this Guide. Ask before classifying.

### 3.2 Private Krankenversicherung (PKV) debits

**Private Krankenversicherung (PKV) debit patterns**

| Pattern | Treatment | Notes |
| --- | --- | --- |
| ALLIANZ PKV, ALLIANZ PRIVATE | EXCLUDE: PKV premium | Private health insurance |
| DEBEKA, DEBEKA KRANKENVERSICHERUNG | EXCLUDE: PKV premium |  |
| DKV, DEUTSCHE KRANKENVERSICHERUNG | EXCLUDE: PKV premium |  |
| SIGNAL IDUNA PKV | EXCLUDE: PKV premium |  |
| HALLESCHE | EXCLUDE: PKV premium |  |
| BARMENIA | EXCLUDE: PKV premium | Could be supplementary |
| PRIVATE KRANKENVERSICHERUNG, PKV | EXCLUDE: PKV premium | Generic |

### 3.3 KSK (Kuenstlersozialkasse) debits

**KSK debit patterns**

| Pattern | Treatment | Notes |
| --- | --- | --- |
| KSK, KUENSTLERSOZIALKASSE | EXCLUDE: KSK contribution | Member's share of health, care and pension in one debit |
| KUENSTLERSOZIALVERSICHERUNG | EXCLUDE: KSK contribution |  |

A KSK debit in the books of a business that commissions artists can instead be the artists' social levy or its monthly prepayment (Rule 6). That is a cost of the business, not the owner's own insurance. Ask which one it is.

### 3.4 Deutsche Rentenversicherung (pension)

**Deutsche Rentenversicherung debit patterns**

| Pattern | Treatment | Notes |
| --- | --- | --- |
| DRV, DEUTSCHE RENTENVERSICHERUNG | EXCLUDE: pension contribution | Voluntary or mandatory pension |
| RENTENVERSICHERUNG, RV BEITRAG | EXCLUDE: pension contribution |  |

### 3.5 Berufsgenossenschaft (accident insurance)

**Berufsgenossenschaft debit patterns**

| Pattern | Treatment | Notes |
| --- | --- | --- |
| BG, BERUFSGENOSSENSCHAFT | ASK: owner's own cover or staff. Staff part is payroll. Owner's own part is a reviewer point (Rule 9): do not book it either way without the reviewer | BG contribution notice, set after the end of the year |
| BG BAU, BG ETEM, BGW, BGHM, BG VERKEHR | ASK: owner's own cover or staff. Staff part is payroll. Owner's own part is a reviewer point (Rule 9): do not book it either way without the reviewer | Named BGs by sector |
| VBG, VERWALTUNGS-BG | ASK: owner's own cover or staff. Staff part is payroll. Owner's own part is a reviewer point (Rule 9): do not book it either way without the reviewer | Office-based industries |
| UNFALLVERSICHERUNG | ASK: owner's own cover or staff. Staff part is payroll. Owner's own part is a reviewer point (Rule 9): do not book it either way without the reviewer | Generic |

A BG invoice can be for the owner's own cover, for the employees, or both: the entrepreneur owes the contributions for the insured who work in the business, and an owner who is insured owes the own contribution too (§ 150(1) SGB VII): https://www.gesetze-im-internet.de/sgb_7/__150.html The part for employees belongs to payroll. Read the notice before classifying.

### 3.6 Arbeitslosenversicherung (unemployment: voluntary)

**Arbeitslosenversicherung debit patterns**

| Pattern | Treatment | Notes |
| --- | --- | --- |
| AGENTUR FUER ARBEIT, BUNDESAGENTUR | EXCLUDE: voluntary unemployment | If self-employed opted in (Rule 12) |
| ARBEITSLOSENVERSICHERUNG | EXCLUDE: voluntary unemployment | Rare for self-employed |

### 3.7 Tax authority (NOT social contributions)

**Tax authority patterns**

| Pattern | Treatment | Notes |
| --- | --- | --- |
| FINANZAMT, FA (+ city name) | EXCLUDE: income tax | Not a social contribution |
| UMSATZSTEUER, UST | EXCLUDE: VAT | Not a social contribution |
| EINKOMMENSTEUER, EST | EXCLUDE: income tax | Not a social contribution |
| GEWERBESTEUER | EXCLUDE: trade tax | Not a social contribution |

## Section 4: Worked examples

Six bank statement classifications for a hypothetical self-employed German IT consultant (Freiberufler, voluntary GKV member, no children, age 35). The amounts are left open on purpose. This Guide never re-derives an amount: the amount is what the fund's or insurer's notice says, and the classifier checks the debit against that notice.

### Example 1: Monthly Krankenkasse debit (Techniker)

**Input line:**
`15.04.2026 ; TECHNIKER KRANKENKASSE ; LASTSCHRIFT ; KV BEITRAG MAERZ ; -[amount] ; EUR`

**Reasoning:**
Matches "TECHNIKER KRANKENKASSE" (pattern 3.1). A voluntary member's contribution for a month is due by the 15th of the following month (Rule 10), so a debit in mid April is normally the March contribution. The amount comes from the fund's contribution notice: the contribution base times the reduced or general rate plus that fund's own additional rate (Rule 1). Do not rebuild it with the ministry's average additional rate. Check whether the care contribution is in the same debit or billed apart.

**Classification:** EXCLUDE: GKV health insurance contribution. Deductible as basic health insurance in the income tax return (Rule 9).

### Example 2: Pflegeversicherung (combined with GKV or separate)

**Input line:**
`15.04.2026 ; TECHNIKER KRANKENKASSE ; LASTSCHRIFT ; PV BEITRAG MAERZ ; -[amount] ; EUR`

**Reasoning:**
Matches TK pattern. This is the long-term care contribution. The client is childless and over 23, so the childless rate in the care table of Section 1 applies to the same contribution base as for health. Some Krankenkassen combine KV + PV in one debit; others split them. Either way, EXCLUDE.

**Classification:** EXCLUDE: Pflegeversicherung. Deductible in the income tax return (Rule 9).

### Example 3: KSK debit (artist member)

**Input line:**
`07.04.2026 ; KUENSTLERSOZIALKASSE ; LASTSCHRIFT ; BEITRAG MAERZ ; -[amount] ; EUR`

**Reasoning:**
Matches "KUENSTLERSOZIALKASSE" (pattern 3.3). The KSK collects the member's share of pension, health and care insurance in one debit. The member pays half of each; a childless member also pays the whole childless surcharge (Rule 5). The share for a month falls due on the 5th of the following month. The amount depends on the income the member estimated for the year and on the fund's additional rate.

**Classification:** EXCLUDE: KSK contribution. Tax treatment: health and care part as basic health and care insurance; pension part as Altersvorsorgeaufwendungen (Rule 9).

### Example 4: Berufsgenossenschaft annual invoice

**Input line:**
`15.05.2026 ; VBG VERWALTUNGS-BG ; UEBERWEISUNG ; BEITRAG 2025 ; -[amount] ; EUR`

**Reasoning:**
Matches "VBG" (pattern 3.5). Accident insurance contributions are set after the end of the calendar year, so the invoice paid in one year is for the year before (Rule 11). The amount is set by the accident insurer in its contribution notice. No official page read for this Guide prints a general rate, so this Guide gives none.

**Classification:** ASK: accident insurance. If it is the owner's own cover, the tax treatment of the owner's own contribution is a reviewer point (Rule 9). If it is for staff, it belongs to payroll.

### Example 5: Voluntary pension payment (Deutsche Rentenversicherung)

**Input line:**
`27.02.2026 ; DEUTSCHE RENTENVERSICHERUNG BUND ; UEBERWEISUNG ; FREIWILLIGER BEITRAG FEB ; -[amount] ; EUR`

**Reasoning:**
Matches "DEUTSCHE RENTENVERSICHERUNG" (pattern 3.4). A voluntary pension contribution. The payer may choose any monthly amount from the minimum to the maximum in the pension table of Section 1. Voluntary contributions for a year count only if paid by 31 March of the following year (Rule 10).

**Classification:** EXCLUDE: voluntary pension contribution. Deductible as Altersvorsorgeaufwendungen up to the yearly cap in Rule 9.

### Example 6: Finanzamt (income tax, NOT social contribution)

**Input line:**
`10.03.2026 ; FINANZAMT MUENCHEN ; LASTSCHRIFT ; EST VORAUSZAHLUNG Q1 ; -[amount] ; EUR`

**Reasoning:**
Matches "FINANZAMT" (pattern 3.7). This is an income tax prepayment, NOT a social contribution. Do not classify as social insurance.

**Classification:** EXCLUDE: income tax. NOT a social contribution.

## Section 5: Tier 1 rules

### Rule 1: GKV contribution formula

- **Monthly GKV formula.** Monthly health contribution = contribution base x (reduced or general rate + the fund's own additional rate). The contribution base is the member's monthly income, not less than the minimum base and not more than the ceiling in Section 1.
- **What counts as income.** For a voluntary member the fund looks at the member's whole economic capacity, not only the business profit. The health ministry names income from capital and from letting as examples. See § 240 SGB V at https://www.gesetze-im-internet.de/sgb_5/__240.html and the funds' uniform rules at https://www.gkv-spitzenverband.de/media/dokumente/krankenversicherung_1/grundprinzipien_1/finanzierung/beitragsbemessung/2025-01-01_Einheitliche_Grundsaetze_zur_Beitragsbemessung_freiwilliger_Mitglieder_Stand_01_01_2025.pdf
- **Self-employed GKV rate share.** A voluntary member bears the contribution alone. There is no employer share. See § 250(2) SGB V at https://www.gesetze-im-internet.de/sgb_5/__250.html
- **The minimum base in the law.** § 240(4) SGB V sets the minimum as one ninetieth of the monthly reference amount per calendar day. The ministry prints the resulting monthly base; use the printed value in Section 1.
- **Never add rates into one total.** No official page prints a combined health rate for a given fund. State the statutory rate and the fund's additional rate as two parts.

### Rule 2: GKV rates (2026)

**GKV rates 2026**

| Component | Rate |
| --- | --- |
| Without sick pay (default for self-employed) | Reduced rate in Section 1 + the fund's own additional rate |
| With sick pay (only after the member elected it) | General rate in Section 1 + the fund's own additional rate |
| Average additional rate (2026) | See the ministry table in Section 1. It is an average, not any fund's rate |

- **Sick pay is an election.** A main-occupation self-employed member has no sick pay claim unless the member declares to the fund that the membership shall include it (Wahlerklärung). See § 44(2) SGB V at https://www.gesetze-im-internet.de/sgb_5/__44.html
- **The fund's own additional rate.** The funds' association publishes the list of funds with their additional rates: https://www.gkv-spitzenverband.de/service/krankenkassenliste/krankenkassen.jsp

### Rule 3: Pflegeversicherung rates (2026)

**Pflegeversicherung rates by children**

| Member | Rate |
| --- | --- |
| Childless, from the month after turning 23 | Childless rate in the care table of Section 1 |
| Parent, one child (any age, for life) | Base rate in the care table of Section 1 |
| Parent, two to five or more children under 25 | The rate printed for that number of children in the care table of Section 1 |

- **PV assessment base and employer share.** Same contribution base as for GKV, from the minimum base to the ceiling. A voluntary GKV member is compulsorily insured in the social care insurance (§ 20(3) SGB XI), the base follows § 240 SGB V (§ 57(4) SGB XI), and the member pays the full rate alone (§ 59(4) SGB XI). See https://www.gesetze-im-internet.de/sgb_11/__57.html
- **Minimum and maximum.** The ministry prints the lowest monthly care contribution of a voluntary member, and a general highest care contribution that it does not label for voluntary members. Both are in the care table of Section 1 and both are before any childless surcharge or parent reduction. The fund's notice decides; for a member who pays alone it can differ from the printed highest amount by a cent.

### Rule 4: Pension (Rentenversicherung)

- **Pension rules.** Rate, ceiling, minimum and maximum contribution, standard and half standard contribution are in the pension tables of Section 1.
- **Who is compulsorily insured.** § 2 SGB VI lists the self-employed who must be insured: teachers and educators with no employee subject to insurance; carers in sick, maternity, infant or child care with no such employee; midwives; sea pilots; artists and publicists under the KSVG; home-based traders (Hausgewerbetreibende); coastal skippers and coastal fishers who belong to the crew of their vessel or fish without a vessel and regularly employ no more than four employees subject to insurance; craftspeople entered in the Handwerksrolle; and persons who have no employee subject to insurance and work permanently and essentially for one client only. See https://www.gesetze-im-internet.de/sgb_6/__2.html For these tests apprentices count as employees and marginally employed persons (Minijobbers) do not (§ 2 sentence 2 SGB VI).
- **Marginal self-employed work is free of pension insurance.** A person who does only marginal self-employed work (geringfügige selbständige Tätigkeit) is insurance-free in that work. The statute does not limit this to teachers; the pension insurer's page merely prints the amount in its paragraph on teachers (table below). The limit in force on 1 January holds for the whole calendar year. Artists and publicists have their own income limit in Rule 5. See § 5(2) SGB VI at https://www.gesetze-im-internet.de/sgb_6/__5.html
- **Everyone else.** Most other Freiberufler and Gewerbetreibende are not compulsorily insured. They may insure voluntarily (§ 7 SGB VI) or apply for compulsory insurance within five years of starting the self-employed work (§ 4(2) SGB VI). Compulsory insurance on application ends only at the end of the day on which its conditions no longer apply (§ 4(4) SGB VI). See https://www.gesetze-im-internet.de/sgb_6/__4.html
- **Registration.** Teachers, carers, midwives and one-client self-employed must register with the pension insurer within three months of starting. See § 190a SGB VI at https://www.gesetze-im-internet.de/sgb_6/__190a.html
- **Contribution base.** Income equal to the reference amount (this gives the standard contribution), or the real income if a lower or higher income is proven with the latest income tax assessment notice, but not less than the minimum base. Until the end of the third calendar year after the year of starting, the base is half the reference amount, or the full reference amount if the insured applies for it (§ 165(1) sentence 2 SGB VI). The pension insurer's form describes the half standard contribution as a choice. A new tax assessment notice must reach the pension insurer at the latest two calendar months after it was issued. See § 165 SGB VI at https://www.gesetze-im-internet.de/sgb_6/__165.html
- **Who bears it.** The self-employed bear their pension contribution alone. Home-based traders share it half and half with their employers (§ 169 no. 3 SGB VI). For artists and publicists the KSK bears it and collects half from the artist. See § 169 SGB VI at https://www.gesetze-im-internet.de/sgb_6/__169.html
- **Exemptions on application.** Craftspeople after at least 18 years of compulsory contributions. One-client self-employed for three years after first starting such work. An exemption works from the day its conditions are met only if it is applied for within three months; otherwise from the day the application arrives (§ 6(4) SGB VI). See § 6 SGB VI at https://www.gesetze-im-internet.de/sgb_6/__6.html

**Self-employed teachers and educators: when the duty starts**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/DRV/DE/Rente/Arbeitnehmer-und-Selbststaendige/03_Selbststaendige/selbststaendige_node.html |
| A self-employed teacher or educator, in a main or side occupation, is compulsorily insured when earning more than this per month and regularly employing no one subject to insurance. The page ties the amount to the Minijob limit. It is a different rule from the minimum contribution base of the same amount | EUR 603 | "mehr als 603 Euro monatlich verdienen und regelmäßig keinen versicherungspflichtigen Arbeitnehmer beschäftigen" |

### Rule 5: KSK members pay half

- **KSK member share rule.** The law says half, not approximately half. An artist or publicist insured under the KSVG pays to the KSK: half of the pension contribution (§ 15 KSVG); half of the health contribution at the general rate plus half of the fund's additional contribution, or at the reduced rate if the member has no sick pay claim (§ 16 KSVG); and half of the care contribution (§ 16a KSVG). The care share rises or falls by the amounts from § 55(3) SGB XI, so a childless member pays the whole childless surcharge on top of the half. See https://www.gesetze-im-internet.de/ksvg/__16a.html
- **Correction of older material.** Older versions of this Guide said that KSK members pay the full care contribution. § 16a KSVG says half.
- **Base.** The member reports the expected income from artistic or publicist work for the next calendar year to the KSK by 1 December, up to the pension ceiling (§ 12 KSVG). For the pension the base is at least the amount in the table below (§ 165(1) no. 3 SGB VI). For health and care the base per calendar day is one three hundred and sixtieth of that expected yearly income, and at least one hundred and eightieth of the monthly reference amount (§ 234(1) SGB V, applied by § 16 KSVG and, for care, by § 57(1) SGB XI). The minimum base of voluntary members in Section 1 is not the KSK member's minimum. See https://www.gesetze-im-internet.de/sgb_5/__234.html See https://www.gesetze-im-internet.de/ksvg/__12.html
- **Halves are not printed as digits.** The KSVG states the shares in words ("die Hälfte"). This Guide does not turn them into half rates.

**KSK: income limit for insurance**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ksvg/__3.html |
| A person whose expected yearly income from self-employed artistic and publicist work does NOT exceed this amount is not insured under the KSVG. Not applied until three years after first taking up the work. Cover stays as long as income is at or under the amount not more than twice within six calendar years. Lowered pro rata when the work covers only part of the year | EUR 3,900 | § 3(1) KSVG: "voraussichtlich ein Arbeitseinkommen erzielt, das 3 900 Euro nicht übersteigt" |

### Rule 6: Kuenstlersozialabgabe (client/Verwerter)

- **Kuenstlersozialabgabe rule.** A business that pays self-employed artists or publicists owes the artists' social levy on those fees. It is a cost of the business and is never deducted from the artist. § 24(1) KSVG lists the typical users (for example publishers, theatres, broadcasters, galleries, and advertising or public relations for third parties). § 24(2) adds businesses that advertise for themselves, or use such works for their business to earn income, and commission self-employed artists or publicists for it. For the second of these two cases (using works for the business) § 24(2) leaves out fees paid at events when no more than three such events are held in a calendar year, and music clubs so far as choir leaders or conductors work for them regularly.
- **Base.** Everything the business spends to get or use the work, less VAT shown separately, paid in the calendar year to self-employed artists or publicists, even when they are not insured under the KSVG themselves. Payments to collecting societies and tax-free expense allowances are left out. See § 25 KSVG at https://www.gesetze-im-internet.de/ksvg/__25.html
- **Reporting and payment.** Report the year's fees to the KSK on its form by 31 March of the following year. Monthly prepayments are due within ten days after the end of each calendar month. A prepayment is the current year's rate applied to one twelfth of the previous year's fees (§ 27 KSVG).
- **Which year's rate.** The rate in the table is for fees paid in 2026. The report due by 31 March 2026 covers fees paid in 2025, at the 2025 rate, which this Guide does not carry. The same care is needed with the small-amount limit: the consolidated law page prints only the current text, so check which version applied to the year being reported.

**Levy rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ksabg2026v/BJNR0DC0A0025.html |
| Artists' social levy for 2026, on the fees paid | 4.9% | "Der Prozentsatz der Künstlersozialabgabe im Jahr 2026 beträgt 4,9 Prozent" |

**Small-amount limit (Bagatellgrenze)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ksvg/__24.html |
| Businesses within § 24(2) KSVG only: the levy is owed only if the total fees for orders placed in a calendar year EXCEED this amount. The law makes the duty depend on the total exceeding the amount; it does not say that only the excess is charged. The limit does not apply to the typical users in § 24(1) | EUR 1,000 | § 24(2) KSVG: "mehrere in einem Kalenderjahr erteilte Aufträge 1 000 Euro übersteigt" |

**Prepayments**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ksvg/__27.html |
| No monthly prepayment is due when the prepayment would not exceed this amount | EUR 40 | § 27(3) KSVG: "wenn der vorauszuzahlende Betrag 40 Euro nicht übersteigt" |

### Rule 7: GKV provisional and final assessment

- **GKV provisional/final assessment rule.** Contributions on self-employed income are first set provisionally from the latest income tax assessment notice; at the start of self-employment from the proven expected income. They are set finally from the real income of the calendar year once that year's tax assessment notice is presented. Overpayments are refunded and underpayments demanded. If the member does not prove the real income within three years after the end of the calendar year, when the fund asks for it, the fund sets the contribution finally on the ceiling. Within twelve months of that notice the member can still ask for a new assessment by presenting the tax assessment notice. See § 240(4a) SGB V at https://www.gesetze-im-internet.de/sgb_5/__240.html

### Rule 8: Every person must have health insurance

- **Mandatory health insurance rule.** There is no opt-out. Every resident must hold health cover: a private policy, unless the person is insured or must be insured in the statutory system or has one of the other claims listed there. See § 193(3) of the insurance contract act (VVG) at https://www.gesetze-im-internet.de/vvg_2008/__193.html
- **No free choice in both directions.** A main-occupation self-employed person is not compulsorily insured as an employee (§ 5(5) SGB V). When compulsory or family insurance ends, the cover goes on as voluntary membership unless the member leaves within two weeks of the fund's notice and proves other cover (§ 188(4) SGB V): https://www.gesetze-im-internet.de/sgb_5/__188.html A person who is outside the statutory system can join it voluntarily only in the cases of § 9 SGB V, for example after leaving compulsory insurance with at least 24 months of cover in the last five years or 12 months without a break just before, and only by telling the fund within three months: https://www.gesetze-im-internet.de/sgb_5/__9.html
- **The JAEG threshold.** The compulsory-insurance threshold in Section 1 applies only to employees.
- **Correction of older material.** Older versions of this Guide said the self-employed can freely choose GKV or PKV. The way into a private policy is open; the way back into a statutory fund is limited by § 9 and § 6(3a) SGB V.

### Rule 9: Tax deductibility (Vorsorgeaufwendungen)

**Tax deductibility table**

| Contribution | Deductibility |
| --- | --- |
| Basiskrankenversicherung (GKV or PKV base) | Deductible without a cap. GKV contributions that carry a sick pay claim are first cut by the share in the table below |
| Pflegeversicherung (statutory care insurance) | Deductible without a cap |
| Rentenversicherung (statutory or Rürup) | Deductible in full since 2023, up to the yearly cap in the pension insurer's table below |
| Other insurance (unemployment, accident, liability, supplementary health) | Only within the yearly cap in the table below, and only if basic health and care contributions have not already used it up |

**Other insurance contributions: cap and sick pay cut**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__10.html |
| Yearly cap for health, care and other insurance contributions together, for a person who pays for health cover alone | EUR 2,800 | § 10(4) EStG: "können je Kalenderjahr insgesamt bis 2 800 Euro abgezogen werden" |
| The lower yearly cap, for a person who gets health costs reimbursed or paid without own expense, or for whose health insurance tax-free payments within § 3 no. 9, 14, 57 or 62 EStG are made. No. 57 is the amounts the KSK pays, so this cap is the one for KSK members | EUR 1,900 | § 10(4) EStG: "Der Höchstbetrag beträgt 1 900 Euro" |
| Cut applied to a statutory health contribution when it can give a sick pay claim | 4% | § 10(1) no. 3 EStG: "ist der jeweilige Beitrag um 4 Prozent zu vermindern" |

- **How the cap works.** It is a yearly cap per person, summed for jointly assessed spouses. If basic health and care contributions are higher than the cap, they are deducted in full and nothing else under § 10(1) no. 3a EStG is deductible.
- **Tax-free KSK payments.** § 3 no. 57 EStG: https://www.gesetze-im-internet.de/estg/__3.html

**Pension contributions: yearly cap for 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/DRV/DE/Ueber-uns-und-Presse/Presse/Meldungen/2026/260420-vorsorgen-und-steuern-sparen |
| Yearly cap for deductible pension contributions (statutory pension, professional pension funds, certain private annuity policies), single person | EUR 30,826 | Pension insurer's notice of 20 April 2026: "2026 beträgt der Höchstbetrag 30.826 Euro für Ledige und 61.652 Euro für Verheiratete" |
| The same cap for a married couple | EUR 61,652 | Same sentence |

- **Where the pension cap comes from.** § 10(3) EStG sets it as the highest contribution to the miners' pension scheme, rounded up to a full euro, doubled for jointly assessed spouses. The statute prints no amount; the amount above is the pension insurer's.
- **Owner's own accident insurance.** § 10(1) no. 3a EStG lists accident insurance among the other insurance contributions. The pages read for this Guide do not settle whether an owner's own contribution to the Berufsgenossenschaft is a business expense instead. Flag for reviewer.

### Rule 10: Payment schedule

**Payment schedule table**

| Branch | Due | Method |
| --- | --- | --- |
| GKV + PV (voluntary member) | By the 15th of the month AFTER the contribution month | Lastschrift or bank transfer to the fund |
| Pension (compulsory, self-employed) | At the latest on the third-last bank working day of the month in which the self-employed work is done, so inside the contribution month itself (§ 23(1) sentence 2 SGB IV). The pension insurer's brochure of April 2026 gives the same day without naming the month | Direct debit by the pension insurer or bank transfer |
| Pension (voluntary) | Any time, but contributions for a year count only if paid by 31 March of the following year | Bank transfer or direct debit |
| KSK (member's shares) | The share for a month falls due on the 5th of the following month | KSK direct debit |
| BG (accident) | Set after the end of the calendar year. Due on the 15th of the month after the month in which the contribution notice was made known | BG invoice |
| Unemployment insurance on application | The running contribution is due on the 1st of the month | Transfer or direct debit to the Bundesagentur |
| Artists' social levy | Yearly report by 31 March. Prepayments within ten days after the end of each calendar month | To the KSK |

- **Sources.** Health and care: § 10 of the funds' uniform rules, "Sie sind bis zum 15. des dem Beitragsmonat folgenden Monats (Fälligkeitstag) zu zahlen": https://www.gkv-spitzenverband.de/media/dokumente/krankenversicherung_1/grundprinzipien_1/finanzierung/beitragsbemessung/2025-01-01_Einheitliche_Grundsaetze_zur_Beitragsbemessung_freiwilliger_Mitglieder_Stand_01_01_2025.pdf
- Pension, compulsory: § 23(1) sentence 2 SGB IV: https://www.gesetze-im-internet.de/sgb_4/__23.html and the brochure "Selbstständig, wie die Rentenversicherung Sie schützt", 21st edition of April 2026: https://www.deutsche-rentenversicherung.de/SharedDocs/Downloads/DE/Broschueren/national/selbstaendig_wie_rv_schuetzt_aktuell.pdf?__blob=publicationFile&v=8
- Pension, voluntary: § 197(2) SGB VI: https://www.gesetze-im-internet.de/sgb_6/__197.html
- KSK: § 15, § 16 and § 16a KSVG: https://www.gesetze-im-internet.de/ksvg/__15.html and https://www.gesetze-im-internet.de/ksvg/__16.html
- Accident insurance: § 152 SGB VII and § 23(3) SGB IV: https://www.gesetze-im-internet.de/sgb_7/__152.html and https://www.gesetze-im-internet.de/sgb_4/__23.html
- Unemployment insurance on application: the employment agency's leaflet of January 2026: https://www.arbeitsagentur.de/datei/hinweis-alv_ba035280.pdf
- **Correction of older material.** Older versions of this Guide said GKV is due on the 15th for the current month and the KSK debit is mid-month. The official texts say the 15th of the following month and the 5th of the following month.

### Rule 11: Accident insurance (Berufsgenossenschaft)

- **Notify the business.** Every entrepreneur must tell the competent accident insurer about the business within one week of its start. A trade registration made within that week counts as the notice. See § 192 SGB VII at https://www.gesetze-im-internet.de/sgb_7/__192.html
- **The owner's own cover.** Most self-employed persons are not insured by law. They can insure themselves voluntarily by written or electronic application; cover starts on the day after the application arrives and lapses if the contribution is not paid within two months of its due date. See § 6 SGB VII at https://www.gesetze-im-internet.de/sgb_7/__6.html
- **Insured by law or by the insurer's statute.** A few groups are insured by law without application, for example self-employed persons in the health service or in welfare work such as midwives, physiotherapists and speech therapists, home-based traders and farmers. Some accident insurers insure certain entrepreneurs by their statute (§ 3 SGB VII). Ask the accident insurer for the client's trade. See https://www.dguv.de/de/versicherung/versicherte_personen/vers-unternehmer/index.jsp
- **No rate in this Guide.** No official page read for this Guide prints a contribution rate or a typical amount. Each accident insurer sets its own.

### Rule 12: Unemployment insurance on application

- **Who can apply.** A person who takes up self-employed work of at least 15 hours a week, and who either was in compulsory unemployment insurance for at least twelve months within the last 30 months before starting, or had a claim to a wage replacement benefit under SGB III (for example unemployment benefit) right before starting. The application must be made within three months of starting. Not open to a person who was already insured on application as self-employed, interrupted that work twice and claimed unemployment benefit in the breaks (§ 28a(2) sentence 2). See § 28a SGB III at https://www.gesetze-im-internet.de/sgb_3/__28a.html
- **Base.** A fixed base, not the real income: the monthly reference amount, and half of it until the end of the calendar year after the year of starting. See § 345b SGB III at https://www.gesetze-im-internet.de/sgb_3/__345b.html
- **Leaving.** The insured can give notice for the first time after five years, with three months' notice to the end of a calendar month. Cover also ends when contributions are more than three months late.

**Unemployment insurance rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_3/__341.html |
| Contribution rate of unemployment insurance. The self-employed person insured on application bears it alone. Not the care rate for five or more children, which happens to be the same number | 2.6% | § 341(2) SGB III: "Der Beitragssatz beträgt 2,6 Prozent" |

**Unemployment insurance on application: monthly contributions 2026 (employment agency leaflet, January 2026)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.arbeitsagentur.de/datei/hinweis-alv_ba035280.pdf |
| Self-employed person after the start phase, per month | EUR 102.83 | "Selbständig Tätige nach der 2-jährigen Startphase 102,83 Euro" |
| Self-employed person in the start phase (the year of starting and the following calendar year), per month | EUR 51.42 | "Selbständig Tätige in der 2-jährigen Startphase (halber Beitrag) 51,42 Euro" |

## Section 6: Tier 2 catalogue

### T2-1: Hauptberuflich vs Nebenberuflich (side business alongside employment)

- **T2-1.** Trigger: Client is employed with a side freelance business. Issue: A compulsorily insured employee pays health contributions on pay; the health ministry's page lists self-employed income as contributory for compulsory members only when it is earned alongside a statutory pension or pension-like payments. If self-employment becomes the main occupation, the person is no longer compulsorily insured as an employee (§ 5(5) SGB V) and pays as a voluntary member on all income. A person who regularly employs at least one employee above the Minijob level in the business is presumed to be self-employed as main occupation. Action: Flag for reviewer. Case-specific assessment by the fund. See https://www.gesetze-im-internet.de/sgb_5/__5.html

### T2-2: PKV to GKV switching

- **T2-2.** Trigger: PKV client wants to switch to GKV. Issue: Very restricted. A self-employed person cannot join a statutory fund by choice outside the cases of § 9 SGB V. A person who becomes subject to compulsory insurance after turning 55 stays outside it if there was no statutory cover in the last five years and the person was insurance-free, exempt or main-occupation self-employed for at least half of that time (§ 6(3a) SGB V). Action: Escalate to Steuerberater. Do not advise that switching is possible. See https://www.gesetze-im-internet.de/sgb_5/__6.html

### T2-3: KSK eligibility determination

- **T2-3.** Trigger: Client's profession may or may not qualify for KSK. Issue: Insurance under the KSVG needs self-employed artistic or publicist work done for a living and not just for a short time, no more than one employee (apprentices and Minijobbers do not count), and expected yearly income above the limit in Rule 5 once the three starter years are over. The KSK decides. Action: Flag for reviewer. Do not assume eligibility. See https://www.gesetze-im-internet.de/ksvg/__1.html

### T2-4: Scheinselbstaendigkeit (false self-employment)

- **T2-4.** Trigger: Client works almost only for one client and has no employees. Issue: Two different risks. First, compulsory pension insurance as a one-client self-employed person under § 2 sentence 1 no. 9 SGB VI ("auf Dauer und im Wesentlichen nur für einen Auftraggeber"). Second, reclassification as an employee, with contributions in all branches; the status can be settled in the procedure of § 7a SGB IV. Older versions of this Guide gave a five-sixths income test; the official pages read for this Guide do not print it. Action: Escalate immediately. Severe financial exposure. See https://www.gesetze-im-internet.de/sgb_4/__7a.html

### T2-5: Handwerker pension after 18 years

- **T2-5.** Trigger: Craftsperson in the Handwerksrolle with 216 or more months of compulsory pension contributions. Issue: May apply for exemption (Befreiungsantrag) under § 6(1) no. 4 SGB VI. All compulsory contributions count, for example from employment or child-raising periods, says the pension insurer's brochure. Action: Flag for reviewer to confirm eligibility.

### T2-6: GKV retroactive adjustment

- **T2-6.** Trigger: Einkommensteuerbescheid shows significant income deviation from provisional estimate. Issue: Krankenkasse recalculates the year finally (Rule 7). Underpayments are demanded. Action: Advise client to submit the Bescheid promptly and reserve funds.

## Section 7: Excel working paper template

~~~
GERMANY SOCIAL CONTRIBUTIONS: WORKING PAPER
Client: [name]
Tax Year: [year]
Prepared: [date]

INPUT DATA
  Insurance type:                [GKV / PKV]
  Krankenkasse name:             [____]
  Fund's own additional rate:    [____]%
  Sick pay elected:              [YES/NO]
  Monthly income (all sources):  EUR [____]
  Parent (any child, any age):   [YES/NO]
  Number of children (under 25): [____]
  Age:                           [____]
  Profession:                    [____]
  Start of self-employment:      [date]
  KSK member:                    [YES/NO]
  Pension: voluntary/mandatory:  [____]

GKV COMPUTATION
  Assessment base (clamped):     EUR [____]
  KV rate:                       [____]%
  Monthly KV:                    EUR [____]
  PV rate:                       [____]%
  Monthly PV:                    EUR [____]
  Total KV + PV monthly:         EUR [____]
  Total KV + PV annual:          EUR [____]
  Checked against fund notice:   [YES/NO]

PENSION COMPUTATION
  Type: [Voluntary / Mandatory / On application / KSK]
  Monthly contribution:          EUR [____]
  Annual contribution:           EUR [____]

OTHER
  BG contribution:               EUR [____]
  Arbeitslosenversicherung:      EUR [____]

TOTAL ANNUAL CONTRIBUTIONS:      EUR [____]

TAX DEDUCTIBILITY (ANLAGE VORSORGEAUFWAND)
  Basiskrankenversicherung:      EUR [____] (no cap; sick pay cut if elected)
  Pflegeversicherung:            EUR [____] (no cap)
  Rentenversicherung:            EUR [____] (within the yearly cap in Rule 9)
  Other (unemployment, accident, supplementary): EUR [____] (within the cap in Rule 9)

REVIEWER FLAGS
  [List any Tier 2 flags]
~~~

## Section 8: Bank statement reading guide

### How German social contribution debits appear

**GKV Krankenkasse debits:**
- Description: Krankenkasse name + "BEITRAG" or "LASTSCHRIFT" or "KV BEITRAG"
- Timing: by the 15th of the month, for the month before
- Amount: Consistent monthly amount (changes when income is reassessed or the fund changes its additional rate)
- Some Kassen combine KV + PV in one debit; others show two debits

**KSK debits:**
- Description: "KUENSTLERSOZIALKASSE" or "KSK"
- Timing: around the 5th of the month, for the month before
- Amount: Varies by declared income and chosen Krankenkasse

**Deutsche Rentenversicherung:**
- Description: "DEUTSCHE RENTENVERSICHERUNG" or "DRV BUND"
- Timing: Monthly. Voluntary payers may also pay later, up to 31 March of the following year
- Amount: voluntary payers choose a fixed amount between the minimum and the maximum in the pension table of Section 1

**Berufsgenossenschaft:**
- Description: BG name + "BEITRAG" + year
- Timing: after the end of the calendar year, for the year before. Advance payments (Beitragsvorschüsse) during the year are possible
- Amount: Set by the accident insurer

**Bundesagentur für Arbeit:**
- Description: "BUNDESAGENTUR FUER ARBEIT" or "AGENTUR FUER ARBEIT"
- Timing: 1st of the month, or one yearly contribution
- Amount: the fixed monthly contribution in Rule 12

**Key identification tips:**
1. GKV debits are the most frequent: monthly, by the 15th
2. KSK debits combine health, care and pension (member share only)
3. BG debits reference the prior year
4. Finanzamt debits are TAX, not social contributions. Do not confuse them
5. Provisional GKV amounts may be retroactively adjusted

## Section 9: Onboarding fallback

If the client provides only a bank statement:

1. **Scan for Krankenkasse debits.** Identify the health insurer and monthly amount
2. **Determine GKV or PKV.** Krankenkasse names (TK, AOK, Barmer, etc.) = GKV; Allianz PKV, Debeka, DKV = PKV (private insurer)
3. **Identify KSK if present.** KSK debits indicate artist, writer or journalist status, or a business that pays the artists' levy
4. **Sum annual contributions.** Total GKV + PV + pension + BG, as a sum of the debits found. Never build a total from rates
5. **Flag:** "Social contribution classification derived from bank statement patterns. Actual Zusatzbeitrag, income assessment base, and pension obligation type have not been independently confirmed. Reviewer must confirm before Anlage Vorsorgeaufwand is completed."

## Section 10: Reference material

### Contribution ceilings and minimums (2026)

**Contribution ceilings and minimums table**

Every value here repeats a linked table in Section 1. The source of each value is given there.

| Parameter | KV/PV | Pension |
| --- | --- | --- |
| BBG monthly | EUR 5,812.50 | EUR 8,450 |
| BBG annual | EUR 69,750 | EUR 101,400 |
| Minimum contribution base, monthly | EUR 1,318.33 | EUR 603 |
| JAEG (employees only) | EUR 77,400 | N/A |

### Test suite

No test carries an amount. The expected result of each test is the rule that must be applied and the table that holds the value.

**Test 1:** Voluntary GKV member, no sick pay, income between the minimum base and the ceiling, childless, age 35. Expected: reduced rate plus the fund's own additional rate on the real income; care at the childless rate; both checked against the fund's notice. If the fund is unknown, the ministry's average is used for an estimate only and flagged.

**Test 2:** Voluntary GKV member, income below the minimum base, one child, age 30. Expected: the base is lifted to the minimum base. The ministry's printed minimum health contribution (with the average additional rate) and minimum care contribution are in Section 1. Care at the base rate.

**Test 3:** Voluntary GKV member, sick pay elected, income above the ceiling, two children under 25. Expected: base capped at the ceiling; general rate plus the fund's own additional rate; care at the rate printed for two children. The ministry's printed maximum health contribution with sick pay is in Section 1.

**Test 4:** KSK member, childless, age 28. Expected: the member pays half of the pension contribution, half of the health contribution (general rate plus half of the fund's additional contribution), half of the care contribution at the base rate, and the whole childless surcharge. NOT the full care contribution. The share for a month is due on the 5th of the following month.

**Test 5:** Handwerker in the Handwerksrolle, 5 years in. Expected: compulsory pension insurance. The standard contribution in Section 1 applies unless a lower or higher income is proven with the tax assessment notice; then the pension rate applies to that income, from the minimum base up to the ceiling. No exemption before 18 years of compulsory contributions.

**Test 6:** Employed full-time with a side freelance income. Expected: if the employment is the main occupation and the employee is compulsorily insured, no separate GKV contribution on the freelance income. Flag T2-1.

**Test 7:** Vorsorgeaufwendungen: client paid GKV without sick pay, PV and statutory pension contributions. Expected: GKV and PV deductible without a cap; no sick pay cut because there is no sick pay claim; pension contributions deductible in full up to the yearly cap in Rule 9. No total is stated without the client's real amounts.

**Test 8:** Kuenstlersozialabgabe: an advertising agency paid fees to self-employed designers during the year. Expected: the agency is a typical user under § 24(1) KSVG, so no small-amount limit applies. Levy = the rate in Rule 6 times the net fees. Report by 31 March of the following year.

### Prohibitions

- NEVER compute without knowing GKV or PKV
- NEVER tell a KSK member that the whole care contribution is theirs: § 16a KSVG gives the member half of it, plus the whole childless surcharge if childless
- NEVER assume pension is voluntary without checking profession
- NEVER tell a voluntary GKV member that contributions can be charged on less than the minimum base
- NEVER advise PKV-to-GKV switching is straightforward
- NEVER compute PKV premiums. They are individual and risk-based
- NEVER advise applying for compulsory pension insurance (Pflichtversicherung auf Antrag) without saying that § 4 SGB VI names no right to cancel it: it ends only at the end of the day on which its conditions no longer apply
- NEVER ignore the fund's own additional rate, and NEVER present the ministry's average as a fund's rate
- NEVER present GKV provisional contributions as final
- NEVER conflate the KV/PV ceiling with the pension ceiling. Both are in Section 1
- NEVER add rates into a combined or total rate. No official page prints one for the self-employed
- NEVER advise on Scheinselbstaendigkeit without escalating

## The method, step by step

1. Settle the health insurance status first. A main-occupation self-employed person is not compulsorily insured as an employee (§ 5(5) SGB V). After leaving compulsory or family insurance the cover goes on as voluntary membership unless the member leaves within two weeks of the fund's notice and proves other cover (§ 188(4) SGB V). Everyone must hold cover (§ 193(3) VVG). https://www.gesetze-im-internet.de/sgb_5/__188.html
2. For a voluntary GKV member, give the fund proof of all income: the latest income tax assessment notice, or at the start the expected income. The fund sets the contribution provisionally and finally after the year's tax assessment notice (§ 240(4a) SGB V). Without proof, when the fund has asked for it, it charges on the ceiling. https://www.gesetze-im-internet.de/sgb_5/__240.html
3. Work out the health contribution from the fund's notice: base between the minimum base and the ceiling, reduced rate (§ 243 SGB V) or, if sick pay was elected under § 44(2) SGB V, general rate (§ 241 SGB V), plus the fund's own additional rate. https://www.gesetze-im-internet.de/sgb_5/__243.html
4. Add long-term care insurance on the same base. Prove parenthood and the children under 25 to the care fund, or the childless rate applies (§ 55(3) and (3a) SGB XI). Rates: the ministry's page. https://www.bundesgesundheitsministerium.de/themen/pflege/online-ratgeber-pflege/die-pflegeversicherung/finanzierung
5. Test the pension duty against the list in § 2 SGB VI. If it applies, register with the pension insurer within three months (§ 190a SGB VI) and choose the standard, half standard or income-based contribution from form V0091. https://www.gesetze-im-internet.de/sgb_6/__2.html
6. If there is no pension duty, decide between no statutory pension, voluntary contributions (§ 7 SGB VI, payable until 31 March of the following year under § 197(2) SGB VI) and compulsory insurance on application within five years of starting (§ 4(2) SGB VI). https://www.gesetze-im-internet.de/sgb_6/__7.html
7. Artists and publicists register with the KSK on its forms (§ 11 KSVG) and report the expected income for the next year by 1 December (§ 12 KSVG). https://www.gesetze-im-internet.de/ksvg/__11.html
8. Tell the accident insurer about the business within one week of its start (§ 192 SGB VII) and decide on voluntary cover for the owner (§ 6 SGB VII). https://www.gesetze-im-internet.de/sgb_7/__192.html
9. Within three months of starting, decide on unemployment insurance on application (§ 28a SGB III). A later application is too late, apart from the case in § 28a(3) sentence 3 SGB III. https://www.gesetze-im-internet.de/sgb_3/__28a.html
10. If the business pays self-employed artists or publicists, test the levy duty (§ 24 KSVG), keep records of the fees, and report them to the KSK by 31 March of the following year (§ 27 KSVG). https://www.gesetze-im-internet.de/ksvg/__27.html
11. Pay on time, by the due dates in Rule 10. https://www.gesetze-im-internet.de/sgb_4/__23.html
12. In the income tax return, enter the contributions in Anlage Vorsorgeaufwand and apply § 10 EStG (Rule 9). Classify the debits as private, not as business expenses (Section 3). https://www.gesetze-im-internet.de/estg/__10.html

Doing step 1 late is what breaks everything else: the health status decides who charges what, and the three-month windows in steps 5 and 9 start on the first day of self-employment.

## Ask the client first

- How are you insured for health today: a statutory fund (which one, voluntary or compulsory, sick pay elected or not) or a private insurer?
- Is self-employment your main occupation, or do you also have a job? Do you employ anyone above the Minijob level?
- What exactly is your work: teaching or coaching, care, midwifery, a craft entered in the Handwerksrolle, art or writing, or work mostly for one client? When did it start?
- Are you a parent? How many of your children are under 25? How old are you?
- What does your latest income tax assessment notice show, and what income do you expect this year from all sources (business, capital, letting)?
- Does your business pay fees to self-employed artists, designers, photographers, writers or other publicists?

## When to refuse or refer

- Private health insurance premiums (R-DE-SC-2) and any advice to move between the private and the statutory system (T2-2).
- Cross-border work and A1 certificates (R-DE-SC-3).
- Professional pension funds (Versorgungswerke) (R-DE-SC-4).
- False self-employment and status determination (R-DE-SC-5, T2-4).
- Whether self-employment is the main occupation (T2-1): the fund decides case by case.
- Whether a profession is artistic or publicist: the KSK decides (T2-3).
- The amount of an accident insurance contribution: each accident insurer sets its own, and no official page prints a general rate.
- A given health fund's additional rate: look it up in the funds' list. This Guide only carries the ministry's average.
- Farmers and foresters: they have their own social insurance.
- Employees, Minijobs and employer shares: see `germany-payroll` and `de-payroll`.
- Pensioners, students and recipients of benefits who are also self-employed: other contribution rules apply.
- A voluntary GKV member whose spouse is not in a statutory fund: the spouse's income can count toward the contribution base (§ 240(5) SGB V). Refer to the fund.
- The special minimum pension bases of sole craftspeople and midwives: the pension insurer's form says they exist but does not print them.
- The income tax computation itself: see `de-einkommensteuer-freelancer`.

## Sources

- SGB V § 5, § 6, § 9, § 44, § 188, § 234, § 240, § 241, § 243, § 250: https://www.gesetze-im-internet.de/sgb_5/__5.html and https://www.gesetze-im-internet.de/sgb_5/__6.html and https://www.gesetze-im-internet.de/sgb_5/__9.html and https://www.gesetze-im-internet.de/sgb_5/__44.html and https://www.gesetze-im-internet.de/sgb_5/__188.html and https://www.gesetze-im-internet.de/sgb_5/__234.html and https://www.gesetze-im-internet.de/sgb_5/__240.html and https://www.gesetze-im-internet.de/sgb_5/__241.html and https://www.gesetze-im-internet.de/sgb_5/__243.html and https://www.gesetze-im-internet.de/sgb_5/__250.html
- SGB XI § 20, § 55, § 57, § 59: https://www.gesetze-im-internet.de/sgb_11/__20.html and https://www.gesetze-im-internet.de/sgb_11/__55.html and https://www.gesetze-im-internet.de/sgb_11/__57.html and https://www.gesetze-im-internet.de/sgb_11/__59.html
- SGB VI § 2, § 4, § 5, § 6, § 7, § 165, § 169, § 190a, § 197: https://www.gesetze-im-internet.de/sgb_6/__2.html and https://www.gesetze-im-internet.de/sgb_6/__4.html and https://www.gesetze-im-internet.de/sgb_6/__5.html and https://www.gesetze-im-internet.de/sgb_6/__6.html and https://www.gesetze-im-internet.de/sgb_6/__7.html and https://www.gesetze-im-internet.de/sgb_6/__165.html and https://www.gesetze-im-internet.de/sgb_6/__169.html and https://www.gesetze-im-internet.de/sgb_6/__190a.html and https://www.gesetze-im-internet.de/sgb_6/__197.html
- SGB VII § 3, § 6, § 152, § 192: https://www.gesetze-im-internet.de/sgb_7/__3.html and https://www.gesetze-im-internet.de/sgb_7/__6.html and https://www.gesetze-im-internet.de/sgb_7/__152.html and https://www.gesetze-im-internet.de/sgb_7/__192.html
- SGB III § 28a, § 341, § 345b: https://www.gesetze-im-internet.de/sgb_3/__28a.html and https://www.gesetze-im-internet.de/sgb_3/__341.html and https://www.gesetze-im-internet.de/sgb_3/__345b.html
- SGB IV § 7a, § 23: https://www.gesetze-im-internet.de/sgb_4/__7a.html and https://www.gesetze-im-internet.de/sgb_4/__23.html
- KSVG § 1, § 3, § 11, § 12, § 15, § 16, § 16a, § 24, § 25, § 27: https://www.gesetze-im-internet.de/ksvg/__1.html and https://www.gesetze-im-internet.de/ksvg/__3.html and https://www.gesetze-im-internet.de/ksvg/__11.html and https://www.gesetze-im-internet.de/ksvg/__12.html and https://www.gesetze-im-internet.de/ksvg/__15.html and https://www.gesetze-im-internet.de/ksvg/__16.html and https://www.gesetze-im-internet.de/ksvg/__16a.html and https://www.gesetze-im-internet.de/ksvg/__24.html and https://www.gesetze-im-internet.de/ksvg/__25.html and https://www.gesetze-im-internet.de/ksvg/__27.html
- Künstlersozialabgabe-Verordnung 2026: https://www.gesetze-im-internet.de/ksabg2026v/BJNR0DC0A0025.html
- Insurance contract act (VVG) § 193: https://www.gesetze-im-internet.de/vvg_2008/__193.html
- EStG § 3, § 10: https://www.gesetze-im-internet.de/estg/__3.html and https://www.gesetze-im-internet.de/estg/__10.html
- Sozialversicherungsrechengrößen-Verordnung 2026 (Federal Law Gazette): https://www.recht.bund.de/bgbl/1/2025/278/regelungstext.pdf?__blob=publicationFile&v=3
- Federal Government, contribution ceilings 2026: https://www.bundesregierung.de/breg-de/aktuelles/beitragsgemessungsgrenzen-2386514
- Health ministry, contributions of statutory health insurance: https://www.bundesgesundheitsministerium.de/beitraege
- Health ministry, financing of long-term care insurance: https://www.bundesgesundheitsministerium.de/themen/pflege/online-ratgeber-pflege/die-pflegeversicherung/finanzierung
- GKV-Spitzenverband, uniform rules for voluntary members (Beitragsverfahrensgrundsätze Selbstzahler), version of 1 January 2025: https://www.gkv-spitzenverband.de/media/dokumente/krankenversicherung_1/grundprinzipien_1/finanzierung/beitragsbemessung/2025-01-01_Einheitliche_Grundsaetze_zur_Beitragsbemessung_freiwilliger_Mitglieder_Stand_01_01_2025.pdf
- GKV-Spitzenverband, list of health funds with their additional rates: https://www.gkv-spitzenverband.de/service/krankenkassenliste/krankenkassen.jsp
- Deutsche Rentenversicherung, changes on 1 January 2026: https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026
- Deutsche Rentenversicherung, form V0091 (contribution values 2026): https://www.deutsche-rentenversicherung.de/SharedDocs/Formulare/DE/_pdf/V0091.pdf?__blob=publicationFile&v=4
- Deutsche Rentenversicherung, the self-employed: https://www.deutsche-rentenversicherung.de/DRV/DE/Rente/Arbeitnehmer-und-Selbststaendige/03_Selbststaendige/selbststaendige_node.html
- Deutsche Rentenversicherung, brochure for the self-employed, 21st edition (April 2026): https://www.deutsche-rentenversicherung.de/SharedDocs/Downloads/DE/Broschueren/national/selbstaendig_wie_rv_schuetzt_aktuell.pdf?__blob=publicationFile&v=8
- Deutsche Rentenversicherung, notice of 20 April 2026 on the tax deduction cap: https://www.deutsche-rentenversicherung.de/DRV/DE/Ueber-uns-und-Presse/Presse/Meldungen/2026/260420-vorsorgen-und-steuern-sparen
- Bundesagentur für Arbeit, leaflet on unemployment insurance on application (January 2026): https://www.arbeitsagentur.de/datei/hinweis-alv_ba035280.pdf
- DGUV, accident insurance for entrepreneurs: https://www.dguv.de/de/versicherung/versicherte_personen/vers-unternehmer/index.jsp

## Disclaimer

This Guide and its outputs are provided for informational and computational purposes only and do not constitute tax, legal, or financial advice. Open Accountants and its contributors accept no liability for any errors, omissions, or outcomes arising from the use of this Guide. All outputs must be reviewed and signed off by a qualified professional (such as a Steuerberater, Wirtschaftspruefer, or equivalent licensed practitioner in Germany) before filing or acting upon.

> Contributed by OpenAccountants.

<!-- openaccountants-cta-block -->

---

## Talk to a verified accountant

This guide is maintained by the OpenAccountants network — accountants who put
their name behind the tax answers AI gives people. The live, always-current
version (and the professional behind it) is at
[openaccountants.com](https://www.openaccountants.com).

- Use it in your AI: https://www.openaccountants.com/connect
- Meet the accountants: https://www.openaccountants.com/network

> **General reference only.** This document does not constitute tax, legal, or
> financial advice. Verify figures against the cited primary sources or with a
> licensed professional before relying on them.
