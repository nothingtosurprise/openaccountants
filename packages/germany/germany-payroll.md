---
name: germany-payroll
description: Use this skill whenever asked about German payroll processing for employees. Trigger on phrases like "German payroll", "Lohnsteuer", "Gehaltsabrechnung", "Brutto Netto Rechner", "Steuerklasse", "Sozialversicherung", "Arbeitnehmeranteil", "Arbeitgeberanteil", "Beitragsbemessungsgrenze", "payslip Germany", "Lohnabrechnung", "Nettolohn", "Solidaritätszuschlag", "Kirchensteuer", "Rentenversicherung", "Krankenversicherung", "Pflegeversicherung", "Arbeitslosenversicherung", "Minijob", "Midijob", "minimum wage Germany", "Mindestlohn", "Entgeltabrechnung", or any question about computing employee pay, withholding tax, or social contributions in Germany. This skill extends de-payroll.md with full payroll lifecycle coverage including mandatory benefits, payslip requirements, filing obligations, and employer cost analysis. ALWAYS read this skill before processing any German employee payroll.
version: 1.0
jurisdiction: DE
tax_year: 2026
last_updated: 2026-09-19
review_status: pending_review
drafted_by: OpenAccountants
approved_by: pending
depends_on:
  - payroll-workflow-base
category: payroll
tier: 2
license: AGPL-3.0-or-later (code) / OpenAccountants Guide License v1.0 (content)
---

# Payroll in Germany (Lohnabrechnung): wage tax, social insurance and employer duties

How a German employer runs payroll for employees: wage tax (Lohnsteuer) with solidarity surcharge and church tax, the four social insurance branches and who pays which share, the employer-only levies, minimum wage, Minijobs and the transition band, statutory leave and sick pay, what a payslip must show, and what is filed when. It is for employers, payroll staff and their advisers, and for employees who want to read their payslip. Figures are for tax year 2026. Sources dated another year: the church tax rates and the marginal tax rates in percent come from the finance ministry's tax booklet, 2025 edition, the latest one published; the Federal Central Tax Office text that names the church tax states carries no year; the health ministry's long-term care page gives rates "since 1 January 2025", and the health funds' fact sheet for 2026 prints the same base rate. Two rows state 2027 values that are already fixed by law and are marked as such.

## Germany Payroll Guide

Version 1.0 of this Guide, refreshed for 2026. It extends `de-payroll`, which holds the wage tax formula and worked examples, with the full payroll cycle: social insurance, minimum wage, statutory benefits, payslip contents, filing duties and the parts of employer cost.

## Section 1: Quick Reference

| Field | Value |
| --- | --- |
| Country | Germany (Bundesrepublik Deutschland) |
| Currency | EUR only |
| Standard pay frequency | Monthly is usual. The wage tax law also knows weekly and daily pay periods (§ 39b(2) EStG) |
| Tax year | Calendar year (1 January to 31 December) |
| Tax withholding | Lohnsteuer (LSt), worked out with the finance ministry's programme plan (Programmablaufplan, PAP) |
| Surcharges | Solidaritätszuschlag and Kirchensteuer, both charged on the wage tax and not on pay. Rates and limits are in Section 2 |
| Social insurance | Rentenversicherung (RV), Krankenversicherung (KV), Pflegeversicherung (PV), Arbeitslosenversicherung (AV). Accident insurance is paid by the employer alone |
| Tax authority | The Finanzamt of the place where payroll is run (Betriebsstättenfinanzamt) takes the wage tax returns. The BZSt (Federal Central Tax Office) holds the electronic wage tax data (ELStAM) |
| Social insurance authority | The employee's Krankenkasse (health fund) collects the total contribution for all four branches as Einzugsstelle (§ 28h and § 28i SGB IV). For Minijobs it is the Minijob-Zentrale (Deutsche Rentenversicherung Knappschaft-Bahn-See) |
| Key legislation | EStG § 38 to § 42g; SolzG; SGB IV, V, VI and XI, SGB III for unemployment insurance; AAG (employer levies); GewO § 108 and the Entgeltbescheinigungsverordnung (payslip); MiLoG (minimum wage) |
| PAP for 2026 | Published by the finance ministry on 12 November 2025: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026.html |
| Online calculator | The finance ministry's wage tax calculator at bmf-steuerrechner.de (named in the ministry's tax booklet; not linked here) |
| Validated by | Pending. Requires sign-off by a German Steuerberater |
| Guide version | 1.0 |

## Section 2: Income Tax Withholding (Lohnsteuer)

- **Who owes and who withholds.** The employee owes the wage tax. The employer withholds it at every wage payment for the employee's account. See § 38(2) and (3) EStG at https://www.gesetze-im-internet.de/estg/__38.html
- **The employer is liable** for wage tax it should have withheld and paid over. See § 42d EStG at https://www.gesetze-im-internet.de/estg/__42d.html
- **ELStAM.** At the start of the job the employer retrieves the employee's electronic wage tax data (tax class, child allowance count, church tax marker, any allowance) from the BZSt and puts it in the wage account. The employee gives the tax identification number and date of birth and says whether this is the first or a further job. See § 39e(4) EStG at https://www.gesetze-im-internet.de/estg/__39e.html

### Tax Brackets (2026 PAP, Grundtarif)

These are the zones of the yearly income tax tariff for 2026. They apply to taxable income for the year, not to gross pay.

**Income tax tariff 2026: the zones**

| Zone | Taxable income per year | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__32a.html |
| Basic allowance (Grundfreibetrag): no tax | up to EUR 12,348 | § 32a(1) EStG, from assessment period 2026: "bis 12 348 Euro (Grundfreibetrag)" |
| First progressive zone: the marginal rate rises along a formula | EUR 12,349 to EUR 17,799 | "von 12 349 Euro bis 17 799 Euro" |
| Second progressive zone: the marginal rate rises more slowly along a second formula | EUR 17,800 to EUR 69,878 | "von 17 800 Euro bis 69 878 Euro" |
| Proportional zone: the formula uses the factor 0.42 | EUR 69,879 to EUR 277,825 | "von 69 879 Euro bis 277 825 Euro" |
| Top zone: the formula uses the factor 0.45 | from EUR 277,826 | "von 277 826 Euro an" |

**Marginal rates in percent, as the ministry prints them (2025 edition)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Lowest marginal rate, just above the basic allowance (Eingangssteuersatz) | 14% | "in zwei linearprogressiven Zonen von 14 Pro- zent (Eingangssteuersatz) bis auf 42 Prozent (Spitzensteuersatz)" |
| Marginal rate in the proportional zone (Spitzensteuersatz) | 42% | "(sog. Proportionalzone) mit 42 Prozent besteuert" |
| Marginal rate in the top zone (the booklet calls it Reichensteuer) | 45% | "um weitere 3 Prozentpunkte auf dann 45 Prozent (Reichensteuer)" |

The booklet prints the zone limits of 2025. For 2026 use the limits in the statute table above. The marginal rates inside the two progressive zones are not printed on any official page read for this Guide, so none are stated.

- **PAP formula usage.** Payroll never applies the zones to one month's pay. The employer scales the pay of the period up to a year (monthly pay times twelve, weekly pay times 360/7, daily pay times 360), takes off the lump sums the law names (employee lump sum, special expenses lump sum, the provision lump sum for social insurance, and in class II the single parent relief for one child), applies the yearly tariff, and scales the tax back (one twelfth, 7/360 or 1/360). See § 39b(2) EStG at https://www.gesetze-im-internet.de/estg/__39b.html The finance ministry publishes this as a programme plan each year under § 39b(6) EStG. See `de-payroll` for the formula.
- **Splitting.** In class III the tariff is applied to half of the taxable amount and the tax is doubled (§ 32a(5) EStG, same page as the zones table).
- **One-off pay (sonstige Bezüge)** such as a bonus is taxed by the yearly method: the tax on the expected yearly pay with the one-off pay, less the tax on it without (§ 39b(3) EStG, same page as above).

**Classes V and VI: the special computation**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__39b.html |
| The yearly wage tax is at least this share of the taxable yearly amount | 14% | § 39b(2) sentence 7 EStG: "mindestens 14 Prozent des zu versteuernden Jahresbetrags" |
| First limit. On the part of the taxable yearly amount above it, the tax is at most the rate in the next row | EUR 14,071 | "für den 14 071 Euro übersteigenden Teil des zu versteuernden Jahresbetrags höchstens 42 Prozent" |
| Rate that caps the tax above the first limit and applies above the second limit | 42% | Same sentence |
| Second limit. On the part above it the rate in the row above applies, no longer as a cap | EUR 34,939 | "für den 34 939 Euro übersteigenden Teil des zu versteuernden Jahresbetrags 42 Prozent" |
| Third limit. On the part above it the rate in the next row applies | EUR 222,260 | "für den 222 260 Euro übersteigenden Teil des zu versteuernden Jahresbetrags 45 Prozent" |
| Rate on the part above the third limit | 45% | Same sentence |

The starting point in classes V and VI is twice the difference between the tariff tax on one and a quarter times and on three quarters of the taxable yearly amount. The rows above are not tax brackets. The first row is a floor on that result and the first limit starts a cap on it. For the parts above the second and the third limit the law fixes the rate itself. Everything is measured on the taxable yearly amount after the lump sums of sentence 5, not on gross pay, and only in classes V and VI.

### Steuerklassen (Tax Classes)

| Class | Who | Key Feature |
| --- | --- | --- |
| I | Single, or married, widowed or divorced without the conditions for class III or IV. Also employees with limited tax liability | Grundtarif |
| II | Class I employees who get the single parent relief (§ 24b EStG) | Grundtarif plus the relief for one child in the table below |
| III | Married, both spouses fully liable and not permanently separated, when both apply and the other spouse takes class V. Also widowed employees for the year after the death | Splittingverfahren (KZTAB=2 in the programme plan) |
| IV | Married, both spouses fully liable and not permanently separated. Also when one spouse has no wages and no application for III and V was made | Grundtarif. Optional factor (§ 39f EStG): on joint application, class IV with a factor below 1 that brings the splitting effect into withholding. The factor holds until the end of the following calendar year |
| V | The spouse of a class III employee, on joint application | Special computation (table above). The employee lump sum and the special expenses lump sum still apply (§ 39b(2) sentence 5 EStG) |
| VI | Second and further jobs held side by side, and the cases of § 39c EStG | Special computation (table above). No employee lump sum and no special expenses lump sum |

See § 38b EStG at https://www.gesetze-im-internet.de/estg/__38b.html and § 39f EStG at https://www.gesetze-im-internet.de/estg/__39f.html An employee may ask for a less favourable class, and one spouse alone may move both from III and V to IV (§ 38b(3) EStG).

**Single parent relief (class II)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__24b.html |
| Relief per calendar year when one qualifying child lives in the household | EUR 4,260 | § 24b(2) EStG: "beträgt der Entlastungsbetrag im Kalenderjahr 4 260 Euro" |
| Increase for each further qualifying child | EUR 240 | "um 240 Euro je weiterem Kind" |

Class II itself carries only the one-child amount (§ 39b(2) sentence 5 no. 4 EStG). The relief falls by one twelfth for each full month in which the conditions are not met, and it is lost when another adult shares the household, with the exceptions in § 24b(3) EStG.

**Employees past the standard retirement age (from 2026)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__3.html |
| Wages that stay free of wage tax per year, for work done from the month after the employee reaches the standard retirement age, only where the employer owes pension contributions for that work. Not for Minijobs | EUR 24,000 | § 3 no. 21 EStG: "bis zu einer Höhe von insgesamt 24 000 Euro im Jahr" |

The amount falls by one twelfth for each month in which the conditions are not met. In withholding the employer counts the amount pro rata over time (zeitanteilig). In class VI it counts only if the employee confirms to the employer that no other job uses it, and the confirmation goes into the wage account (§ 3 no. 21 sentences 3 to 6 EStG). The contribution exemption for tax-free extras does not apply to income that is tax-free only under this rule (§ 1(1) no. 1 SvEV), and such income bars the employer's yearly adjustment (§ 42b(1) no. 4 EStG).

### Solidaritätszuschlag (2026)

**Rate and phase-in**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__4.html |
| Surcharge rate, charged on the wage tax | 5.5% | § 4 SolzG: "Der Solidaritätszuschlag beträgt 5,5 Prozent der Bemessungsgrundlage" |
| Phase-in cap: the surcharge is not more than this share of the amount by which the wage tax exceeds the limit below | 11.9% | "Er beträgt nicht mehr als 11,9 Prozent des Unterschiedsbetrages" |

**Exemption limit (Freigrenze), first applied for 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__3.html |
| Yearly tax up to which no surcharge is charged: splitting cases, in payroll class III | EUR 40,700 | § 3(3) SolzG: "in den Fällen des § 32a Absatz 5 und 6 des Einkommensteuergesetzes 40 700 Euro" |
| Yearly tax up to which no surcharge is charged: all other cases, in payroll classes I, II, IV, V and VI | EUR 20,350 | "in anderen Fällen 20 350 Euro übersteigt" |

- **It is a limit with a phase-in, not an allowance.** At or below the limit there is no surcharge. Above it, the surcharge is the smaller of the full rate on the whole wage tax and the phase-in share of the excess.
- **Pay periods.** For monthly pay the limit is one twelfth of the yearly amount, for weekly pay 7/360 and for daily pay 1/360 (§ 3(4) SolzG). The statute prints these as fractions, not as amounts.
- **The base is a wage tax computed with child allowances**, even though the wage tax itself ignores them (§ 3(2a) SolzG).
- **One-off pay.** The surcharge on one-off pay is the full rate with no phase-in cap, and only when the yearly wage tax exceeds the limit (§ 3(4a) and § 4 SolzG).
- **Start date.** § 6(27) SolzG applies these limits from assessment period 2026. The ministry's programme plan for 2026 uses the same yearly limit. See https://www.gesetze-im-internet.de/solzg_1995/__6.html

### Kirchensteuer

**Rates as the finance ministry prints them (2025 edition)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Church tax, charged on the wage tax, depending on the federal state | 8% or 9% | "beträgt je nach Bundesland 8 oder 9 Prozent" |

**Which states use which rate, as the Federal Central Tax Office prints it**

| Land | Rate | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bzst.de/SharedDocs/Downloads/DE/KiStA/Widerspruch_Mustertext.pdf?__blob=publicationFile&v=10 |
| Bavaria, Baden-Württemberg | 8% | "Württemberg und Bayern 8 Prozent, in den übrigen Bundesländern 9 Prozent" |
| All other Länder | 9% | Same sentence. The text is a sample letter about church tax on investment income; it is the only federal page found that names the states |

- **Applies only if** the employee's ELStAM carry a church tax marker. The employer never decides membership itself.
- **Base.** The wage tax, with child allowances taken into account. The ministry booklet says the rate is fixed by the tax resolutions of the religious communities entitled to levy the tax (table above). No federal statute page prints it.
- **Minijob flat tax.** The uniform flat tax for Minijobs in Section 5 already includes church tax.

## Section 3: Social Security: Employee Deductions (2026)

### Contribution Rates and Ceilings

| Branch | German Name | How it is shared | Ceiling that applies |
| --- | --- | --- | --- |
| Pension | Rentenversicherung (RV) | Half each. See the pension table below | Pension ceiling |
| Health | Krankenversicherung (KV) | The general rate and the health fund's own additional rate are each borne half by the employee and half by the employer. The law says this in words (§ 249 SGB V) and no official page read prints the half as a number, so none is stated here | Health and care ceiling |
| Care | Pflegeversicherung (PV) | Half each of the base rate, except in Saxony. The childless surcharge is the employee's alone. See the care table below | Health and care ceiling |
| Unemployment | Arbeitslosenversicherung (AV) | Half each. See the unemployment table below | Pension ceiling |

**Pension and unemployment insurance: the halves**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/KnappschaftBahnSee/DE/Aktuelles/Meldungen/2026/2026_01_02_Sozialversicherungsrechengroessen2026.html |
| Pension insurance: employee share, and the equal employer share | 9.3% | "Der Arbeitnehmer- als auch der Arbeitgeberanteil beträgt jeweils 9,3 Prozent" |
| Unemployment insurance: employee share, and the equal employer share. Not to be confused with Saxony's employer share of care insurance, which is the same number | 1.3% | "Der Arbeitnehmer- als auch der Arbeitgeberanteil hat eine Höhe von 1,3 Prozent" |

**Pension insurance: the full rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026 |
| General pension insurance, full rate for 2026. Not the miners' scheme and not the Minijob flat rate | 18.6% | "Dieser beträgt 2026 weiterhin 18,6 Prozent" |

**Unemployment insurance: the full rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_3/__341.html |
| Unemployment insurance, full rate. The ceiling is the pension ceiling | 2.6% | § 341(2) SGB III: "Der Beitragssatz beträgt 2,6 Prozent" |

**Health insurance: the general rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_5/__241.html |
| General rate, full, for members with a sick pay claim. The health fund's additional rate comes on top | 14.6% | § 241 SGB V: "Der allgemeine Beitragssatz beträgt 14,6 Prozent der beitragspflichtigen Einnahmen" |

**Health insurance: the average additional rate (Zusatzbeitrag)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesgesundheitsministerium.de/beitraege |
| Average additional rate for 2026, set by the health ministry. It is not what a given health fund charges | 2.9% | "Für das Jahr 2026 beträgt der durchschnittliche Zusatzbeitragssatz 2,9 Prozent" |

- **Average Zusatzbeitrag 2026.** Payroll uses the rate of the employee's own health fund, not the average. Each fund sets its own rate. The ministry page says the average applies to some groups only, for example low earners, apprentices paid up to the apprentice limit in Section 4, and recipients of basic income support. It also says the national association of health funds publishes an overview of the funds' rates.
- **Halves.** See § 249(1) SGB V at https://www.gesetze-im-internet.de/sgb_5/__249.html Older material prints a half of the general rate and a combined employee health rate. Neither is printed on an official page read for this Guide, so neither is stated.
- **A missed deduction** of the employee's share can only be made up in the next three wage payments, unless the employer was not at fault. See § 28g SGB IV at https://www.gesetze-im-internet.de/sgb_4/__28g.html

### Pflegeversicherung Employee Rates (2026)

**Long-term care insurance: rates and shares**

| Situation | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesgesundheitsministerium.de/themen/pflege/online-ratgeber-pflege/die-pflegeversicherung/finanzierung |
| Full base rate (a member with one child). Not to be confused with a Minijobber's own pension share, which is the same number | 3.6% | "Seit dem 1. Januar 2025 beträgt der Beitragssatz 3,6 Prozent der beitragspflichtigen Einnahmen" |
| Full rate for a childless member | 4.2% | "bei Kinderlosen sind es 4,2 Prozent" |
| Childless surcharge (Kinderlosenzuschlag), paid by the employee alone | 0.6% | "Beitragszuschlag für Kinderlose in Höhe von 0,6 Prozent der beitragspflichtigen Einnahmen" |
| Employee share with one child, and the employer share, in every state except Saxony | 1.8% | "grundsätzlich zur Hälfte, also jeweils 1,8 Prozent" |
| Employee share, childless, age 23 and over | 2.4% | Table on the page (columns: employee, childless employee, employer): "Übrige Bundesländer 1,8 % 2,4 % 1,8 %" |
| Employee share with 2 children under 25 | 1.55% | List on the page, entry "Mitglieder mit 2 Kindern": "(Arbeitnehmer-Anteil: 1,55 %)" |
| Employee share with 3 children under 25 | 1.3% | Entry "Mitglieder mit 3 Kindern": "(Arbeitnehmer-Anteil: 1,3 %)" |
| Employee share with 4 children under 25 | 1.05% | Entry "Mitglieder mit 4 Kindern": "(Arbeitnehmer-Anteil: 1,05 %)" |
| Employee share with 5 or more children under 25 | 0.8% | Entry "Mitglieder mit 5 und mehr Kindern": "(Arbeitnehmer-Anteil: 0,8 %)" |
| Sachsen exception: the employee share in every row above is higher by | 0.5% | "Erhöhung des Arbeitnehmeranteils jeweils um 0,5 % im Bundesland Sachsen" |
| Saxony: employee share with one child | 2.3% | "2,3 Prozent auf die Beschäftigten und 1,3 Prozent auf die Arbeitgeber" |
| Saxony: employee share, childless | 2.9% | Table on the page: "Bundesland Sachsen 2,3 % 2,9 % 1,3 %" |
| Saxony: employer share. Not to be confused with the half of unemployment insurance, which is the same number | 1.3% | "1,3 Prozent auf die Arbeitgeber" |

**The reduction per child**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf |
| Reduction of the care rate for each child from the second to the fifth, in percentage points | 0.25% | "Beitragsabschlag ab dem zweiten bis zum fünften Kind jeweils 0,25 %" |

- **Who pays the surcharge.** Childless members, from the end of the month in which they turn 23. Not members born before 1 January 1940, not conscripts, and not recipients of basic income support. A parent does not pay it: the ministry page marks the one-child rate as lifelong. See § 55(3) SGB XI at https://www.gesetze-im-internet.de/sgb_11/__55.html
- **Who gets the reduction.** Parents, for each child from the second to the fifth, until the end of the month in which that child turns 25. Children who have turned 25 are not counted at all when the reduction is worked out, so the rows above count only children under 25. Nothing for the first child and nothing beyond the fifth. The reduction lowers the employee share only. The ministry page says the employer share stays the same whatever the number of children.
- **Stale statute.** § 55(1) SGB XI on the federal law site still prints an older base rate, because the rise was made by regulation. Use the ministry page above for the rate. The surcharge, reduction and proof rules in § 55(3) and (3a) are current. The finance ministry's programme plan for 2026 uses the same employee shares, Saxony share, surcharge and per-child reduction as parameters, and the health ministry page above was last updated in September 2026.
- **Proof.** Parenthood and the number of children under 25 must be proven to the body that pays the contributions over, which in payroll is the employer, unless it already knows them (§ 55(3a) SGB XI, same page). The payslip shows a code for it (Section 7).

### Beitragsbemessungsgrenzen (2026)

**Pension and unemployment ceiling, and the compulsory insurance thresholds**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.recht.bund.de/bgbl/1/2025/278/regelungstext.pdf?__blob=publicationFile&v=3 |
| RV/AV-BBG: pension and unemployment ceiling, per year. One value for west and east | EUR 101,400 | "in der allgemeinen Rentenversicherung auf 101 400 Euro jährlich" |
| RV/AV-BBG per month | EUR 8,450 | "umgerechnet auf den Monat ergeben sich 8 450 Euro" |
| JAEG (Versicherungspflichtgrenze), general threshold, per year. It is a status test, not a ceiling | EUR 77,400 | "für das Jahr 2026 auf 77 400 Euro festgesetzt" |
| JAEG, general threshold, per month | EUR 6,450 | "Umgerechnet auf den Monat ergeben sich 6 450 Euro" |
| Special threshold, per year: only for employees who were privately insured and above the threshold on 31 December 2002 | EUR 69,750 | "für das Jahr 2026 auf 69 750 Euro festgesetzt" |
| Special threshold per month | EUR 5,812.50 | "Umgerechnet auf den Monat ergeben sich 5 812,50 Euro" |

**Health and care ceiling**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesregierung.de/breg-de/aktuelles/beitragsgemessungsgrenzen-2386514 |
| KV/PV-BBG: health and care ceiling, per year. In 2026 it is the same number as the special threshold above, but it is a different rule | EUR 69,750 | "Beitragsbemessungsgrenze 2026 auf jährlich 69.750 Euro beziehungsweise 5.812,50 Euro im Monat" |
| KV/PV-BBG per month | EUR 5,812.50 | Same sentence |

- **What a ceiling is.** Pay above the ceiling carries no contributions in that branch. It is not an allowance: pay below it is charged in full from the first euro.
- **What the JAEG is.** An employee whose regular yearly pay is above the general threshold may leave statutory health insurance. Compulsory cover ends only at the end of the calendar year in which the threshold is exceeded, and only if the pay also exceeds the threshold of the next year. See § 6(4) SGB V at https://www.gesetze-im-internet.de/sgb_5/__6.html
- **One-off pay** is charged in the month it is paid, but only up to the part of the yearly ceiling that matches the time worked for this employer so far in the year, less pay already charged. One-off pay from 1 January to 31 March is counted in the last pay period of the year before when the same employer pays it and it would otherwise pass the ceiling. See § 23a SGB IV at https://www.gesetze-im-internet.de/sgb_4/__23a.html

## Section 4: Social Security: Employer Contributions (2026)

### Employer Rates and Ceilings

| Branch | Employer share | Ceiling |
| --- | --- | --- |
| Pension (RV) | The same half as the employee. See the halves table in Section 3 | Pension ceiling |
| Health (KV) | Half of the general rate and half of the fund's additional rate. No official page read prints the half as a number | Health and care ceiling |
| Care (PV) | Half of the base rate. See the care table in Section 3. The employer pays no part of the childless surcharge and gets no benefit from the child reductions | Health and care ceiling |
| Unemployment (AV) | The same half as the employee. See the halves table in Section 3 | Pension ceiling |

- **PV employer rate Sachsen exception.** In Saxony the employer share of care insurance is lower and the employee share higher. Both are in the care table in Section 3.
- **No monthly maximums are stated.** Older material prints a highest monthly contribution per branch. Those are products of a rate and a ceiling. No official page read prints them, so they are not stated. The payroll software works them out from the tables.

**Apprentices on low pay: the employer pays everything**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_4/__20.html |
| Monthly pay of an apprentice up to which the employer bears the whole social insurance contribution alone | EUR 325 | § 20(3) SGB IV: "ein Arbeitsentgelt erzielen, das auf den Monat bezogen 325 Euro nicht übersteigt" |

**Employer subsidy for employees who are not compulsorily insured (pay above the JAEG)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf |
| Highest monthly subsidy to health insurance with sick pay claim, before half of the additional contribution, which the sheet says comes on top | EUR 424.31 | "Krankenversicherung mit Anspruch auf Krankengeld 424,31" |
| Highest monthly subsidy to care insurance, every state except Saxony | EUR 104.63 | "Pflegeversicherung (bundeseinheitlich außer Sachsen) 104,63" |
| Highest monthly subsidy to care insurance, Saxony only | EUR 75.56 | "Pflegeversicherung nur Bundesland Sachsen 75,56" |

A voluntary member of a statutory fund gets what the employer would pay under compulsory cover. A privately insured employee gets at most half of what the employee really pays for the private cover. See § 257 SGB V at https://www.gesetze-im-internet.de/sgb_5/__257.html

### Employer-Only Contributions (not deducted from employee)

| Contribution | Rate | Base |
| --- | --- | --- |
| Umlage U1 (continued pay in sickness). Only employers with, as a rule, not more than 30 employees, apprentices not counted | Set by each health fund in its statutes. No general rate exists. The rate the Minijob-Zentrale charges is in Section 5 and applies to Minijobs only | The pay on which pension contributions are assessed, so up to the pension ceiling. For U1, one-off pay is left out, and so is the pay of staff employed for not more than four weeks who can get no continued pay (§ 7(2) AAG) |
| Umlage U2 (maternity costs). All employers | Set by each health fund. No general rate exists | The pay on which pension contributions are assessed |
| Insolvenzgeldumlage | See the table below | The pay on which pension contributions are assessed |
| Berufsgenossenschaft (accident insurance) | No general rate exists. The accident insurer works out the contribution after the end of the year from its financial need, the wages paid and the hazard class of the trade | Gross wages, as the insurer's wage catalogue defines them |

- **Correction.** Older material gives rate ranges for U1, U2 and accident insurance and says the levy base runs up to the health ceiling. No official page prints such ranges, and § 7(2) AAG ties the base to pension-assessable pay. See https://www.gesetze-im-internet.de/aufag/__7.html
- **Accident insurance.** Only the employer pays: § 150(1) SGB VII at https://www.gesetze-im-internet.de/sgb_7/__150.html How the contribution is worked out: https://www.dguv.de/de/ihr_partner/unternehmen/beitragsberechnung/index.jsp

**Insolvency levy**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://magazin.minijob-zentrale.de/minijob-beitraege-2026/ |
| Insolvenzgeldumlage for 2026, employer only. The same rate applies to ordinary employees. Not payable by private households or public bodies | 0.15% | Table headed 2026: "Insolvenzgeldumlage 0,15% 0,15%" |

The statute prints the same rate: § 360 SGB III at https://www.gesetze-im-internet.de/sgb_3/__360.html

**What U1 and U2 pay back**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/aufag/__1.html |
| U1: statutory share of continued sick pay, and of the employer contributions on it, that the health fund refunds. A fund's statutes may set other levels | 80% | § 1(1) AAG: "nicht mehr als 30 Arbeitnehmer und Arbeitnehmerinnen beschäftigen, 80 Prozent" |

U2 refunds the employer's maternity pay top-up and the pay during employment bans in full, with the employer contributions on that pay (§ 1(2) AAG, same page).

### Total Employer Cost Estimate

No official page prints a total employer on-cost as a share of gross pay, and this Guide does not compute one. An earlier worked example with estimated shares is gone for that reason. The parts are:

1. The employer shares of pension, health, care and unemployment insurance (Section 3 tables), each only up to its ceiling.
2. Half of the health fund's own additional rate.
3. U1 where the employer is small enough, U2, and the insolvency levy.
4. The accident insurance contribution, billed after the year by the accident insurer.
5. For employees above the JAEG, the subsidy instead of the health and care shares.

## Section 5: Minimum Wage and Overtime

### Minimum Wage (Mindestlohn, 2026)

| Item | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/milov5/__1.html |
| Statutory minimum from 1 January 2026, gross per hour worked | EUR 13.90 | Fifth Minimum Wage Adjustment Regulation: "ab 1. Januar 2026 13,90 Euro brutto je Zeitstunde" |
| Statutory minimum from 1 January 2027 (not the 2026 amount) | EUR 14.60 | "ab 1. Januar 2027 14,60 Euro brutto je Zeitstunde" |

- **Stale statute.** § 1(2) MiLoG on the federal law site still prints the first amount of 2022. The regulation above is the source. Sector minimum wages can be higher.
- **Due date.** The minimum wage must be paid at the agreed date, and at the latest on the last bank working day (Frankfurt am Main) of the month after the work was done. See § 2 MiLoG at https://www.gesetze-im-internet.de/milog/__2.html
- **Who is not covered.** Persons under 18 without completed vocational training; apprentices; volunteers; compulsory internships and the short internships listed in the law; and formerly long-term unemployed employees in the first six months of the job. See § 22 MiLoG at https://www.gesetze-im-internet.de/milog/__22.html
- **Working time records.** For Minijobbers and short-term staff, and in the sectors named in § 2a of the Schwarzarbeitsbekämpfungsgesetz, the employer records start, end and length of daily working time within seven days and keeps the records for at least two years. See § 17 MiLoG at https://www.gesetze-im-internet.de/milog/__17.html A regulation relaxes this for some staff; it was not read for this Guide.

**Minijob threshold**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesregierung.de/breg-de/aktuelles/mindestlohn-steigt-2391010 |
| Minijob earnings limit (Geringfügigkeitsgrenze) from 1 January 2026: regular monthly pay. Not to be confused with the minimum base for voluntary pension contributions, which is the same number | EUR 603 | "Sie liegt seit 1. Januar 2026 bei 603 Euro im Monat. 2027 steigt sie auf 633 Euro." |
| Minijob earnings limit for 2027 (not the 2026 limit) | EUR 633 | Same sentence |

**Minijob limit per year, and where the Midijob starts**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026 |
| Minijob limit for 2026 per year. Monthly pay may vary as long as the yearly amount is kept | EUR 7,236 | "603 Euro monatlich beziehungsweise 7.236 Euro jährlich" |
| Midijob (Übergangsbereich): lower limit per month | EUR 603.01 | "steigt im kommenden Jahr auf monatlich 603,01 Euro" |

**Midijob (Übergangsbereich): upper limit**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_4/__20.html |
| Upper limit of the transition band: regular monthly pay. With several jobs the total counts. Not for apprentices | EUR 2,000 | § 20(2) SGB IV: "die regelmäßig 2 000 Euro im Monat nicht übersteigen" |

**Midijob factor and Minijob pension base, from the health funds' fact sheet for 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf |
| Total social insurance rate for 2026. It exists only to derive Factor F. Nobody pays this rate | 42.30% | "Gesamtsozialversicherungsbeitragssatz / Faktor F 42,30 % / 0,6619" |
| Factor F for 2026, used in the § 20(2a) SGB IV formula | 0.6619 | Same line |
| Lowest monthly base for the pension contribution of a Minijobber who is subject to pension duty | EUR 175 | "Mindestbemessungsgrundlage i. d. RV für geringfügig Beschäftigte 175,00" |

- **How the Minijob limit moves.** It is the minimum wage times 130, divided by three, rounded up to a full euro (§ 8(1a) SGB IV). See https://www.gesetze-im-internet.de/sgb_4/__8.html
- **Going over the limit.** An unforeseeable overrun in not more than two calendar months of a twelve-month period, each time by no more than the limit itself, does not end the Minijob (§ 8(1b) SGB IV). That rule covers unforeseeable overruns only. For pay that varies in a foreseeable way the test is whether regular pay stays within the limit (§ 8(1) no. 1 SGB IV), which the pension insurer also prints as a yearly amount (table above).
- **Several jobs are added together** (§ 8(2) SGB IV). One Minijob next to a main job stays a Minijob.
- **Short-term jobs** are the other kind of marginal employment: limited in advance to three months or 70 working days in the calendar year, and not done as a profession when pay is above the limit (§ 8(1) no. 2 SGB IV).
- **Inside the transition band** the employee's share is worked out on a reduced base and the employer bears the rest. Above the band the normal halves apply. The formulas are in § 20(2a) SGB IV (link in the upper limit table).

**Commercial Minijob with earnings limit: what the employer pays to the Minijob-Zentrale in 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://magazin.minijob-zentrale.de/minijob-beitraege-2026/ |
| Flat health insurance contribution, only if the Minijobber is in statutory health insurance | 13% | "Krankenversicherung 13% - Rentenversicherung 15%" |
| Flat pension contribution | 15% | Same line |
| The Minijobber's own pension share, withheld from pay, unless released on application | 3.6% | "Dieser Eigenanteil liegt im Jahr 2026 bei 3,6 Prozent des Verdienstes bei gewerblichen Minijobs" |
| U1 rate of the Minijob-Zentrale from 1 January 2026. For Minijobs and short-term jobs only | 0.8% | "Zum 1. Januar 2026 wurde die Umlage 1 von bisher 1,1 Prozent auf 0,8 Prozent" |
| U2 rate of the Minijob-Zentrale. For Minijobs and short-term jobs only | 0.22% | "Umlage 2 0,22% 0,22%" |

**The most a commercial employer pays in total**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.minijob-zentrale.de/DE/fuer-gewerbetreibende/abgaben-und-steuern/detailseite |
| Highest total of contributions, levies and flat tax, as the Minijob-Zentrale prints it. Accident insurance comes on top | 31.17% | "insgesamt bei höchstens 31,17 Prozent" |

**Flat wage tax for marginal and short-term jobs**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__40a.html |
| Uniform flat tax for a Minijob where the employer pays the flat pension contribution. It covers wage tax, solidarity surcharge and church tax, and goes to the Minijob-Zentrale | 2% | § 40a(2) EStG: "mit einem einheitlichen Pauschsteuersatz in Höhe von insgesamt 2 Prozent des Arbeitsentgelts" |
| Flat wage tax where the employer does not owe the flat pension contribution. Surcharge and church tax come on top. Paid to the tax office | 20% | § 40a(2a) EStG: "mit einem Pauschsteuersatz in Höhe von 20 Prozent des Arbeitsentgelts" |
| Flat wage tax for short-term employees under the tax-law test: occasional work, not more than 18 working days in a row. Surcharge and church tax come on top. Paid to the tax office | 25% | § 40a(1) EStG: "mit einem Pauschsteuersatz von 25 Prozent des Arbeitslohns erheben" |
| Short-term employees: highest average pay per working day, unless the work became necessary at once at an unforeseeable time | EUR 150 | "150 Euro durchschnittlich je Arbeitstag nicht übersteigt" |
| Short-term employees: no flat tax when average pay per hour is above | EUR 19 | § 40a(4) EStG: "durchschnittlich je Arbeitsstunde 19 Euro übersteigt" |

The employer may always tax a Minijob by the employee's ELStAM instead. The tax-law test for a short-term job is not the social insurance test in the bullet above.

### Working Hours and Overtime

| Rule | Detail |
| --- | --- |
| Standard weekly hours | No statutory standard. Set by employment contract or collective agreement |
| Maximum daily hours | 8 hours per working day. Up to 10 hours only if the average over six calendar months or 24 weeks stays at 8 hours per working day (§ 3 ArbZG) |
| Maximum weekly hours | § 3 ArbZG prints limits per working day (werktäglich) only and no weekly number. Weekly figures found in older material are products of the daily limits and are not stated here |
| Overtime regulation | No federal overtime pay rule beyond the working time limits. Overtime pay and surcharges come from the collective agreement (Tarifvertrag) or the contract |
| Typical overtime surcharges | Not stated. No official page prints typical shares. They come from the collective agreement or the contract |
| Tax treatment of surcharges | Surcharges for night, Sunday and public holiday work paid on top of basic pay are tax-free within the shares in the table below |

See § 3 ArbZG at https://www.gesetze-im-internet.de/arbzg/__3.html

**Tax-free surcharges for night, Sunday and public holiday work**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__3b.html |
| Night work (20:00 to 06:00), share of basic pay | 25% | § 3b(1) EStG: "für Nachtarbeit 25 Prozent" |
| Night work from 00:00 to 04:00, when the shift began before midnight | 40% | § 3b(3) EStG: "erhöht sich der Zuschlagssatz auf 40 Prozent" |
| Sunday work | 50% | "für Sonntagsarbeit 50 Prozent" |
| Public holidays, and 31 December from 14:00 | 125% | "an den gesetzlichen Feiertagen 125 Prozent" |
| 24 December from 14:00, 25 and 26 December, and 1 May | 150% | "sowie am 1. Mai 150 Prozent" |
| Highest hourly basic pay (Grundlohn) that counts for the tax exemption | EUR 50 | § 3b(2) EStG: "mit höchstens 50 Euro anzusetzen" |

**The same surcharges in social insurance**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/svev/__1.html |
| The tax-free surcharges are free of contributions only so far as the hourly pay they are worked out on is not more than | EUR 25 | § 1(1) no. 1 SvEV: "mehr als 25 Euro für jede Stunde beträgt" |

Only surcharges for work really done count, and only when paid on top of basic pay. The tax cap and the social insurance cap differ, so a surcharge can be tax-free and still carry contributions.

## Section 6: Mandatory Benefits

### Annual Leave (Bundesurlaubsgesetz)

| Entitlement | Detail |
| --- | --- |
| Minimum statutory | At least 24 Werktage per year. Werktage are all calendar days that are not Sundays or public holidays, so the law counts on a six-day week (§ 3 BUrlG). The statute prints no figure for a five-day week. The figure often quoted for it is a conversion and is not stated here |
| Typical contractual | Not stated. No official page prints a typical contractual figure. Read the contract or the collective agreement |
| Carry-over | Leave must be given and taken in the current calendar year. It carries over only for urgent operational or personal reasons, and then must be taken in the first three months of the next year (§ 7(3) BUrlG). Leave that cannot be taken because the job ends is paid out (§ 7(4) BUrlG) |

See § 3 BUrlG at https://www.gesetze-im-internet.de/burlg/__3.html and § 7 BUrlG at https://www.gesetze-im-internet.de/burlg/__7.html

### Sick Leave (Entgeltfortzahlungsgesetz)

| Entitlement | Detail |
| --- | --- |
| Employer-paid sick leave | Up to six weeks for each case of incapacity, at the pay the employee would have had for regular working time, without overtime pay (§ 3 and § 4 EntgFG). The claim starts only after four weeks of unbroken employment |
| Same illness again | A new six weeks only if the employee was not unfit from that illness for at least six months, or twelve months have passed since the first incapacity from it began. It is not "six weeks per illness per year", as older material says |
| After 6 weeks | Krankengeld from the Krankenkasse. See the table below |
| Medical certificate | If the incapacity lasts longer than three calendar days, a certificate is due on the next working day. The employer may ask for it earlier. Members of a statutory health fund do not hand in paper: they must have the incapacity established by a doctor at those times. Two groups still hand in paper: Minijobbers in private households, and patients of doctors outside statutory health care (§ 5(1) and (1a) EntgFG) |

See § 3 EntgFG at https://www.gesetze-im-internet.de/entgfg/__3.html and § 4 at https://www.gesetze-im-internet.de/entgfg/__4.html and § 5 at https://www.gesetze-im-internet.de/entgfg/__5.html

**Krankengeld (paid by the health fund, not by the employer)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_5/__47.html |
| Krankengeld as a share of regular pay that is subject to contributions | 70% | § 47(1) SGB V: "Das Krankengeld beträgt 70 vom Hundert des erzielten regelmäßigen Arbeitsentgelts" |
| It may not exceed this share of net pay | 90% | "darf 90 vom Hundert des bei entsprechender Anwendung des Absatzes 2 berechneten Nettoarbeitsentgelts nicht übersteigen" |

For the same illness Krankengeld runs for at most 78 weeks within three years, counted from the first day of incapacity. See § 48 SGB V at https://www.gesetze-im-internet.de/sgb_5/__48.html

### Maternity Leave (Mutterschutzgesetz)

| Entitlement | Detail |
| --- | --- |
| Pre-birth protection | The last 6 weeks before the expected date. The woman may work if she expressly declares that she is willing, and may take that back at any time |
| Post-birth protection | 8 weeks. The employer may not employ the woman in that time; the only openings are those of § 3(3) and (4) MuSchG (school or university training at her express request, and after the death of the child). 12 weeks for premature births, multiple births and, on application, when a disability of the child is found within 8 weeks. After an early birth the days lost before the birth are added |
| Miscarriage | Protection periods of two, six or eight weeks from the 13th, 17th or 20th week of pregnancy, unless the woman expressly declares that she is willing to work |
| Pay | Mutterschaftsgeld from the Krankenkasse plus an employer top-up. See the tables below. The employer gets the top-up back in full through U2 (Section 4) |

See § 3 MuSchG at https://www.gesetze-im-internet.de/muschg_2018/__3.html

**Mutterschaftsgeld from the health fund**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_5/__24i.html |
| Highest Mutterschaftsgeld per calendar day for members in employment | EUR 13 | § 24i(2) SGB V: "Es beträgt höchstens 13 Euro für den Kalendertag" |

**Employer top-up**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/muschg_2018/__20.html |
| The employer pays the difference between this amount and the average net pay per calendar day of the last three settled calendar months before the protection period | EUR 13 | § 20(1) MuSchG: "der Unterschiedsbetrag zwischen 13 Euro und dem um die gesetzlichen Abzüge verminderten durchschnittlichen kalendertäglichen Arbeitsentgelt" |

**Women who are not members of a statutory health fund**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/muschg_2018/__19.html |
| Mutterschaftsgeld paid by the federal office, in total at most | EUR 210 | § 19(2) MuSchG: "jedoch insgesamt höchstens 210 Euro" |

### Parental Leave (Elternzeit, BEEG)

| Entitlement | Detail |
| --- | --- |
| Duration | Until the child's third birthday, for each parent. Up to 24 months of it may be taken between the third and the eighth birthday. The mother's protection period after the birth counts toward it (§ 15(2) BEEG) |
| Work during the leave | Not more than 32 hours a week on monthly average (§ 15(4) BEEG) |
| Elterngeld | Paid by the state, not by the employer. Amounts in the table below. The parents together get twelve monthly amounts of basic Elterngeld, plus two partner months when one parent's earned income is reduced in two months. Basic Elterngeld can be drawn until the child is 14 months old. Both parents can draw basic Elterngeld at the same time in only one of the first twelve months, with the exceptions listed in § 4(6) BEEG, among them multiple and premature births (§ 4 BEEG) |
| ElterngeldPlus | One month of basic Elterngeld can be swapped for two months of ElterngeldPlus. ElterngeldPlus is at most half of the basic Elterngeld the parent would get with no income in the period. The law says "half" in words (§ 4a BEEG) |

See § 15 BEEG at https://www.gesetze-im-internet.de/beeg/__15.html and § 4 at https://www.gesetze-im-internet.de/beeg/__4.html and § 4a at https://www.gesetze-im-internet.de/beeg/__4a.html

**Elterngeld amounts**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/beeg/__2.html |
| Share of earned income before the birth, after tax and social contributions | 67% | § 2(1) BEEG: "Elterngeld wird in Höhe von 67 Prozent des Einkommens aus Erwerbstätigkeit vor der Geburt" |
| The share falls step by step to this floor when prior income was above the higher amount below | 65% | § 2(2) BEEG: "auf bis zu 65 Prozent" |
| The share rises step by step to this cap when prior income was below the lower amount below | 100% | "auf bis zu 100 Prozent" |
| Prior monthly income below which the share rises | EUR 1,000 | "geringer als 1 000 Euro war" |
| Prior monthly income above which the share falls | EUR 1,200 | "höher als 1 200 Euro war" |
| Highest monthly Elterngeld | EUR 1,800 | "bis zu einem Höchstbetrag von 1 800 Euro monatlich" |
| Lowest monthly Elterngeld | EUR 300 | § 2(4) BEEG: "Elterngeld wird mindestens in Höhe von 300 Euro gezahlt" |
| Highest prior income that counts when the parent works part time during the period | EUR 2,770 | § 2(3) BEEG: "höchstens der Betrag von 2 770 Euro anzusetzen" |

**Who gets no Elterngeld**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/beeg/__1.html |
| No claim when taxable income in the last completed assessment period before the birth was above this. For two entitled persons their incomes are added and tested against the same amount | EUR 175,000 | § 1(8) BEEG: "in Höhe von mehr als 175 000 Euro erzielt hat" |

### 13th Month / Christmas Bonus

No statutory obligation. A 13th salary or Christmas bonus (Weihnachtsgeld) rests on the collective agreement or the employment contract. No official page prints a typical amount, so none is stated. In payroll a bonus is one-off pay: wage tax by the yearly method (Section 2) and contributions under the one-off pay rule (Section 3).

## Section 7: Payslip Requirements

German employers must give an itemised payslip (Entgeltabrechnung, Lohnabrechnung) in text form when pay is paid. It must show at least the pay period and how the pay is made up: kind and amount of surcharges, allowances and other pay, and kind and amount of deductions, part payments and advances. No new payslip is needed when nothing has changed since the last proper one. See § 108 GewO at https://www.gesetze-im-internet.de/gewo/__108.html

### Mandatory Payslip Fields

The Entgeltbescheinigungsverordnung (EBV) lists what a pay certificate under § 108(3) GewO must contain. Employees get this certificate in text form for every pay period, together with the pay settlement. The duty falls away when nothing has changed since the last pay period, or only the period itself has changed (§ 2(1) EBV). See § 1 EBV at https://www.gesetze-im-internet.de/entgbv/__1.html and § 2 EBV at https://www.gesetze-im-internet.de/entgbv/__2.html

| Field | Required |
| --- | --- |
| Employer name and address | Yes |
| Employee name, address and date of birth | Yes |
| Employee's pension insurance number | Yes |
| Start date of the job, and the end date on the last payslip | Yes |
| Pay period, with the number of tax days and social insurance days in it | Yes |
| Steuerklasse with any factor, number of child allowances, Kirchensteuermerkmale, any tax allowance or add-back, and the tax identification number | Yes |
| Contribution group key (Beitragsgruppenschlüssel) and the health fund that collects the contributions | Yes |
| Care insurance code: 0 for the childless surcharge, 1 to 5 for the number of children that count, and a code for proven parenthood | Yes |
| Note that the job is in the transition band, or is one of several jobs, where that is so | Yes |
| Every kind of pay and deduction by name and amount, saying whether it is regular or one-off and whether it counts for tax gross, social insurance gross and total gross | Yes |
| Taxable pay, social insurance gross (per branch if different), total gross (Bruttolohn), and flat-taxed pay by legal basis | Yes |
| Lohnsteuer, Kirchensteuer and Solidaritätszuschlag withheld, split between regular and one-off pay | Yes |
| Employee SV contributions to health, pension and care insurance and to unemployment insurance | Yes |
| Nettolohn (net pay) as total gross less the statutory deductions | Yes |
| Employer subsidy to voluntary or private health and care insurance, and the employer share to a professional pension scheme | Yes |
| Other pay, deductions and set-offs that do not change a gross figure, such as Vorschüsse, Pfändungen, VWL and bAV, each by kind | Yes |
| Amount paid out | Yes |
| Employer SV contributions | Not on the EBV list. Often shown for information |
| Zusatzbeitrag rate (KV), hours worked | Not on the EBV list, although older material calls them mandatory |

### Delivery

- The law asks for text form (§ 108(1) GewO). It does not say "paper or secure electronic format".
- **Retention, tax.** Wage accounts (Lohnkonten) are kept until the end of the sixth calendar year after the last wage payment entered. See § 41(1) sentence 9 EStG at https://www.gesetze-im-internet.de/estg/__41.html
- **Retention, social insurance.** Pay records, contribution statements and contribution calculations are kept until the end of the calendar year after the last audit. Older material says ten years; the law ties the period to the audit. See § 28f(1) SGB IV at https://www.gesetze-im-internet.de/sgb_4/__28f.html The pension insurer audits at least every four years: § 28p SGB IV at https://www.gesetze-im-internet.de/sgb_4/__28p.html
- **Records abroad.** Pay records must be kept in Germany and in German. An employer with no seat in Germany must appoint an authorised person in Germany for this (§ 28f(1) and (1b) SGB IV).

## Section 8: Filing Obligations

### Monthly

| Obligation | Deadline | To Whom |
| --- | --- | --- |
| Lohnsteuer-Anmeldung (wage tax return) and payment | By the tenth day after the end of each return period. The period is the month unless the limits below allow the quarter or the year | Betriebsstättenfinanzamt, sent electronically by the official data set (ELSTER) |
| SV-Beitragsnachweis (contribution statement) | Two working days before the contributions fall due | The employee's Krankenkasse as Einzugsstelle, by data transfer |
| SV payment | The expected contribution debt is due at the latest on the third-last bank working day of the month in which the work was done. Any rest is due on the third-last bank working day of the next month. The employer may instead pay the amount of the month before and settle the rest the next month | Krankenkasse |
| DEÜV-Meldungen (social insurance notifications) | Start of a job: with the first payroll run after it, at the latest within six weeks. Other events such as end of the job, breaks in pay, one-off pay and changes of fund have their own notifications | The Krankenkasse as Einzugsstelle |
| Sofortmeldung | At the latest when work starts, in the sectors the law lists, among them building, hotels and restaurants, passenger and goods transport, cleaning, meat, security, and hairdressing and cosmetics | Data centre of the pension insurance |

- **Corrections.** Older material puts the payment on the fifth-last and the statement on the second-last working day of the month. The law says third-last bank working day for the payment (§ 23(1) SGB IV at https://www.gesetze-im-internet.de/sgb_4/__23.html) and two working days before the due date for the statement (§ 28f(3) SGB IV, link in Section 7).
- **Notifications.** See § 28a SGB IV at https://www.gesetze-im-internet.de/sgb_4/__28a.html and § 6 DEÜV at https://www.gesetze-im-internet.de/de_v/__6.html

**How often the wage tax return is due**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__41a.html |
| Wage tax of the previous calendar year up to which one return per year is enough. Not to be confused with the staff discount allowance in § 8(3) EStG, which is the same number | EUR 1,080 | § 41a(2) EStG: "für das vorangegangene Kalenderjahr nicht mehr als 1 080 Euro betragen hat" |
| Wage tax of the previous calendar year up to which the return is quarterly. Above it the return is monthly | EUR 5,000 | "aber nicht mehr als 5 000 Euro betragen hat" |

A business that did not exist for the whole previous year scales its wage tax up to a year. A new business uses the wage tax of its first full month, scaled up to a year (§ 41a(2) EStG).

### Annual

| Obligation | Deadline | Notes |
| --- | --- | --- |
| Lohnsteuerbescheinigung | Sent electronically by the last day of February of the following year | The employer closes the wage account at year end or when the job ends. The employee gets a printout or electronic access. § 41b EStG with § 93c(1) no. 1 AO |
| Jahresmeldung (SV annual notification) | With the first payroll run of the new year, at the latest by 15 February | For every employee in insured employment on 31 December. To the Krankenkasse. § 10 DEÜV |
| Jahresmeldung zur Unfallversicherung | By 16 February of the following year | Pay subject to accident insurance, by hazard tariff position. § 28a(2a) SGB IV |
| Lohnnachweis zur Unfallversicherung | By 16 February of the following year | The employer's statement of pay and hours worked, sent electronically to the accident insurer. It is separate from the per-employee notification in the row above. § 165(1) SGB VII with § 99(1) SGB IV |
| Lohnsteuer-Jahresausgleich (employer) | At the earliest with the last pay period that ends in the year, at the latest with the pay period that ends in February of the following year | The employer may do it for employees who worked for it all year. It must do it when it has at least ten employees on 31 December. It is barred in the cases listed in § 42b(1) EStG, among them class V or VI in the year, class II, III or IV for part of the year, a tax allowance or the factor method, and short-time work or maternity top-up pay in the year. Older material calls it optional and leaves out the ten-employee rule |

See § 41b EStG at https://www.gesetze-im-internet.de/estg/__41b.html and § 93c AO at https://www.gesetze-im-internet.de/ao_1977/__93c.html and § 10 DEÜV at https://www.gesetze-im-internet.de/de_v/__10.html and § 42b EStG at https://www.gesetze-im-internet.de/estg/__42b.html

### Employee Income Tax Return

| Scenario | Deadline |
| --- | --- |
| Mandatory filers | Seven months after the end of the calendar year, so 31 July of the following year (§ 149(2) AO) |
| With Steuerberater | The last day of February of the second year after the tax year (§ 149(3) AO). Older material says 31 December of the following year, which is not the current law. The tax office may ask for the return earlier |
| Voluntary filers | Within the four-year assessment period (§ 169(2) AO) |

See § 149 AO at https://www.gesetze-im-internet.de/ao_1977/__149.html and § 169 AO at https://www.gesetze-im-internet.de/ao_1977/__169.html

**One of the tests that make a return mandatory**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__46.html |
| Other income with no wage tax withheld, or income replacements under the progression clause, above this amount per year | EUR 410 | § 46(2) no. 1 EStG: "jeweils mehr als 410 Euro beträgt" |

Other mandatory cases in § 46(2) EStG: wages from several employers side by side; both spouses earned wages and one was taxed in class V or VI, or class IV with the factor; a tax allowance was used and pay was above the amounts the law names.

## Section 9: Common Payroll Patterns

### Typical Bank Statement Descriptions (Salary Credits)

| Pattern | Classification |
| --- | --- |
| GEHALT, LOHN, ENTGELT, NETTOBEZUG | Net salary payment |
| NACHZAHLUNG GEHALT | Salary back-payment (the one-off pay rules may apply) |
| WEIHNACHTSGELD, 13. GEHALT | Christmas bonus or 13th salary |
| URLAUBSGELD | Holiday bonus |
| ABFINDUNG | Severance. The relief for extraordinary income (§ 34 EStG, Fünftelregelung) is claimed in the employee's own tax return. The current § 39b EStG holds no such relief for withholding |
| ELTERNGELD | Parental allowance, paid by the state and not by the employer |
| KRANKENGELD | Sick pay from the Krankenkasse. Not wages, but it raises the tax rate on other income (progression clause) |

See § 34 EStG at https://www.gesetze-im-internet.de/estg/__34.html and, for the progression clause, § 32b EStG at https://www.gesetze-im-internet.de/estg/__32b.html Elterngeld and Mutterschaftsgeld fall under the same clause.

### Typical Employer Debit Patterns

| Pattern | Classification |
| --- | --- |
| FINANZAMT LST, LOHNSTEUER | Wage tax, solidarity surcharge and church tax paid over |
| (name of the Krankenkasse) SV-BEITRAG | Social insurance contributions |
| BG BEITRAG, BERUFSGENOSSENSCHAFT | Accident insurance contribution |
| UMLAGE U1 U2 | Sick pay and maternity levies |
| MINIJOB-ZENTRALE, KNAPPSCHAFT-BAHN-SEE | Minijob contributions, levies and the uniform flat tax |

## Section 10: Interaction with Other Guides

| Scenario | Guide to use |
| --- | --- |
| Employee payroll (Lohnsteuer and social insurance) | **This Guide (`germany-payroll`)** |
| Detailed PAP formula and worked examples | `de-payroll` |
| Self-employed income tax (Einkommensteuer) | `de-income-tax` |
| Self-employed social contributions | `de-social-contributions` |
| Gewerbesteuer (trade tax) | `de-trade-tax` |
| Umsatzsteuer (VAT) | `germany-vat-return` |
| Bookkeeping | `germany-bookkeeping` |

### Key Handoff Points

- **Payroll to Bookkeeping:** Gross wages and employer social insurance are P&L expenses. Wage tax, solidarity surcharge, church tax and employee contributions are payroll liabilities (Verbindlichkeiten) until paid over. Employer contributions are booked to Sozialaufwendungen.
- **Payroll to Income Tax:** The Lohnsteuerbescheinigung feeds the employee's Einkommensteuererklärung. The PAP computation in `de-payroll` is the reference for checking withholding amounts.
- **Payroll to SV:** Beitragsnachweise and DEÜV-Meldungen must agree with the payslip amounts. The Krankenkasse collects all four branches centrally.

## PROHIBITIONS

- **PAP formula required.** NEVER compute Lohnsteuer without the ministry's PAP formula. Simple bracket percentages are wrong.
- **BBG confusion.** NEVER confuse the health and care ceiling with the pension and unemployment ceiling. Both are in Section 3.
- **Ceiling and threshold confusion.** NEVER treat the JAEG as a ceiling. It decides who may leave statutory health insurance, not how much is charged.
- **Childless PV surcharge misapplication.** NEVER apply the childless care surcharge to employees whose parenthood is proven or already known to the employer, or to employees who have not yet turned 23. Proof that does not come through the automated data procedure of § 55a SGB XI and is given later than six months after the birth works only from the month after it is given (§ 55(3a) SGB XI).
- **SV above BBG.** NEVER charge contributions on pay above the Beitragsbemessungsgrenze.
- **Sachsen PV exception.** NEVER omit the Saxony split of care insurance.
- **Minijob standard payroll treatment.** NEVER treat a Minijob (pay within the limit in Section 5) as standard payroll. Flat contributions go to the Minijob-Zentrale.
- **Kirchensteuer rate assumption.** NEVER assume one church tax rate everywhere. The rate depends on the federal state (Section 2).
- **Invented rates.** NEVER use a general U1, U2 or accident insurance rate. Each health fund and each accident insurer sets its own.
- **Employer-only costs omission.** NEVER forget employer-only costs (Umlagen, accident insurance, Insolvenzgeldumlage) when working out total cost.
- **Payslip field omission.** NEVER issue a payslip missing what § 108 GewO requires.
- **Definitive presentation prohibition.** NEVER present payroll computations as definitive. Direct the user to a Steuerberater or Lohnbuchhalter for sign-off.

## The method, step by step

1. When a job starts, get the employee's tax identification number and date of birth, ask whether it is the first or a further job, and retrieve the ELStAM from the BZSt (§ 39e EStG). As long as the employee culpably withholds the number and the date of birth, the employer must use class VI. If the data cannot be retrieved for technical reasons, the expected data may be used for at most three calendar months (§ 39c(1) EStG). https://www.gesetze-im-internet.de/estg/__39e.html and https://www.gesetze-im-internet.de/estg/__39c.html
2. Decide the social insurance status before the first payslip: ordinary job, Minijob, short-term job, transition band, apprentice, or pay above the JAEG. The tests are in § 8 and § 20 SGB IV and § 6 SGB V. https://www.gesetze-im-internet.de/sgb_4/__8.html
3. Register the job with the health fund as Einzugsstelle, or with the Minijob-Zentrale for a Minijob: with the first payroll run, at the latest within six weeks (§ 6 DEÜV). In the listed sectors send the Sofortmeldung at the latest when work starts (§ 28a(4) SGB IV). https://www.gesetze-im-internet.de/sgb_4/__28a.html
4. Check the hourly pay against the minimum wage in Section 5 and keep working time records where § 17 MiLoG demands them. https://www.gesetze-im-internet.de/milog/__17.html
5. Work out the wage tax of the pay period with the ministry's programme plan for the year (§ 39b EStG), then the solidarity surcharge (§ 3 and § 4 SolzG) and, if the ELStAM say so, the church tax. https://www.gesetze-im-internet.de/estg/__39b.html
6. Work out contributions branch by branch, each up to its ceiling, with the health fund's own additional rate, the care share that fits the employee's children and age, and the Saxony split where it applies (Section 3). Deduct only the employee share. A missed deduction can be made up only in the next three wage payments (§ 28g SGB IV). https://www.gesetze-im-internet.de/sgb_4/__28g.html
7. Add the employer-only levies: U1 if the employer has not more than 30 employees, U2, the insolvency levy (§ 7 AAG, § 360 SGB III). https://www.gesetze-im-internet.de/aufag/__7.html
8. Issue the payslip with the contents of § 108 GewO and § 1 EBV. https://www.gesetze-im-internet.de/entgbv/__1.html
9. Send the contribution statement two working days before the due date and pay the expected contributions by the third-last bank working day of the month (§ 28f(3) and § 23(1) SGB IV). https://www.gesetze-im-internet.de/sgb_4/__23.html
10. Send the Lohnsteuer-Anmeldung and pay the wage tax by the tenth day after the return period (§ 41a EStG). https://www.gesetze-im-internet.de/estg/__41a.html
11. At year end close the wage accounts, run the employer's yearly adjustment where § 42b EStG demands or allows it, send the Lohnsteuerbescheinigung by the last day of February (§ 41b EStG), the Jahresmeldung by 15 February (§ 10 DEÜV) and the accident insurance notification by 16 February (§ 28a(2a) SGB IV). https://www.gesetze-im-internet.de/estg/__41b.html
12. Keep the wage accounts and pay records for the periods in Section 7. https://www.gesetze-im-internet.de/estg/__41.html

If step 2 is skipped, every later step can be wrong: a Minijob run as ordinary payroll pays the wrong body at the wrong rates.

## Ask the client first

- What kind of job is it: ordinary employment, Minijob, short-term job, apprenticeship, working student? What is the regular monthly pay, and does the employee have other jobs?
- In which federal state is the workplace? Saxony changes the care insurance split, and the state decides the church tax rate.
- Which health fund is the employee in, and what is its additional rate? Or is the employee privately or voluntarily insured because pay is above the JAEG?
- Does the employee have children? How many are under 25, and is there proof of parenthood? Is the employee 23 or older?
- How many employees does the employer have as a rule, apprentices not counted? That decides U1.
- Is there one-off pay in the period (bonus, Christmas pay, severance), or pay for night, Sunday or public holiday work?

## When to refuse or refer

- The exact wage tax for a pay period. It needs the programme plan of the year in certified payroll software. See `de-payroll` for the formula.
- A health fund's own additional rate, and any U1 or U2 rate for ordinary employees. Each health fund sets its own; ask the fund.
- Accident insurance contributions. The accident insurer (Berufsgenossenschaft) sets them by hazard class after the year.
- Minijobs in private households (Haushaltsscheck procedure): other rates, other procedure.
- Miners' pension scheme, seafarers, and members of professional pension schemes (berufsständische Versorgung).
- Short-time work pay (Kurzarbeitergeld), partial retirement (Altersteilzeit) and working time accounts (Wertguthaben).
- Company pension schemes, company cars, benefits in kind and flat-rate wage tax on benefits (§ 37b, § 40 and § 40b EStG). They are outside this Guide.
- Cross-border cases: postings, A1 certificates, tax treaties, cross-border commuters, employees with limited tax liability.
- Managing directors who hold shares in their company and family members working in the business: whether they are employees at all for social insurance needs a status decision.
- Severance pay, and any employment law question on notice, leave disputes or collective agreements.
- The exact church tax rate for an employee. It rests on state church tax rules, which are not on the federal pages.

## Sources


- EStG § 3 no. 21 (tax-free pay after the standard retirement age): https://www.gesetze-im-internet.de/estg/__3.html
- EStG § 24b, § 32a, § 32b, § 34: https://www.gesetze-im-internet.de/estg/__24b.html and https://www.gesetze-im-internet.de/estg/__32a.html and https://www.gesetze-im-internet.de/estg/__32b.html and https://www.gesetze-im-internet.de/estg/__34.html
- EStG § 3b (tax-free surcharges): https://www.gesetze-im-internet.de/estg/__3b.html
- EStG § 38, § 38b, § 39b, § 39c, § 39e, § 39f (withholding, classes, computation, missing data, ELStAM, factor): https://www.gesetze-im-internet.de/estg/__38.html and https://www.gesetze-im-internet.de/estg/__38b.html and https://www.gesetze-im-internet.de/estg/__39b.html and https://www.gesetze-im-internet.de/estg/__39c.html and https://www.gesetze-im-internet.de/estg/__39e.html and https://www.gesetze-im-internet.de/estg/__39f.html
- EStG § 40a (flat tax for marginal and short-term jobs): https://www.gesetze-im-internet.de/estg/__40a.html
- EStG § 41, § 41a, § 41b, § 42b, § 42d, § 46: https://www.gesetze-im-internet.de/estg/__41.html and https://www.gesetze-im-internet.de/estg/__41a.html and https://www.gesetze-im-internet.de/estg/__41b.html and https://www.gesetze-im-internet.de/estg/__42b.html and https://www.gesetze-im-internet.de/estg/__42d.html and https://www.gesetze-im-internet.de/estg/__46.html
- SolzG § 3, § 4, § 6: https://www.gesetze-im-internet.de/solzg_1995/__3.html and https://www.gesetze-im-internet.de/solzg_1995/__4.html and https://www.gesetze-im-internet.de/solzg_1995/__6.html
- AO § 93c, § 149, § 169: https://www.gesetze-im-internet.de/ao_1977/__93c.html and https://www.gesetze-im-internet.de/ao_1977/__149.html and https://www.gesetze-im-internet.de/ao_1977/__169.html
- Finance ministry, programme plans for wage tax 2026, letter of 12 November 2025: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026.html and annex 1 at https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026-anlage-1.pdf?__blob=publicationFile&v=2
- Finance ministry, tax booklet (Steuern von A bis Z), 2025 edition: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9
- Federal Central Tax Office, sample text on church tax: https://www.bzst.de/SharedDocs/Downloads/DE/KiStA/Widerspruch_Mustertext.pdf?__blob=publicationFile&v=10
- SGB IV § 8, § 20, § 23, § 23a, § 28a, § 28f, § 28g, § 28h, § 28i, § 28p, § 99: https://www.gesetze-im-internet.de/sgb_4/__8.html and https://www.gesetze-im-internet.de/sgb_4/__20.html and https://www.gesetze-im-internet.de/sgb_4/__23.html and https://www.gesetze-im-internet.de/sgb_4/__23a.html and https://www.gesetze-im-internet.de/sgb_4/__28a.html and https://www.gesetze-im-internet.de/sgb_4/__28f.html and https://www.gesetze-im-internet.de/sgb_4/__28g.html and https://www.gesetze-im-internet.de/sgb_4/__28h.html and https://www.gesetze-im-internet.de/sgb_4/__28i.html and https://www.gesetze-im-internet.de/sgb_4/__28p.html and https://www.gesetze-im-internet.de/sgb_4/__99.html
- DEÜV § 6, § 10 (notifications): https://www.gesetze-im-internet.de/de_v/__6.html and https://www.gesetze-im-internet.de/de_v/__10.html
- SGB III § 341, § 360: https://www.gesetze-im-internet.de/sgb_3/__341.html and https://www.gesetze-im-internet.de/sgb_3/__360.html
- SGB V § 6, § 24i, § 47, § 48, § 241, § 249, § 257: https://www.gesetze-im-internet.de/sgb_5/__6.html and https://www.gesetze-im-internet.de/sgb_5/__24i.html and https://www.gesetze-im-internet.de/sgb_5/__47.html and https://www.gesetze-im-internet.de/sgb_5/__48.html and https://www.gesetze-im-internet.de/sgb_5/__241.html and https://www.gesetze-im-internet.de/sgb_5/__249.html and https://www.gesetze-im-internet.de/sgb_5/__257.html
- SGB VII § 150, § 165 (accident insurance, who pays; the employer's yearly wage notice to the insurer): https://www.gesetze-im-internet.de/sgb_7/__150.html and https://www.gesetze-im-internet.de/sgb_7/__165.html
- SGB XI § 55 (care insurance: surcharge, reductions, proof; its base rate is stale): https://www.gesetze-im-internet.de/sgb_11/__55.html
- AAG § 1, § 7 (levies U1 and U2): https://www.gesetze-im-internet.de/aufag/__1.html and https://www.gesetze-im-internet.de/aufag/__7.html
- SvEV § 1: https://www.gesetze-im-internet.de/svev/__1.html
- Social insurance figures 2026, regulation in the Federal Law Gazette: https://www.recht.bund.de/bgbl/1/2025/278/regelungstext.pdf?__blob=publicationFile&v=3
- Federal Government, contribution ceilings 2026: https://www.bundesregierung.de/breg-de/aktuelles/beitragsgemessungsgrenzen-2386514
- Federal Government, minimum wage and Minijob limit: https://www.bundesregierung.de/breg-de/aktuelles/mindestlohn-steigt-2391010
- Health ministry, contributions: https://www.bundesgesundheitsministerium.de/beitraege
- Health ministry, financing of long-term care insurance: https://www.bundesgesundheitsministerium.de/themen/pflege/online-ratgeber-pflege/die-pflegeversicherung/finanzierung
- National association of health funds, fact sheet of figures for 2026: https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf
- Pension insurance, figures for 2026: https://www.deutsche-rentenversicherung.de/KnappschaftBahnSee/DE/Aktuelles/Meldungen/2026/2026_01_02_Sozialversicherungsrechengroessen2026.html and https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026
- Minijob-Zentrale, contributions 2026: https://magazin.minijob-zentrale.de/minijob-beitraege-2026/ and https://www.minijob-zentrale.de/DE/fuer-gewerbetreibende/abgaben-und-steuern/detailseite
- Accident insurers (DGUV), how the contribution is worked out: https://www.dguv.de/de/ihr_partner/unternehmen/beitragsberechnung/index.jsp
- MiLoG § 2, § 17, § 22 and the Fifth Minimum Wage Adjustment Regulation: https://www.gesetze-im-internet.de/milog/__2.html and https://www.gesetze-im-internet.de/milog/__17.html and https://www.gesetze-im-internet.de/milog/__22.html and https://www.gesetze-im-internet.de/milov5/__1.html
- ArbZG § 3, BUrlG § 3 and § 7, EntgFG § 3, § 4 and § 5: https://www.gesetze-im-internet.de/arbzg/__3.html and https://www.gesetze-im-internet.de/burlg/__3.html and https://www.gesetze-im-internet.de/burlg/__7.html and https://www.gesetze-im-internet.de/entgfg/__3.html and https://www.gesetze-im-internet.de/entgfg/__4.html and https://www.gesetze-im-internet.de/entgfg/__5.html
- MuSchG § 3, § 19, § 20: https://www.gesetze-im-internet.de/muschg_2018/__3.html and https://www.gesetze-im-internet.de/muschg_2018/__19.html and https://www.gesetze-im-internet.de/muschg_2018/__20.html
- BEEG § 1, § 2, § 4, § 4a, § 15: https://www.gesetze-im-internet.de/beeg/__1.html and https://www.gesetze-im-internet.de/beeg/__2.html and https://www.gesetze-im-internet.de/beeg/__4.html and https://www.gesetze-im-internet.de/beeg/__4a.html and https://www.gesetze-im-internet.de/beeg/__15.html
- GewO § 108 and EBV § 1, § 2 (payslip): https://www.gesetze-im-internet.de/gewo/__108.html and https://www.gesetze-im-internet.de/entgbv/__1.html and https://www.gesetze-im-internet.de/entgbv/__2.html

## Disclaimer

This Guide and its outputs are provided for informational and computational purposes only and do not constitute tax, legal, or financial advice. Open Accountants and its contributors accept no liability for any errors, omissions, or outcomes arising from the use of this Guide. All outputs must be reviewed and signed off by a qualified professional (such as a Steuerberater or Lohnbuchhalter in Germany) before implementation.

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
