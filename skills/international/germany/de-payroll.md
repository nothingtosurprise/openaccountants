---
name: de-payroll
description: Use this skill whenever asked about German payroll tax (Lohnsteuer) computation for EMPLOYEES. Trigger on phrases like "Lohnsteuer", "Gehaltsabrechnung", "payslip Germany", "Steuerklasse", "Brutto Netto", "Solidaritaetszuschlag on wages", "Kirchensteuer on payroll", "Sozialversicherungsbeitraege employee", "Arbeitnehmeranteil", "Arbeitgeberanteil", "Beitragsbemessungsgrenze", "Lohnabrechnung", "Nettolohn", "payroll withholding Germany", "German wage tax", "Lohnsteuerklasse I II III IV V VI", or any question about computing employee payroll deductions in Germany. Covers Lohnsteuer (income tax withholding), Solidaritatszuschlag, Kirchensteuer, and all four branches of Sozialversicherung (RV, KV, PV, AV) from an employer/employee split perspective. This is SEPARATE from the self-employed income tax skill (de-income-tax.md). ALWAYS read this skill before computing any German employee payroll.
version: 1.0
jurisdiction: DE
tax_year: 2026
last_updated: 2026-09-19
review_status: pending_review
drafted_by: OpenAccountants
approved_by: pending
depends_on:
  - income-tax-workflow-base
category: international
tier: 2
license: AGPL-3.0-or-later (code) / OpenAccountants Guide License v1.0 (content)
---

# German payroll: wage tax and social insurance for employees (Lohnsteuer)

How a German employer works out an employee's payslip: wage tax (Lohnsteuer), solidarity surcharge, church tax, and the four social insurance branches with the split between employer and employee. It is for employers, payroll staff and employees who check a payslip. It does not cover the self-employed. Figures are for tax year 2026. Wage tax figures are read from the consolidated federal law pages and from the finance ministry's official wage tax program for 2026 (Programmablaufplan, final version of 12 November 2025). Social insurance figures come from the 2026 regulation in the Federal Law Gazette, the Federal Government, the health ministry, the pension insurer, the health funds' association and the Minijob-Zentrale. Three sources carry another date. The church tax range is from the finance ministry's tax booklet, 2025 edition, the latest one published. The health ministry's long-term care page states rates in force since 1 January 2025, and the health funds' fact sheet for 2026 prints the same rates. The end of the one-fifth relief in payroll is taken from the ministry letter of 22 November 2024 on the 2025 program.

## Germany Payroll Tax (Lohnsteuer): Employee Guide

Wage tax cannot be worked out from a rate table. The law makes the employer annualise the pay, take off fixed allowances and a lump sum for insurance, apply the income tax formula, and divide the result back to the pay period. The finance ministry publishes that routine each year as a program flow (the PAP). This Guide gives the 2026 constants and the order of the steps. It does not replace payroll software that implements the PAP.

## Section 1: Quick Reference

| Field | Value |
| --- | --- |
| Country | Germany (Bundesrepublik Deutschland) |
| Taxes | Lohnsteuer (LSt), Solidaritätszuschlag (SolZ), Kirchensteuer (KiSt, church members only) |
| Social contributions | Rentenversicherung (RV), Krankenversicherung (KV), Pflegeversicherung (PV), Arbeitslosenversicherung (AV) |
| Currency | EUR only |
| Pay period | Monthly (Monat), weekly (Woche), daily (Tag) or annual (Jahr), § 39b(2) EStG |
| Primary legislation | Einkommensteuergesetz (EStG) § 38 to § 42f; Solidaritätszuschlaggesetz (SolzG); SGB III, IV, V, VI, VII and XI; Aufwendungsausgleichsgesetz (AAG) |
| Computation source | BMF Programmablaufplan (PAP): the official program for machine wage tax, published by the Federal Ministry of Finance for each year under § 39b(6) EStG |
| Who owes, who withholds | The employee owes the wage tax. The employer withholds it at every wage payment (§ 38 EStG) and pays the total social insurance contribution (§ 28e SGB IV) |
| Community code | MarcelLehmann/Lohnsteuer and jenner/LstGen on GitHub implement the PAP. They are private projects, not official sources, and were not checked in this refresh |
| Ministry calculator | The finance ministry runs an online wage tax calculator at bmf-steuerrechner.de. That host is not on this Guide's list of linkable hosts, so it is named without a link |
| Contributor | Open Accountants Community |
| Validated by | Pending. Requires sign-off by a German Steuerberater |
| Validation date | Pending |
| Guide version | 2026 refresh |

### Grundfreibetrag and Tax Brackets (2026, from § 32a EStG and the BMF PAP of 12 November 2025)

**Income tax tariff 2026**

| Taxable amount for the year | Tax in this zone | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__32a.html |
| Up to EUR 12,348 | None. This is the Grundfreibetrag (GFB in the PAP) | § 32a(1) no. 1 EStG: "bis 12 348 Euro (Grundfreibetrag)" |
| EUR 12,349 to EUR 17,799 | Formula, first progressive zone | § 32a(1) no. 2 EStG: "von 12 349 Euro bis 17 799 Euro" |
| EUR 17,800 to EUR 69,878 | Formula, second progressive zone | § 32a(1) no. 3 EStG: "von 17 800 Euro bis 69 878 Euro" |
| EUR 69,879 to EUR 277,825 | The factor 0.42 on the whole amount, less a fixed sum | § 32a(1) no. 4 EStG: "von 69 879 Euro bis 277 825 Euro: 0,42" |
| From EUR 277,826 | The factor 0.45 on the whole amount, less a fixed sum | § 32a(1) no. 5 EStG: "von 277 826 Euro an: 0,45" |

- **What the zones measure.** They apply to the taxable amount for the year (zu versteuernder Jahresbetrag), not to gross pay. In payroll that is the annualised pay less the fixed allowances of the tax class and less the Vorsorgepauschale (Section 3). The statute is written for the assessment period 2026.
- **No percentage for the progressive zones.** The statute prints a formula for the two progressive zones and the factors 0.42 and 0.45 for the two upper zones. It prints no percentage for any zone, so this Guide states none. The live version of this Guide showed rough percentages for the zone edges; they were on no official page and are removed.
- **Splitting.** In tax class III the tax is twice the tax on half of the taxable amount (§ 32a(5) EStG).
- **Germany uses the BMF Programmablaufplan (PAP) formula, not simple bracket multiplication. The exact formula is in Section 3.**

### Solidaritatszuschlag (SolZ) on Lohnsteuer

**Rate and mitigation rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__4.html |
| Solidarity surcharge, charged on the wage tax and not on the pay | 5.5% | § 4 sentence 1 SolzG: "Der Solidaritätszuschlag beträgt 5,5 Prozent der Bemessungsgrundlage" |
| Mitigation rate: the surcharge is not more than this share of the difference between the base and the exemption limit | 11.9% | § 4 sentence 2 SolzG: "Er beträgt nicht mehr als 11,9 Prozent des Unterschiedsbetrages" |

**Exemption limit (Freigrenze) 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__3.html |
| Yearly limit on the base, tax classes I, II, IV, V and VI | EUR 20,350 | § 3(3) no. 2 SolzG: "in anderen Fällen 20 350 Euro übersteigt" |
| Yearly limit on the base, tax class III (splitting cases) | EUR 40,700 | § 3(3) no. 1 SolzG: "Einkommensteuergesetzes 40 700 Euro" |

- **What the limit is.** It is a limit on the wage tax, not on pay. If the base does not exceed the limit, no surcharge is withheld. Above the limit the surcharge is the lower of two amounts: the rate in the first table applied to the base, or the mitigation rate applied to the part of the base above the limit. So the surcharge rises gradually from the limit upward and does not jump.
- **The base is not the plain wage tax when there are children.** For running pay the base is the wage tax that results when the taxable amount is reduced by the child allowances: doubled in classes I, II and III, single in class IV, for each child counter in the wage tax data (§ 3(2a) SolzG). Child allowances do not reduce the wage tax itself during the year.
- **Pay periods.** The statute gives the limit per pay period as a fraction of the yearly limit: one twelfth for a month, seven three hundred and sixtieths for a week, one three hundred and sixtieth for a day (§ 3(4) SolzG). It prints no monthly amount, so none is stated here.
- **One-time payments (sonstige Bezüge).** Surcharge is withheld on the wage tax for a one-time payment only if the year's wage tax, worked out with the one-time payment and with the child allowances, exceeds the limit (§ 3(4a) SolzG). If it does, the full rate applies to that wage tax. The mitigation rate does not apply to one-time payments (§ 4 sentence 4 SolzG).

### Kirchensteuer (KiSt)

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Church tax, lower of the two state rates, charged on the wage tax | 8% | Ministry booklet, 2025 edition: "beträgt je nach Bundesland 8 oder 9 Prozent" |
| Church tax, higher of the two state rates, charged on the wage tax | 9% | Same sentence |

- **Which states.** The rate is set by the church tax decisions of each state, not by federal law. The federal tax office's sample text for banks says the rate is the lower one in Baden-Württemberg and Bavaria and the higher one in the other states. That text is written for church tax on investment income. See https://www.bzst.de/SharedDocs/Downloads/DE/KiStA/Widerspruch_Mustertext.pdf?__blob=publicationFile&v=10
- **Applied only if.** The employee is a member of a church that levies the tax. In the PAP the input R is above zero.
- **Bemessungsgrundlage.** The PAP output BK. It is the wage tax worked out with the child allowances, the same base rule as for the surcharge. See § 51a(2a) EStG at https://www.gesetze-im-internet.de/estg/__51a.html
- **Not on the federal pages.** Caps, minimum amounts and the rules for spouses of different faiths are state law. This Guide does not state them.

### Steuerklassen (Tax Classes)

| Class | Who (§ 38b(1) EStG) | Tariff | Fixed amounts the 2026 PAP builds in |
| --- | --- | --- | --- |
| I | Single. Also married, widowed or divorced employees who do not meet the conditions of class III or IV. Also employees with limited tax liability | Grundtarif (KZTAB = 1) | ANP, SAP, Vorsorgepauschale |
| II | As class I, when the relief for single parents applies | Grundtarif (KZTAB = 1) | ANP, SAP, EFA, Vorsorgepauschale |
| III | Married, both spouses resident and not permanently separated, and the other spouse is put in class V on the application of both. Also a widowed employee for the calendar year after the death, and the case of a dissolved marriage in § 38b(1) no. 3(c) | Splittingverfahren (KZTAB = 2) | ANP, SAP, Vorsorgepauschale |
| IV | Married, both spouses resident and not permanently separated. This is the class for married employees unless both apply for III and V. It also applies when one spouse has no wages. On application of both, class IV with a factor (§ 39f EStG) | Grundtarif (KZTAB = 1) | ANP, SAP, Vorsorgepauschale |
| V | The spouse of a class III employee, on the application of both | Special method of § 39b(2) sentence 7 EStG | ANP, SAP, Vorsorgepauschale |
| VI | Second and every further employment. Also when the employee is at fault for not giving the identification number and date of birth (§ 39c EStG) | Special method of § 39b(2) sentence 7 EStG | No ANP, no SAP. Vorsorgepauschale only for pension, statutory health and care |

See § 38b EStG at https://www.gesetze-im-internet.de/estg/__38b.html and § 39b(2) sentence 5 EStG at https://www.gesetze-im-internet.de/estg/__39b.html

**Employee lump sum (ANP)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__9a.html |
| Arbeitnehmer-Pauschbetrag, per year, classes I to V | EUR 1,230 | § 9a sentence 1 no. 1(a) EStG: "ein Arbeitnehmer-Pauschbetrag von 1 230 Euro" |

**Special expenses lump sum (SAP)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__10c.html |
| Sonderausgaben-Pauschbetrag, per year, classes I to V | EUR 36 | § 10c sentence 1 EStG: "wird ein Pauschbetrag von 36 Euro abgezogen (Sonderausgaben-Pauschbetrag)" |

**Relief for single parents (EFA)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__24b.html |
| Entlastungsbetrag für Alleinerziehende, per year, class II. Class II carries the amount for one child only | EUR 4,260 | § 24b(2) sentence 1 EStG: "beträgt der Entlastungsbetrag im Kalenderjahr 4 260 Euro" |

**Child allowances in the PAP (KFB)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026-anlage-1.pdf?__blob=publicationFile&v=2 |
| Amount per child counter (ZKF) in classes I, II and III | EUR 9,756 | PAP for 2026, section 1: "des Kinderfreibetrags (Anhebung auf 4 878 Euro bzw. 9.756 Euro)" |
| Amount per child counter (ZKF) in class IV | EUR 4,878 | Same sentence. Classes V and VI carry no child allowance |

- **Key abbreviations.** ANP = Arbeitnehmer-Pauschbetrag (employee lump sum); SAP = Sonderausgaben-Pauschbetrag; KFB = the sum of the child allowances; EFA = Entlastungsbetrag für Alleinerziehende; KZTAB = tariff marker (1 = Grundtarif, 2 = Splittingverfahren); ZKF = number of child allowance counters in the wage tax data, with one decimal place.
- **The child allowance does not lower the wage tax.** The PAP uses KFB only for a second calculation that gives the base for the solidarity surcharge and the church tax. The wage tax itself is worked out without it. The live version of this Guide listed KFB with the fixed amounts of each tax class and used it in a worked example as if it lowered the wage tax. It does not.
- **What the PAP amounts are.** In classes I, II and III the amount is the doubled child allowance plus the doubled allowance for care, upbringing and education of § 32(6) sentence 1 EStG. In class IV it is the single amounts (§ 51a(2a) sentence 1 EStG). A counter of 0.5 is used when the employee is entitled to one parent's share only (§ 38b(2) EStG).
- **Single parents with more than one child.** The increase for each further child in § 24b(2) sentence 2 EStG is not part of class II. It is one of the amounts the tax office can set as an allowance in the wage tax data (§ 39a(1) no. 4a EStG). See https://www.gesetze-im-internet.de/estg/__39a.html
- **Factor method.** Spouses in class IV can apply for a factor below 1. The employer then applies class IV and multiplies the wage tax by the factor (§ 39f EStG). See https://www.gesetze-im-internet.de/estg/__39f.html

### Social Security Rates (2026)

**Pension insurance: the full rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026 |
| General pension insurance, full rate, same in west and east | 18.6% | Pension insurer: "Dieser beträgt 2026 weiterhin 18,6 Prozent" |

**Pension and unemployment insurance: the two halves**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/KnappschaftBahnSee/DE/Aktuelles/Meldungen/2026/2026_01_02_Sozialversicherungsrechengroessen2026.html |
| Pension insurance, employee share and employer share, each | 9.3% | "Der Arbeitnehmer- als auch der Arbeitgeberanteil beträgt jeweils 9,3 Prozent" |
| Unemployment insurance, employee share and employer share, each | 1.3% | "Der Arbeitnehmer- als auch der Arbeitgeberanteil hat eine Höhe von 1,3 Prozent" |

**Unemployment insurance: the full rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_3/__341.html |
| Unemployment insurance (Arbeitsförderung), full rate | 2.6% | § 341(2) SGB III: "Der Beitragssatz beträgt 2,6 Prozent" |

**Health insurance: the general rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_5/__241.html |
| Statutory health insurance, general rate, without the fund's additional rate | 14.6% | § 241 SGB V: "Der allgemeine Beitragssatz beträgt 14,6 Prozent der beitragspflichtigen Einnahmen" |

**Health insurance: the average additional rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesgesundheitsministerium.de/beitraege |
| Average additional rate (durchschnittlicher Zusatzbeitragssatz) set by the health ministry. It is not what a given fund charges | 2.9% | Health ministry: "Für das Jahr 2026 beträgt der durchschnittliche Zusatzbeitragssatz 2,9 Prozent" |

**Summary of the four branches.** Every value in this summary is proven in the source tables above or in the care table below.

| Branch | German name | Full rate | Employee (AN) | Employer (AG) |
| --- | --- | --- | --- | --- |
| Pension | Rentenversicherung (RV) | 18.6% | 9.3% | 9.3% |
| Health | Krankenversicherung (KV) | 14.6% plus the additional rate of the employee's own fund | Half of both | Half of both |
| Care | Pflegeversicherung (PV) | 3.6% | See the care table | See the care table |
| Unemployment | Arbeitslosenversicherung (AV) | 2.6% | 1.3% | 1.3% |

- **Health insurance halves.** Employer and employee each bear half of the general rate and half of the fund's additional rate. The health ministry says so in words ("jeweils zur Hälfte") on the page in the table above, and § 249(1) SGB V says the same. No official page read prints the half as a number, so this Guide does not print one. See https://www.gesetze-im-internet.de/sgb_5/__249.html
- **The additional rate is the fund's own.** Each health fund sets its own additional rate. The average rate in the table applies only to some groups; the health ministry's page gives examples, among them apprentices paid up to the apprentice limit and recipients of basic income support. For everyone else it is only a planning value.
- **Never add halves.** The live version of this Guide printed a total health rate that it had built by adding the average additional rate to the general rate. No official page prints that total. It is removed.
- **Who is not covered by these rates.** Minijobs and the transition band (Section 9), the miners' pension scheme, civil servants, and employees who are exempt from a branch.

### Pflegeversicherung Detail (2026)

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesgesundheitsministerium.de/themen/pflege/online-ratgeber-pflege/die-pflegeversicherung/finanzierung |
| Full rate, member with one child | 3.6% | "Seit dem 1. Januar 2025 beträgt der Beitragssatz 3,6 Prozent der beitragspflichtigen Einnahmen" |
| Full rate, childless member | 4.2% | "bei Kinderlosen sind es 4,2 Prozent" |
| Surcharge for childless members, borne by the employee alone | 0.6% | "Beitragszuschlag für Kinderlose in Höhe von 0,6 Prozent der beitragspflichtigen Einnahmen" |
| Employer share, and employee share without surcharge or reductions, every state except Saxony | 1.8% | "grundsätzlich zur Hälfte, also jeweils 1,8 Prozent" |
| Employee share, childless, every state except Saxony (PVZ = 1) | 2.4% | The page's table: "Übrige Bundesländer 1,8 % 2,4 % 1,8 %" |
| Full rate, member with 2 children under 25 (PVA = 1) | 3.35% | "Mitglieder mit 2 Kindern = 3,35 % (Arbeitnehmer-Anteil: 1,55 %)" |
| Employee share, 2 children under 25, outside Saxony | 1.55% | Same line |
| Full rate, member with 3 children under 25 (PVA = 2) | 3.10% | "Mitglieder mit 3 Kindern = 3,10 % (Arbeitnehmer-Anteil: 1,3 %)" |
| Employee share, 3 children under 25, outside Saxony | 1.3% | Same line |
| Full rate, member with 4 children under 25 (PVA = 3) | 2.85% | "Mitglieder mit 4 Kindern = 2,85 % (Arbeitnehmer-Anteil: 1,05 %)" |
| Employee share, 4 children under 25, outside Saxony | 1.05% | Same line |
| Full rate, member with 5 or more children under 25 (PVA = 4) | 2.60% | "Mitglieder mit 5 und mehr Kindern = 2,60 % (Arbeitnehmer-Anteil: 0,8 %)" |
| Employee share, 5 or more children under 25, outside Saxony | 0.8% | Same line |
| Saxony (PVS = 1): employee share without surcharge or reductions | 2.3% | "2,3 Prozent auf die Beschäftigten und 1,3 Prozent auf die Arbeitgeber" |
| Saxony: employer share, whatever the number of children | 1.3% | Same sentence |
| Saxony: employee share, childless | 2.9% | The page's table: "Bundesland Sachsen 2,3 % 2,9 % 1,3 %" |
| Saxony: amount by which every employee share in this table is higher | 0.5% | "Erhöhung des Arbeitnehmeranteils jeweils um 0,5 % im Bundesland Sachsen" |

**Reduction per child, as the health funds print it**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf |
| Reduction of the care rate for each child from the second to the fifth, while that child is under 25 | 0.25% | Fact sheet for 2026: "Beitragsabschlag ab dem zweiten bis zum fünften Kind jeweils 0,25 %" |

- **Do not cite the statute for the rate.** § 55(1) SGB XI on the federal law page still prints an older rate, because the last rise was made by regulation. The rules around the rate below are read from § 55(3) SGB XI, which is current. See https://www.gesetze-im-internet.de/sgb_11/__55.html
- **Childless surcharge.** It starts after the end of the month in which the member turns 23. It is not charged to members born before 1 January 1940, to people doing military or civilian service, or to recipients of basic income support. Parents do not pay it; the health ministry's page marks the one-child rate as lifelong.
- **Reductions for children.** They run for the second to the fifth child, each until the end of the month in which that child turns 25. Children who have turned 25 do not count. Nothing is given for the first child or beyond the fifth. The reductions lower the employee share only. The employer share stays the same.
- **Proof.** Parenthood and the number of children under 25 must be proven to the office that pays the contributions over (beitragsabführende Stelle), unless it already has the data (§ 55(3a) SGB XI).
- **Sachsen PV adjustment.** Saxony kept a public holiday when care insurance was introduced, so the employee bears a larger part and the employer a smaller part. What counts is the place of employment, not where the employee lives (§ 58(3) SGB XI). See https://www.gesetze-im-internet.de/sgb_11/__58.html The live version of this Guide asked for "Sachsen residence"; that was the wrong test.

### Beitragsbemessungsgrenzen (Contribution Ceilings, 2026)

**Set by the 2026 regulation (Sozialversicherungsrechengrößen-Verordnung 2026)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.recht.bund.de/bgbl/1/2025/278/regelungstext.pdf?__blob=publicationFile&v=3 |
| Pension and unemployment insurance ceiling (RV-BBG and AV-BBG), per year | EUR 101,400 | "in der allgemeinen Rentenversicherung auf 101 400 Euro jährlich" |
| Pension and unemployment insurance ceiling, per month | EUR 8,450 | "umgerechnet auf den Monat ergeben sich 8 450 Euro" |
| General compulsory insurance threshold (JAEG, Versicherungspflichtgrenze), per year | EUR 77,400 | "für das Jahr 2026 auf 77 400 Euro festgesetzt" |
| General compulsory insurance threshold, per month | EUR 6,450 | "Umgerechnet auf den Monat ergeben sich 6 450 Euro" |
| Special compulsory insurance threshold, only for employees who were privately insured on 31 December 2002 because their pay was above the threshold of that day, per year | EUR 69,750 | "für das Jahr 2026 auf 69 750 Euro festgesetzt" |
| Special compulsory insurance threshold, per month | EUR 5,812.50 | "Umgerechnet auf den Monat ergeben sich 5 812,50 Euro" |

**Health and care ceiling, as the Federal Government prints it**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesregierung.de/breg-de/aktuelles/beitragsgemessungsgrenzen-2386514 |
| Health and care insurance ceiling (KV/PV-BBG), per year | EUR 69,750 | "Beitragsbemessungsgrenze 2026 auf jährlich 69.750 Euro beziehungsweise 5.812,50 Euro im Monat" |
| Health and care insurance ceiling, per month | EUR 5,812.50 | Same sentence |

- **Ceiling application rule.** Pay above a ceiling carries no contributions for that branch. There are two ceilings: one for pension and unemployment insurance, a lower one for health and care insurance.
- **One number, two rules.** In 2026 the health and care ceiling and the special compulsory insurance threshold are the same amount. They are different rules. The ceiling caps contributions. The threshold decides who may leave statutory health insurance.
- **What the general threshold does.** An employee whose regular yearly pay is above it is free of compulsory statutory health insurance and may insure privately or stay as a voluntary member. When pay rises above the threshold, compulsory insurance ends only at the end of that calendar year, and only if the pay is also above the threshold that applies from the start of the next year (§ 6(4) SGB V). It is not a contribution ceiling. See https://www.gesetze-im-internet.de/sgb_5/__6.html
- **West and east.** Each ceiling has one value for the whole country. The miners' pension scheme has its own higher ceiling and is outside this Guide.

### Conservative Defaults

| Ambiguity | Default |
| --- | --- |
| Unknown Steuerklasse | Steuerklasse I for an estimate. In real payroll the employer must use class VI while the employee is at fault for missing wage tax data (§ 39c EStG) |
| Unknown church membership | No Kirchensteuer (R = 0) |
| Unknown Zusatzbeitrag | For an estimate only, the average additional rate in the health table. Real payroll needs the rate of the employee's own fund: the PAP says the average rate is not relevant for the input KVZ |
| Unknown number of children | Childless surcharge (PVZ = 1) if the employee is 23 or older |
| Unknown KRV status | KRV = 0 (compulsorily insured in the statutory pension scheme) |
| Unknown ALV status | ALV = 0 (compulsorily insured in unemployment insurance) |
| Unknown Sachsen status | PVS = 0 (place of employment outside Saxony) |

## Section 2: Required Inputs and Refusal Catalogue

### Required Inputs

- **Minimum viable.** Gross pay for the period (Bruttolohn), Steuerklasse, and the pay period (monthly, weekly, daily or annual).
- **Recommended.** The additional rate of the employee's own Krankenkasse, number of children under 25 and the employee's age, church membership and the state of the workplace, any allowance (Freibetrag) or added amount (Hinzurechnungsbetrag) in the wage tax data, the insurance markers KRV, ALV and PKV, and whether the place of employment is in Saxony.
- **Ideal.** Full ELStAM data (electronic wage tax deduction data), the employment contract, the wage tax certificate (Lohnsteuerbescheinigung) of an earlier employer in the same year, and proof of children for the care insurance.

### Refusal Catalogue

- **R-DE-P-1: Self-employed / Freiberufler.** This Guide covers employee payroll (Lohnsteuer). Self-employed persons compute Einkommensteuer, not Lohnsteuer. Use `de-einkommensteuer-freelancer`.
- **R-DE-P-2: Mini-job (geringfugige Beschaftigung).** Jobs with regular pay up to the Minijob limit in Section 9 have flat employer contributions and can have a flat tax. Section 9 gives the 2026 rates for a commercial Minijob. Private household Minijobs and the details are outside this Guide.
- **R-DE-P-3: Cross-border workers (Grenzganger).** Cross-border employment needs a tax treaty (DBA) analysis and may fall under foreign social security. Escalate to a Steuerberater.
- **R-DE-P-4: Board members / Geschaftsfuhrer of GmbH.** Managing directors have special social security rules. Escalate.
- **R-DE-P-5: Short-term employment (kurzfristige Beschaftigung).** A job limited to three months or 70 working days in a calendar year, by its nature or by contract in advance, is marginal employment, unless it is done as a profession and the pay is above the Minijob limit. For farms the limit is 15 weeks or 90 working days. The Minijob-Zentrale's table for 2026 shows no health or pension contribution for a short-term Minijob, only the levies and a flat tax option. Special rules apply. See § 8(1) no. 2 SGB IV at https://www.gesetze-im-internet.de/sgb_4/__8.html

## Section 3: BMF PAP Tax Formula (UPTAB26)

The formulas below are the 2026 values from § 32a EStG and from the finance ministry's Programmablaufplan for 2026, Anlage 1, final version of 12 November 2025. It covers pay periods that end after 31 December 2025 and before 1 January 2027. PAP document: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026-anlage-1.pdf?__blob=publicationFile&v=2

All values are annual. For monthly, weekly or daily payroll the employer multiplies the pay by 12, by 360 / 7 or by 360, works out the annual tax, and takes 1 / 12, 7 / 360 or 1 / 360 of it. Parts of a cent are dropped (§ 39b(2) sentences 2, 9 and 10 EStG). The PAP takes its money inputs in cents.

The live version of this Guide carried the 2025 constants and took them from a private code repository. Every constant below is now read from the statute or the ministry's own document.

### Formula (§ 32a EStG, 2026 PAP constants)

~~~
UPTAB26: tariff formula 2026
Input: X = taxable amount for the year, rounded down to whole euros (in class III: half of it, rounded down)
GFB = 12348

Zone 0: if X is less than GFB + 1:
    ST = 0
Zone 1: if X is less than 17800:
    Y  = (X - GFB) / 10000
    RW = Y * 914.51 + 1400
    ST = floor(RW * Y)
Zone 2: if X is less than 69879:
    Y  = (X - 17799) / 10000
    RW = Y * 173.10 + 2397
    ST = floor(RW * Y + 1034.87)
Zone 3: if X is less than 277826:
    ST = floor(X * 0.42 - 11135.63)
Zone 4: otherwise:
    ST = floor(X * 0.45 - 19470.38)

Final: ST = ST * KZTAB
(KZTAB = 2 for tax class III, where X is half of the taxable amount; KZTAB = 1 for all others)
~~~

The taxable amount (ZVE in the PAP) is the annualised pay, less any pension allowance and old-age relief, less or plus the allowance or added amount from the wage tax data, less the fixed amounts of the tax class (ANP, SAP, EFA), less the Vorsorgepauschale. See § 39b(2) sentence 5 EStG at https://www.gesetze-im-internet.de/estg/__39b.html

### Steuerklasse V/VI Special Method (MST5_6)

Tax classes V and VI do not use the tariff directly. The wage tax is twice the difference between the tariff tax on one and a quarter times the taxable amount and the tariff tax on three quarters of it, with the floor and the caps in the table.

~~~
UP5-6(ZX):
    ST1  = UPTAB26(ZX * 1.25, rounded down to whole euros)
    ST2  = UPTAB26(ZX * 0.75, rounded down to whole euros)
    DIFF = (ST1 - ST2) * 2
    MIST = ZX * 0.14, rounded down to whole euros        minimum tax
    ST   = the higher of DIFF and MIST

PAP constants 2026:
    W1STKL5 = 14071
    W2STKL5 = 34939
    W3STKL5 = 222260
~~~

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__39b.html |
| Minimum wage tax in classes V and VI, as a share of the taxable amount | 14% | § 39b(2) sentence 7 EStG: "mindestens 14 Prozent des zu versteuernden Jahresbetrags" |
| First threshold (W1STKL5). For the part of the taxable amount above it, the tax is at most the first upper share below | EUR 14,071 | "für den 14 071 Euro übersteigenden Teil des zu versteuernden Jahresbetrags höchstens 42 Prozent" |
| Second threshold (W2STKL5). For the part above it, the tax is the first upper share | EUR 34,939 | "für den 34 939 Euro übersteigenden Teil des zu versteuernden Jahresbetrags 42 Prozent" |
| First upper share | 42% | Same sentence |
| Third threshold (W3STKL5). For the part above it, the tax is the second upper share | EUR 222,260 | "für den 222 260 Euro übersteigenden Teil des zu versteuernden Jahresbetrags 45 Prozent" |
| Second upper share | 45% | Same sentence |

UP5-6 is never called on its own. The PAP calls it through MST5-6, which applies the three thresholds:
~~~
MST5-6(X):                      X = taxable amount, whole euros
    if X is more than W2STKL5:
        ST = UP5-6(W2STKL5)
        if X is more than W3STKL5:
            ST = ST + floor((W3STKL5 - W2STKL5) * 0.42)
            ST = ST + floor((X - W3STKL5) * 0.45)
        else:
            ST = ST + floor((X - W2STKL5) * 0.42)
    else:
        ST = UP5-6(X)
        if X is more than W1STKL5:
            VERGL = ST
            HOCH  = UP5-6(W1STKL5) + floor((X - W1STKL5) * 0.42)
            ST    = the lower of HOCH and VERGL
~~~

### Solidaritatszuschlag Formula (MSOLZ)

~~~
MSOLZ (running pay):
    SOLZFREI = 20350 * KZTAB
    JBMG = annual wage tax worked out with the child allowances (KFB), times the factor F if one applies
    if JBMG is more than SOLZFREI:
        SOLZJ   = JBMG * 5.5 / 100              rounded down to the cent
        SOLZMIN = (JBMG - SOLZFREI) * 11.9 / 100
        if SOLZMIN is less than SOLZJ: SOLZJ = SOLZMIN
        SOLZLZZ = the share of SOLZJ for the pay period
    else:
        SOLZLZZ = 0
    if R is more than 0: BK = the share of JBMG for the pay period, else BK = 0

MSOLZSTS (one-time payments):
    if the year's wage tax with the one-time payment, worked out with KFB, is more than SOLZFREI:
        SOLZS = STS * 5.5 / 100                 rounded down to the cent
    else:
        SOLZS = 0
~~~

- **Phase-in rate purpose.** The mitigation rate makes the surcharge grow gradually above the exemption limit and keeps it from jumping to the full rate. The rate, the mitigation rate and the limits are in the two tables in Section 1.

### Vorsorgepauschale (Insurance Deduction in Tax Computation)

The PAP deducts a Vorsorgepauschale from pay before it works out the wage tax. It stands for the employee's own social insurance contributions. In the 2026 text it has five parts (§ 39b(2) sentence 5 no. 3 EStG): pension insurance, statutory health insurance, care insurance, private health and care insurance, and unemployment insurance.

~~~
MPARA constants 2026 (from the PAP):
    BBGRVALV = 101400                  yearly ceiling, pension and unemployment insurance
    RVSATZAN = 0.0930                  employee pension rate
    AVSATZAN = 0.0130                  employee unemployment rate
    BBGKVPV  = 69750                   yearly ceiling, health and care insurance
    KVSATZAN = KVZ / 2 / 100 + 0.07    half the fund's additional rate plus half the REDUCED health rate
    PVSATZAN = 0.018                   (0.023 if PVS = 1)
    if PVZ = 1: PVSATZAN = PVSATZAN + 0.006
    else:       PVSATZAN = PVSATZAN - PVA * 0.0025

UPEVP:
    pension part:
        if KRV = 1: VSPR = 0
        else:       VSPR = (pay, at most BBGRVALV) * RVSATZAN
    health and care part (MVSPKVPV):
        if PKV = 0:  VSPKVPV = (pay, at most BBGKVPV) * (KVSATZAN + PVSATZAN)
        if PKV = 1:  VSPKVPV = PKPV * 12 - PKPVAGZ * 12, in euros, not below 0   (class VI: 0)
    VSP = VSPR + VSPKVPV, rounded UP to whole euros
    unemployment part (MVSPHB), only if ALV = 0 and the tax class is not VI:
        VSPALV = (pay, at most BBGRVALV) * AVSATZAN
        VSPHB  = VSPALV + VSPKVPV, at most 1900
        VSPN   = VSPR + VSPHB, rounded UP to whole euros
        if VSPN is more than VSP: VSP = VSPN
~~~

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__39b.html |
| Cap that lets the unemployment part count: it counts only so far as, together with the health and care parts, it does not go above this amount per year | EUR 1,900 | § 39b(2) sentence 5 no. 3(e) EStG: "einen Betrag in Höhe von 1 900 Euro nicht übersteigt" |

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_5/__243.html |
| Reduced health insurance rate of § 243 SGB V, the rate § 39b(2) sentence 5 no. 3(b) EStG names for the Vorsorgepauschale. FULL rate. Not the rate the employee pays | 14.0% | "Der ermäßigte Beitragssatz beträgt 14,0 Prozent der beitragspflichtigen Einnahmen" |

- **Rounding.** The PAP rounds the Vorsorgepauschale up to whole euros. It rounds the tariff input, every tariff result, the minimum tax and the threshold steps of classes V and VI down to whole euros. The PAP shows the direction with arrow symbols that a text copy of the PDF loses. The statute words it only for the tariff (§ 32a(1) sentences 1 and 6 EStG) and for parts of a cent (§ 39b(2) sentence 10 EStG).
- **What the cap means in practice.** Once the health and care part alone is above the cap, the unemployment part adds nothing. Below that, health, care and unemployment parts together count up to the cap.
- **The health part uses the reduced rate.** For the wage tax the PAP takes half of the reduced health rate of § 243 SGB V plus half of the fund's own additional rate. That is not the rate the employee pays, which is built on the general rate. Do not swap one for the other. The PAP prints the constant without naming it; this reading follows the statute and the PAP's opening note.
- **The fund's own additional rate counts.** The PAP says the input KVZ is the full additional rate of the employee's own fund, and that the average rate is not relevant, except for the groups of § 242(3) SGB V, for whom the average rate counts. The PAP splits it between employee and employer itself.
- **Severance.** Compensation within § 24 no. 1 EStG is left out when the pension, health, care and unemployment parts are worked out.
- **No minimum Vorsorgepauschale any more.** The live version of this Guide used a minimum part: a share of pay with a cap that was higher in class III. The 2026 text of § 39b(2) EStG and the 2026 PAP have no such minimum. It is removed.
- **Private insurance.** For privately insured employees the PAP takes the monthly premiums for basic private health and compulsory care cover from the wage tax data (PKPV) and takes off the tax-free employer subsidy (PKPVAGZ). This applies in classes I to V only.

## Section 4: Social Security Computation (Employer Payroll)

### 4.1 Monthly Payroll Social Security Deductions

- **Assessment base rule.** For each branch the employer works out contributions on `assessment_base = min(gross_monthly, BBG)`, with the ceiling of that branch from the ceilings tables in Section 1.

| Branch | Rate (AN) | Rate (AG) | Ceiling that applies |
| --- | --- | --- | --- |
| RV (Pension) | Employee half in the halves table | Employer half in the halves table | Pension and unemployment ceiling |
| KV (Health) | Half of the general rate plus half of the fund's additional rate | The same | Health and care ceiling |
| PV (Care) | By children, age and Saxony: see the care table | Employer share in the care table | Health and care ceiling |
| AV (Unemployment) | Employee half in the halves table | Employer half in the halves table | Pension and unemployment ceiling |

- **Who pays.** The employer pays the whole contribution to the collecting office and takes the employee's part out of the pay. A deduction that was missed can be made up only at the next three wage payments, and later only if the employer was not at fault (§ 28g SGB IV). See https://www.gesetze-im-internet.de/sgb_4/__28g.html
- **Several jobs at once.** If pay from several insured jobs together goes above a ceiling, each pay is reduced in proportion, so that together they reach the ceiling at most. Before that step each pay is first cut to the ceiling (§ 22(2) SGB IV). See https://www.gesetze-im-internet.de/sgb_4/__22.html
- **One-time payments.** A one-time payment belongs to the pay period in which it is paid. It carries contributions only so far as the pay so far in the year has not reached the part of the yearly ceiling that matches the time worked for that employer. A one-time payment made from 1 January to 31 March is moved to the last pay period of the year before, if the same employer pays it and it would go above that part-year ceiling. For an employee who is compulsorily insured in statutory health insurance, only the health ceiling counts for this test (§ 23a SGB IV). See https://www.gesetze-im-internet.de/sgb_4/__23a.html
- **Part months.** This Guide gives the monthly and yearly ceilings as printed. It does not cover part-month ceilings.

### 4.2 Total Maximum Monthly Deductions (at or above all ceilings)

The live version of this Guide listed maximum monthly contributions per branch. It had worked them out itself as ceiling times rate, with 2025 values. No official page read prints maximum employee contributions per branch, so those amounts are removed. To get a maximum, apply the rates in Section 1 to the monthly ceilings in Section 1.

The health funds' fact sheet for 2026 does print maximum amounts for one payroll case: the employer's subsidy for an employee who is not compulsorily insured, for example because pay is above the general compulsory insurance threshold, and who is a voluntary member of a statutory fund or privately insured.

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf |
| Maximum monthly employer subsidy to health insurance with sick pay claim (§ 257 SGB V). Half of the additional contribution comes on top | EUR 424.31 | Fact sheet: "Krankenversicherung mit Anspruch auf Krankengeld 424,31" |
| Maximum monthly employer subsidy to care insurance (§ 61 SGB XI), every state except Saxony | EUR 104.63 | "Pflegeversicherung (bundeseinheitlich außer Sachsen) 104,63" |
| Maximum monthly employer subsidy to care insurance, Saxony | EUR 75.56 | "Pflegeversicherung nur Bundesland Sachsen 75,56" |

### 4.3 Employer-Only Contributions (not deducted from employee)

| Contribution | Rate | Base |
| --- | --- | --- |
| Umlage U1 (continued pay in sickness) | No single rate. Each health fund sets its own rate in its statutes (§ 9 AAG) | The pay on which pension contributions are worked out (§ 7(2) AAG). One-time payments are left out for U1 |
| Umlage U2 (maternity costs) | No single rate. Each health fund sets its own rate | The pay on which pension contributions are worked out |
| Insolvenzgeldumlage | See the table below | The pay on which pension contributions are worked out (§ 358(2) SGB III) |
| Berufsgenossenschaft (accident insurance) | No general rate. The accident insurer bills the employer after the end of the year | Total pay, the hazard class of the trade and the insurer's contribution factor |

**Insolvency levy and the Minijob-Zentrale's own levy rates, 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://magazin.minijob-zentrale.de/minijob-beitraege-2026/ |
| Insolvency levy (Insolvenzgeldumlage), employer only. § 360 SGB III prints the same rate | 0.15% | Minijob-Zentrale, table for 2026: "Insolvenzgeldumlage 0,15% 0,15%" |
| U1 rate of the Minijob-Zentrale, for Minijobs only. It is not the U1 rate of any other health fund | 0.8% | "Zum 1. Januar 2026 wurde die Umlage 1 von bisher 1,1 Prozent auf 0,8 Prozent" |
| U2 rate of the Minijob-Zentrale, for Minijobs only | 0.22% | "Umlage 2 0,22% 0,22%" |

**What U1 pays back**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/aufag/__1.html |
| Share of continued sick pay that U1 refunds under the statute. A fund's statutes may set other refund levels | 80% | § 1(1) AAG: "nicht mehr als 30 Arbeitnehmer und Arbeitnehmerinnen beschäftigen, 80 Prozent" |

- **Who is in U1.** Employers that as a rule employ not more than 30 employees, not counting apprentices (§ 1(1) AAG). The live version of this Guide said "fewer than 30"; the statute says "not more than 30". For U2 the statute sets no size limit, and U2 refunds the maternity costs it covers in full (§ 1(2) AAG).
- **Base corrected.** The live version of this Guide said U1 and U2 are charged on pay up to the health ceiling. The statute ties both to the pay on which pension contributions are worked out (§ 7(2) AAG). See https://www.gesetze-im-internet.de/aufag/__7.html
- **Insolvency levy corrected.** The live version of this Guide carried an older, lower rate. Private households and public bodies do not pay the levy (§ 358(1) SGB III). See https://www.gesetze-im-internet.de/sgb_3/__358.html
- **Accident insurance.** The commercial accident insurers work out the contribution after the end of the business year from their financial need, the pay of the insured and the hazard classes. The live version of this Guide gave a range of rates; no official page prints one, so it is removed. See https://www.dguv.de/de/ihr_partner/unternehmen/beitragsberechnung/index.jsp

## Section 5: Worked Examples

The examples show which rule and which table row applies. They do not print computed amounts, because this Guide states only numbers that an official page prints. The wage tax amounts come from the ministry's own test table in Section 10. That table is worked out with all insurance markers at 0, an additional health rate (KVZ) of 2.90 and, outside class II, the childless surcharge.

### Example 1: Steuerklasse I, no church, childless

**Input:** Stkl I, R = 0, PVZ = 1, KVZ = 2.90, KRV = 0, ALV = 0, PKV = 0, PVS = 0, no children, employee aged 23 or older. Annual gross pay: EUR 60,000.

**Lohnsteuer:** the Section 10 table shows EUR 9,389 for the year in class I. The PAP gets there in this order: annual pay, less ANP and SAP, less the Vorsorgepauschale, gives the taxable amount; UPTAB26 gives the tax.

**SolZ:** the year's wage tax is below the exemption limit for class I in Section 1, so no surcharge is withheld.

**KiSt:** none, because R = 0.

**Social security:** the pay is below both yearly ceilings, so the whole pay is the base in all four branches. Employee shares: the pension half and the unemployment half from the halves table; the childless employee share from the care table; and for health, half of the general rate plus half of the fund's own additional rate.

### Example 2: Steuerklasse III, church (Bavaria), 2 children

**Input:** Stkl III, R above 0, workplace in Bavaria, ZKF = 2.0, PVZ = 0, PVA = 1 (two children under 25). Annual gross pay: EUR 80,000.

**Lohnsteuer:**
- KZTAB = 2 (Splitting): UPTAB26 is applied to half of the taxable amount and the result is doubled.
- The child allowances do not change the wage tax. They are used only for the second calculation that gives JBMG, the base for SolZ and KiSt. Here KFB is ZKF times the amount for classes I, II and III in the child allowance table in Section 1.
- The Section 10 table cannot be used for this employee as it stands. Its class III column is worked out with the childless surcharge (PVZ = 1). With two children the care part of the Vorsorgepauschale is different, so the wage tax is different. Run the PAP with the real inputs.

**KiSt:** BK times the church tax rate of the state. For Bavaria see the church tax table and the note on states in Section 1.

**Social security (2 children):**
- RV and AV: the pay is below the pension and unemployment ceiling, so the whole pay is the base.
- KV and PV: the pay is above the health and care ceiling, so the base is that ceiling.
- PV: the employee share for two children under 25 in the care table. The employer share does not change.

### Example 3: Steuerklasse VI (second job)

**Input:** Stkl VI, R = 0, a second employment. Annual gross pay from it: EUR 20,000.

**Lohnsteuer:** no ANP, no SAP, no EFA and no child allowance count in class VI. The special method of § 39b(2) sentence 7 EStG applies. The Section 10 table shows EUR 2,766 for the year in class VI, against EUR 380 in class I at the same pay.

**Social security:** normal rates apply to the second job. The live version of this Guide said that no more contributions are due once the first job has reached the ceiling. That was wrong. When pay from both jobs together is above a ceiling, both pays are reduced in proportion and each employer pays on its reduced share (§ 22(2) SGB IV, Section 4.1). A second job with pay in the transition band is not treated as a Midijob when the total pay from all jobs is above the band (§ 20(2) SGB IV).

**Afterwards:** an employee who had wages from several employers at the same time must file an income tax return (§ 46(2) no. 2 EStG). See https://www.gesetze-im-internet.de/estg/__46.html

## Section 6: Payslip Transaction Pattern Library

### 6.1 Payslip Credits (Employee receives)

| Pattern | Classification | Notes |
| --- | --- | --- |
| GEHALT, LOHN, ENTGELT | Net salary payment | After all deductions |
| NACHZAHLUNG GEHALT | Salary back-payment | May fall under the sonstige Bezüge rules |
| WEIHNACHTSGELD, 13. GEHALT | Christmas bonus | Taxed as sonstiger Bezug |
| URLAUBSGELD | Holiday bonus | Taxed as sonstiger Bezug |
| ABFINDUNG | Severance payment | Taxed as sonstiger Bezug in payroll. The one-fifth relief of § 34 EStG is no longer applied by the employer; see Section 8 |
| TANTIEME, BONUS, PRAEMIE | Performance bonus | Sonstiger Bezug |
| JUBILAEUM | Anniversary bonus | Sonstiger Bezug |

### 6.2 Employer Deductions (visible on payslip, debited from gross)

| Line Item | What It Is | Employee Portion |
| --- | --- | --- |
| LSt / Lohnsteuer | Income tax withholding | All of it is the employee's |
| SolZ / Solidaritatszuschlag | Solidarity surcharge | All of it is the employee's |
| KiSt / Kirchensteuer | Church tax | All of it is the employee's |
| RV-Beitrag AN | Pension contribution | 9.3% of gross (up to the pension ceiling) |
| KV-Beitrag AN | Health contribution | Half of the general rate plus half of the fund's additional rate, on gross up to the health ceiling |
| PV-Beitrag AN | Care contribution | See the care table in Section 1 |
| AV-Beitrag AN | Unemployment contribution | 1.3% of gross (up to the pension ceiling) |

## Section 7: Key PAP Input Parameters Reference

These are input parameters of the finance ministry's Programmablaufplan for 2026, section 3.1, final version of 12 November 2025. The list is not complete: the inputs for employer pensions (VBEZ and related fields) and for employee share schemes are left out. The PAP does not check its inputs; the employer's software must. Source: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026-anlage-1.pdf?__blob=publicationFile&v=2

| Parameter | Description |
| --- | --- |
| RE4 | Taxable pay for the pay period, in cents, before pension allowance, old-age relief and any allowance or added amount from the wage tax data |
| STKL | Steuerklasse: 1 = I, 2 = II, 3 = III, 4 = IV, 5 = V, 6 = VI |
| LZZ | Pay period: 1 = Jahr, 2 = Monat, 3 = Woche, 4 = Tag |
| R | Religious community from the wage tax data (0 = none) |
| KRV | Marker for the Vorsorgepauschale. 0 = compulsorily insured in the statutory pension scheme or a professional pension institution, or insured there voluntarily after an exemption. 1 = if not 0 |
| ALV | New in 2026. Marker for the Vorsorgepauschale. 0 = compulsorily insured in unemployment insurance. 1 = if not 0 |
| KVZ | Additional rate of the employee's own health fund in percent with two decimals (for example 2.90). Always the full rate; the PAP splits it |
| PVS | 1 = the Saxony rule for care insurance applies |
| PVZ | 1 = the employee pays the childless surcharge |
| PVA | Number of care insurance reductions for more than one child: 0 = none, 1 = second child, 2 = second and third, 3 = second to fourth, 4 = second to fifth or more |
| PKV | 0 = statutory health insurance, 1 = private health insurance only. The value 2 of earlier years no longer exists |
| PKPV | Monthly premiums for basic private health cover and compulsory private care cover from the wage tax data, in cents. Always a monthly amount |
| PKPVAGZ | New in 2026. Tax-free employer subsidy to private health and care cover, in cents. Always a monthly amount |
| ZKF | Number of child allowance counters, one decimal, only in classes I, II, III and IV |
| AF | 1 = the factor method was chosen (class IV only) |
| F | The factor from the wage tax data, three decimals |
| ALTER1 | 1 = the employee turned 64 before the start of the calendar year in which the pay period ends (§ 24a EStG), else 0 |
| AJAHR | The calendar year after the employee turned 64. Needed when ALTER1 = 1 |
| LZZFREIB | Allowance for the pay period from the wage tax data, in cents |
| LZZHINZU | Added amount for the pay period from the wage tax data, in cents |
| JFREIB | Annual allowance from the wage tax data for the tax on one-time payments, in cents |
| JHINZU | Annual added amount from the wage tax data for the tax on one-time payments, in cents |
| JRE4 | Expected annual pay without one-time payments, in cents. Needed whenever SONSTB is filled |
| SONSTB | One-time payments, in cents |
| SONSTENT | Compensation within § 24 no. 1 EStG that is included in SONSTB, in cents |

The field types in the live version of this Guide (BigDecimal, int, double) came from a private Java project, not from the ministry. They are dropped.

### Key Output Parameters

| Parameter | Description |
| --- | --- |
| LSTLZZ | Lohnsteuer to withhold for the pay period, in cents |
| SOLZLZZ | Solidaritätszuschlag to withhold for the pay period, in cents |
| BK | Bemessungsgrundlage for Kirchensteuer for the pay period, in cents |
| STS | Lohnsteuer on sonstige Bezüge, in cents |
| SOLZS | Solidaritätszuschlag on sonstige Bezüge, in cents |
| BKS | Kirchensteuer Bemessungsgrundlage on sonstige Bezüge, in cents |

The 2026 PAP also returns six fields for the tax treaty routine (VFRB, VFRBS1, VFRBS2, WVFRB, WVFRBM, WVFRBO). The output VKVLZZ in the live version of this Guide is not among the outputs of the 2026 PAP and is removed.

## Section 8: Sonstige Bezuege (Bonuses, One-Time Payments)

Sonstige Bezüge (bonuses, severance, holiday pay) are taxed separately under § 39b(3) EStG. The employer:

1. Works out the annual Lohnsteuer on the expected annual pay without the one-time payment (the voraussichtlicher Jahresarbeitslohn).
2. Works out the annual Lohnsteuer on that pay plus the one-time payment.
3. Withholds the difference as the tax on the one-time payment.

This keeps a one-time payment from being taxed as if it were paid every month. See https://www.gesetze-im-internet.de/estg/__39b.html

- **Earlier employers in the same year.** If the employee has not handed in the wage tax certificates of earlier employers in the year, the employer scales the current monthly pay up to cover those months. The employer marks this in the payroll account with the capital letter S, and the employee must then file a return (§ 39b(3) sentence 2, § 41(1) sentence 6 and § 46(2) no. 5a EStG).
- **Solidarity surcharge.** See the note on one-time payments in the SolZ part of Section 1: a yearly test, then the full rate without mitigation.
- **Social insurance.** See the note on one-time payments in Section 4.1.

**Fünftelregelung (§ 34 EStG): no longer in payroll.** The live version of this Guide said the one-fifth rule "may apply" to Entschädigungen and Abfindungen in payroll. That ended on 1 January 2025. The ministry letter of 22 November 2024 on the 2025 PAP records "den Wegfall der Tarifermäßigung des § 34 EStG im Lohnsteuer-Abzugsverfahren nach der Aufhebung von § 39b Absatz 3 Satz 9 und 10 EStG durch das Wachstumschancengesetz". See https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2024-11-22-PAP-2025_anlage.pdf?__blob=publicationFile&v=2 The 2026 PAP covers § 39b(3) sentences 1 to 8 only. The employer now taxes a severance payment like any other one-time payment. § 34 EStG itself still exists as a rule of the income tax assessment:
- The tax on the extraordinary income is five times the difference between the tax on the other taxable income and the tax on that income plus one fifth of the extraordinary income.
- Extraordinary income includes compensation within § 24 no. 1 EStG and pay for work that spans at least two assessment periods and more than twelve months.
- See https://www.gesetze-im-internet.de/estg/__34.html

## Section 9: Mini-Jobs and Gleitzone (Midijobs)

### Mini-Jobs (Geringfugige Beschaftigung)

**The Minijob limit**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesregierung.de/breg-de/aktuelles/mindestlohn-steigt-2391010 |
| Minijob limit (Geringfügigkeitsgrenze) from 1 January 2026: regular pay per month | EUR 603 | Federal Government: "Sie liegt seit 1. Januar 2026 bei 603 Euro im Monat. 2027 steigt sie auf 633 Euro." |

**Commercial Minijob: what the employer and the Minijobber pay in 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://magazin.minijob-zentrale.de/minijob-beitraege-2026/ |
| Employer's flat health insurance contribution, only if the Minijobber is in statutory health insurance | 13% | Minijob-Zentrale, table for 2026: "Krankenversicherung 13% - Rentenversicherung 15%" |
| Employer's flat pension contribution | 15% | Same row |
| The Minijobber's own pension share, withheld from pay | 3.6% | "Dieser Eigenanteil liegt im Jahr 2026 bei 3,6 Prozent des Verdienstes bei gewerblichen Minijobs" |

**Flat tax for a Minijob**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__40a.html |
| Uniform flat tax that covers wage tax, solidarity surcharge and church tax in one. Only where the employer pays the flat pension contribution for that Minijob | 2% | § 40a(2) EStG: "mit einem einheitlichen Pauschsteuersatz in Höhe von insgesamt 2 Prozent des Arbeitsentgelts" |

- **Pension duty is the rule, release is on application.** The live version of this Guide said the Minijobber pays nothing unless they opt in to pension insurance. It is the other way round. A Minijobber is subject to pension insurance and pays the own share in the table, unless they apply to be released. The Minijob-Zentrale page in the table says so.
- **Tax.** Instead of the flat tax the employer can tax the pay by the employee's wage tax data. The flat tax is paid to the Minijob-Zentrale, not to the tax office.
- **Levies.** The employer also pays U1, U2 and the insolvency levy at the Minijob-Zentrale's rates in Section 4.3, and accident insurance to its own accident insurer.
- **What the limit is.** It is regular monthly pay. An overrun that could not be foreseen, in not more than two calendar months within a twelve-month period, each time by not more than the limit itself, does not end the Minijob (§ 8(1b) SGB IV). See https://www.gesetze-im-internet.de/sgb_4/__8.html
- **Several jobs.** Several Minijobs are added together. One Minijob beside a main job that is subject to insurance is not added to it; any further Minijob is (§ 8(2) SGB IV).
- **Trap.** The Minijobber's own pension share is the same number as the full care insurance rate. They are different rules.
- **Not covered here.** Minijobs in private households have lower rates. Short-term jobs carry no contributions but have their own flat tax rule.

### Midijobs / Uebergangsbereich (Gleitzone)

**Lower limit**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026 |
| Lower limit of the transition band in 2026, per month | EUR 603.01 | Pension insurer: "steigt im kommenden Jahr auf monatlich 603,01 Euro" |

**Upper limit and the value behind Factor F**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/sgb_4/__20.html |
| Upper limit of the transition band: regular pay per month. With several jobs the total pay counts | EUR 2,000 | § 20(2) SGB IV: "die regelmäßig 2 000 Euro im Monat nicht übersteigen" |
| Factor F is this value divided by the total contribution rate of the year | 28% | § 20(2a) SGB IV: "indem der Wert 28 Prozent geteilt wird durch den Gesamtsozialversicherungsbeitragssatz" |

**Total contribution rate and Factor F for 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf |
| Total social insurance contribution rate 2026 (Gesamtsozialversicherungsbeitragssatz). It exists only to derive Factor F. Nobody pays this rate | 42.30% | Fact sheet for 2026: "Gesamtsozialversicherungsbeitragssatz / Faktor F 42,30 % / 0,6619" |
| Factor F for 2026. A plain factor, not a percentage and not an amount | 0.6619 | Same line of the fact sheet |

| Parameter | Value |
| --- | --- |
| Range | From the lower limit to the upper limit in the tables above, regular monthly pay |
| Employee contributions | Reduced. The employee's part is worked out on a reduced base, by the second formula in § 20(2a) SGB IV |
| Employer contributions | Not the normal half. The total contribution is worked out on a first reduced base, by the first formula in § 20(2a) SGB IV. The employee bears half of the contribution on the second base. The employer bears the rest |
| Lohnsteuer | Normal withholding by Steuerklasse |

- **Corrected.** The live version of this Guide said the employer pays "full standard rates" in the band. Under the current rules the employer bears whatever the employee does not. See § 20(2a) SGB IV in the table above, and for each branch § 249(3) SGB V, § 168(1) no. 1d SGB VI, § 58(5) SGB XI and § 346(1a) SGB III. Health insurance: https://www.gesetze-im-internet.de/sgb_5/__249.html Unemployment insurance: https://www.gesetze-im-internet.de/sgb_3/__346.html
- **The formulas.** The federal law page shows the two formulas of § 20(2a) SGB IV as images that the text reader cannot read. This Guide does not restate them from memory. Take them from the statute page.
- **Who is not covered.** Apprentices. For an apprentice paid up to the apprentice limit in § 20(3) SGB IV the employer bears the whole contribution alone.

## Section 10: Test Suite

**Test 1: the ministry's own test table.** The 2026 PAP ends with a test table of annual wage tax (allgemeine maschinelle Jahreslohnsteuer, Prüftabelle). Software that implements the PAP must reproduce it. The table is worked out with ALV = 0, KRV = 0, PKV = 0 and KVZ = 2.90. In class II it uses PVZ = 0, in all other classes PVZ = 1. It is the wage tax for an employee who is insured in all branches. Five of its rows:

| Annual gross pay | Class I | Class II | Class III | Class IV | Class V | Class VI |
| --- | --- | --- | --- | --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026-anlage-1.pdf?__blob=publicationFile&v=2 | | | | |
| EUR 20,000 | EUR 380 | none | none | EUR 380 | EUR 2,234 | EUR 2,766 |
| EUR 40,000 | EUR 4,407 | EUR 3,293 | EUR 1,000 | EUR 4,407 | EUR 8,720 | EUR 9,218 |
| EUR 60,000 | EUR 9,389 | EUR 8,091 | EUR 4,822 | EUR 9,389 | EUR 15,364 | EUR 15,895 |
| EUR 80,000 | EUR 15,694 | EUR 14,188 | EUR 9,496 | EUR 15,694 | EUR 22,538 | EUR 23,070 |
| EUR 100,000 | EUR 23,248 | EUR 21,634 | EUR 15,012 | EUR 23,248 | EUR 30,157 | EUR 30,689 |

The PAP prints a second table for employees who are insured in no branch (besondere Lohnsteuer). It is not repeated here.

**Test 2: Stkl III with children and church tax.** Input: STKL = 3, LZZ = 2, R above 0, ZKF = 2.0, PVZ = 0, PVA = 1. Expected: LSTLZZ is the same with ZKF = 0 and with ZKF = 2.0. SOLZLZZ and BK are never higher with ZKF = 2.0 than with ZKF = 0. KiSt = BK times the state's rate.

**Test 3: Stkl V.** Input: STKL = 5, LZZ = 2, PVZ = 1. Expected: LSTLZZ is never below the minimum share of the taxable amount in the Section 3 table. In every row of the ministry's test table the class V tax is higher than the class I tax.

**Test 4: above all ceilings, Stkl I.** Input: monthly pay above the pension and unemployment ceiling. Expected: the base for RV and AV is that ceiling, and the base for KV and PV is the lower health and care ceiling. Raising the pay further changes no contribution.

**Test 5: SolZ phase-in.** Input: an annual base (JBMG) a little above the exemption limit, tax class I. Expected: the surcharge equals the mitigation rate applied to the excess over the limit, and it is lower than the full rate applied to the base. With a base at or below the limit the surcharge is zero.

**Test 6: check against the ministry's online calculator.** Results should match the finance ministry's online wage tax calculator (bmf-steuerrechner.de) for the same inputs.

The live version of this Guide carried test values it had worked out itself with 2025 constants. They are replaced by the ministry's printed values and by checks that need no computed number.

## Section 11: Interaction with Other German Guides

| Scenario | Guide to use |
| --- | --- |
| Employee payroll (Lohnsteuer) | **This Guide (`de-payroll`)** |
| Full payroll lifecycle: payslip content, mandatory benefits, filing duties, employer cost | `germany-payroll` |
| Self-employed income tax (Einkommensteuer) | `de-einkommensteuer-freelancer` |
| Self-employed social contributions | `de-social-contributions` |
| Gewerbesteuer (trade tax) | `de-trade-tax` |
| Umsatzsteuer / VAT return | `germany-vat-return` |
| Quarterly income tax prepayments | `de-estimated-tax` |
| ZUGFeRD and XRechnung e-invoicing | `germany-einvoice` |

## The method, step by step

1. Get an employer number (Betriebsnummer). The Bundesagentur für Arbeit's Betriebsnummern-Service issues it on an online application. An employer needs one for each place of employment to take part in the social insurance reporting procedure. https://www.arbeitsagentur.de/unternehmen/betriebsnummern-service/alles-wichtige
2. At the start of each employment, take the employee's tax identification number, date of birth, and whether this is the first or a further employment. Retrieve the electronic wage tax data (ELStAM) from the Bundeszentralamt für Steuern, put them in the payroll account, and check for changes every month (§ 39e(4) and (5) EStG). If the employee is at fault for not giving the data, use class VI (§ 39c EStG). https://www.gesetze-im-internet.de/estg/__39e.html
3. Keep a payroll account (Lohnkonto) for each employee and each calendar year at the place of business, and enter the kind and amount of pay and the tax withheld at every wage payment. Keep it until the end of the sixth calendar year after the last wage payment entered (§ 41(1) EStG; details in § 4 LStDV). https://www.gesetze-im-internet.de/estg/__41.html
4. Report the start of the employment to the collecting office (Einzugsstelle): the employee's health fund, or the Minijob-Zentrale at the Deutsche Rentenversicherung Knappschaft-Bahn-See for a Minijob (§ 28a and § 28i SGB IV). Decide the status first: Minijob, transition band, normal employment, or pay above the compulsory insurance threshold. https://www.gesetze-im-internet.de/sgb_4/__28a.html
5. At every wage payment, work out and withhold the wage tax with the PAP (§ 38(3) and § 39b EStG), then the solidarity surcharge (§ 3 and § 4 SolzG) and, for church members, the church tax on BK. https://www.gesetze-im-internet.de/estg/__39b.html
6. At every wage payment, work out the contributions of each branch on pay up to that branch's ceiling and take the employee's share out of the pay (§ 28g SGB IV). https://www.gesetze-im-internet.de/sgb_4/__28g.html
7. Send the contribution statement (Beitragsnachweis) to the collecting office two working days before the contributions fall due (§ 28f(3) SGB IV) https://www.gesetze-im-internet.de/sgb_4/__28f.html and pay the expected contributions by the third-last bank working day of the month in which the work is done. A remainder falls due on the third-last bank working day of the next month (§ 23(1) SGB IV). https://www.gesetze-im-internet.de/sgb_4/__23.html
8. File the wage tax return (Lohnsteuer-Anmeldung) electronically with the tax office of the place of business and pay the wage tax, both by the tenth day after the end of each return period (§ 41a(1) EStG). The return period is the month, unless the table below allows a longer one. https://www.gesetze-im-internet.de/estg/__41a.html
9. At the end of the year or of the employment, close the payroll account and send the electronic wage tax certificate (Lohnsteuerbescheinigung) to the tax authority (§ 41b(1) EStG https://www.gesetze-im-internet.de/estg/__41b.html ), by the last day of February of the following year (§ 93c(1) no. 1 AO https://www.gesetze-im-internet.de/ao_1977/__93c.html ). Give the employee a printout or electronic access.
10. Where § 42b EStG allows it, carry out the employer's annual wage tax adjustment. It is a duty for an employer with at least ten employees on 31 December. It is not allowed in a list of cases, among them classes V or VI in the year, the factor method, an allowance in the wage tax data, or a change of the health fund's additional rate during the year. https://www.gesetze-im-internet.de/estg/__42b.html

**Return period for the wage tax return**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__41a.html |
| One return per calendar year if the wage tax for the previous calendar year was not more than | EUR 1,080 | § 41a(2) EStG: "für das vorangegangene Kalenderjahr nicht mehr als 1 080 Euro betragen hat" |
| One return per quarter if it was more than the yearly limit but not more than | EUR 5,000 | § 41a(2) EStG: "aber nicht mehr als 5 000 Euro betragen hat" |

A business that did not exist for the whole previous year converts its wage tax to a yearly amount for this test. A new business uses the wage tax of the first full month, converted to a year.

What breaks when the order is wrong: without wage tax data the employer must use class VI and correct it later; a missed employee deduction can be made up only at the next three wage payments; a late contribution statement lets the collecting office estimate the pay.

## Ask the client first

- What do the wage tax data (ELStAM) show: tax class, child allowance counters, church membership, any allowance or factor? Is this the employee's first employment or a further one?
- Which health fund is the employee in, and what is its additional rate? Or is the employee privately insured, or a voluntary member because pay is above the compulsory insurance threshold?
- Does the employee have children, how many are under 25, has proof been given, and is the employee 23 or older?
- In which state is the place of employment? It decides the church tax rate and the Saxony rule for care insurance.
- What is the regular monthly pay, and are there other jobs? The answer decides between Minijob, transition band and normal employment, and whether pay from several jobs goes above a ceiling.
- Is a one-time payment, such as a bonus or severance, part of this pay run?

## When to refuse or refer

- Self-employed people and freelancers. Use `de-einkommensteuer-freelancer` and `de-social-contributions`.
- Cross-border workers, postings abroad or into Germany, and any case under a tax treaty. The ministry publishes a separate treaty PAP; it is not covered here.
- Managing directors and board members, whose social insurance status must be decided first.
- Minijobs in private households, short-term jobs and their flat taxes, beyond the short summary in Section 9.
- The miners' pension scheme, civil servants, and employees exempt from a branch.
- Employer pensions (Versorgungsbezüge) and the old-age relief. The PAP has inputs for them; this Guide does not explain them.
- Employees who work on after the standard retirement age. Part of their wages can be tax-free under § 3 no. 21 EStG, within a yearly amount and only where the employer owes pension contributions for that work. This Guide does not cover it. See https://www.gesetze-im-internet.de/estg/__3.html
- Benefits in kind, company cars, flat-rate wage tax under § 40 and § 37b EStG, and company pension schemes.
- Short-time work pay (Kurzarbeitergeld), maternity pay and sick pay periods.
- Apprentices paid up to the apprentice limit, and students.
- Part-month pay periods and the part-month ceilings.
- The exact church tax for a client: caps, minimum amounts and the rules for spouses of different faiths are state law and are not on the federal pages.
- Sign-off. Payroll results from this Guide are working papers. Send them to a Steuerberater or payroll accountant (Lohnbuchhalter) before they are used.

## PROHIBITIONS

- NEVER compute Lohnsteuer with simple bracket percentages. Use the PAP formula (UPTAB26).
- NEVER apply the tariff (UPTAB26) directly to Steuerklasse V or VI. Use MST5-6, which calls UP5-6.
- NEVER forget the Vorsorgepauschale deduction before computing Lohnsteuer, and NEVER use the 2025 minimum Vorsorgepauschale for 2026.
- NEVER reduce the Lohnsteuer itself by child allowances. They count only for the SolZ and KiSt base.
- NEVER confuse the health and care ceiling with the higher pension and unemployment ceiling, or either of them with the compulsory insurance threshold.
- NEVER apply the childless PV surcharge to employees with children, or before the month after the employee turns 23.
- NEVER charge social security contributions above the Beitragsbemessungsgrenze.
- NEVER omit the Sachsen PV exception when the place of employment is in Sachsen.
- NEVER treat sonstige Bezüge (bonuses) as regular pay. Use the separate method of § 39b(3) EStG. NEVER apply the Fünftelregelung in payroll.
- NEVER use the average additional health rate for a real payslip, unless the employee is in one of the groups of § 242(3) SGB V, for whom the law makes the average rate the one that counts, also for the wage tax. For everyone else use the rate of the employee's own fund.
- NEVER add two halves or build a combined rate. State the parts as the official pages print them.
- NEVER assume Kirchensteuer is the same in every state. There are two state rates.
- NEVER present payroll computations as definitive. Direct the user to a Steuerberater or Lohnbuchhalter for sign-off.

## Sources

- EStG § 32a (tariff): https://www.gesetze-im-internet.de/estg/__32a.html
- EStG § 38 (employer withholds): https://www.gesetze-im-internet.de/estg/__38.html
- EStG § 38b (tax classes): https://www.gesetze-im-internet.de/estg/__38b.html
- EStG § 39a (allowances in the wage tax data): https://www.gesetze-im-internet.de/estg/__39a.html
- EStG § 39b (wage tax computation, one-time payments, PAP): https://www.gesetze-im-internet.de/estg/__39b.html
- EStG § 39c (no wage tax data): https://www.gesetze-im-internet.de/estg/__39c.html
- EStG § 39e (electronic wage tax data): https://www.gesetze-im-internet.de/estg/__39e.html
- EStG § 39f (factor method): https://www.gesetze-im-internet.de/estg/__39f.html
- EStG § 9a, § 10c, § 24b (lump sums and single parent relief): https://www.gesetze-im-internet.de/estg/__9a.html and https://www.gesetze-im-internet.de/estg/__10c.html and https://www.gesetze-im-internet.de/estg/__24b.html
- EStG § 34 (one-fifth rule in the assessment): https://www.gesetze-im-internet.de/estg/__34.html
- EStG § 40a (flat tax for Minijobs): https://www.gesetze-im-internet.de/estg/__40a.html
- EStG § 41, § 41a, § 41b, § 42b (payroll account, wage tax return, certificate, annual adjustment): https://www.gesetze-im-internet.de/estg/__41.html and https://www.gesetze-im-internet.de/estg/__41a.html and https://www.gesetze-im-internet.de/estg/__41b.html and https://www.gesetze-im-internet.de/estg/__42b.html
- EStG § 46 (when an employee must file a return): https://www.gesetze-im-internet.de/estg/__46.html
- EStG § 51a (base for church tax and surcharge): https://www.gesetze-im-internet.de/estg/__51a.html
- AO § 93c (deadline for data transmission): https://www.gesetze-im-internet.de/ao_1977/__93c.html
- LStDV § 4 (entries in the payroll account): https://www.gesetze-im-internet.de/lstdv/__4.html
- SolzG § 3 and § 4: https://www.gesetze-im-internet.de/solzg_1995/__3.html and https://www.gesetze-im-internet.de/solzg_1995/__4.html
- Finance ministry, Programmablaufplan for 2026, overview page: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026.html
- Finance ministry, Programmablaufplan for 2026, Anlage 1: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2025-11-12-PAP-2026-anlage-1.pdf?__blob=publicationFile&v=2
- Finance ministry, letter of 22 November 2024 on the 2025 PAP: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Steuerarten/Lohnsteuer/Programmablaufplan/2024-11-22-PAP-2025_anlage.pdf?__blob=publicationFile&v=2
- Finance ministry, tax booklet "Steuern von A bis Z", 2025 edition: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9
- Federal tax office, sample text on church tax rates by state: https://www.bzst.de/SharedDocs/Downloads/DE/KiStA/Widerspruch_Mustertext.pdf?__blob=publicationFile&v=10
- Sozialversicherungsrechengrößen-Verordnung 2026, Federal Law Gazette: https://www.recht.bund.de/bgbl/1/2025/278/regelungstext.pdf?__blob=publicationFile&v=3
- Federal Government, contribution ceilings 2026: https://www.bundesregierung.de/breg-de/aktuelles/beitragsgemessungsgrenzen-2386514
- Federal Government, minimum wage and Minijob limit: https://www.bundesregierung.de/breg-de/aktuelles/mindestlohn-steigt-2391010
- Health ministry, contributions: https://www.bundesgesundheitsministerium.de/beitraege
- Health ministry, financing of long-term care insurance: https://www.bundesgesundheitsministerium.de/themen/pflege/online-ratgeber-pflege/die-pflegeversicherung/finanzierung
- Health funds' association, fact sheet for 2026: https://www.gkv-spitzenverband.de/media/dokumente/presse/zahlen_und_grafiken/20260101_Faktenblatt_Rechengroessen_Beitragsrecht.pdf
- Pension insurer, changes from 1 January 2026: https://www.deutsche-rentenversicherung.de/Nord/DE/Presse/Pressemitteilungen-und-Pressearchiv/Pressemitteilungen/20251218_Aenderung-RV-01012026
- Pension insurer Knappschaft-Bahn-See, social insurance values 2026: https://www.deutsche-rentenversicherung.de/KnappschaftBahnSee/DE/Aktuelles/Meldungen/2026/2026_01_02_Sozialversicherungsrechengroessen2026.html
- Minijob-Zentrale, contributions 2026: https://magazin.minijob-zentrale.de/minijob-beitraege-2026/
- SGB III § 341, § 346, § 358: https://www.gesetze-im-internet.de/sgb_3/__341.html and https://www.gesetze-im-internet.de/sgb_3/__346.html and https://www.gesetze-im-internet.de/sgb_3/__358.html
- SGB IV § 28e and § 28i (who pays, which collecting office): https://www.gesetze-im-internet.de/sgb_4/__28e.html and https://www.gesetze-im-internet.de/sgb_4/__28i.html
- SGB IV § 8, § 20, § 22, § 23, § 23a, § 28a, § 28f, § 28g: https://www.gesetze-im-internet.de/sgb_4/__8.html and https://www.gesetze-im-internet.de/sgb_4/__20.html and https://www.gesetze-im-internet.de/sgb_4/__22.html and https://www.gesetze-im-internet.de/sgb_4/__23.html and https://www.gesetze-im-internet.de/sgb_4/__23a.html and https://www.gesetze-im-internet.de/sgb_4/__28a.html and https://www.gesetze-im-internet.de/sgb_4/__28f.html and https://www.gesetze-im-internet.de/sgb_4/__28g.html
- SGB V § 6, § 241 and § 249: https://www.gesetze-im-internet.de/sgb_5/__6.html and https://www.gesetze-im-internet.de/sgb_5/__241.html and https://www.gesetze-im-internet.de/sgb_5/__249.html
- SGB XI § 55 and § 58: https://www.gesetze-im-internet.de/sgb_11/__55.html and https://www.gesetze-im-internet.de/sgb_11/__58.html
- AAG § 1 and § 7: https://www.gesetze-im-internet.de/aufag/__1.html and https://www.gesetze-im-internet.de/aufag/__7.html
- Bundesagentur für Arbeit, Betriebsnummern-Service: https://www.arbeitsagentur.de/unternehmen/betriebsnummern-service/alles-wichtige
- Deutsche Gesetzliche Unfallversicherung, how contributions are worked out: https://www.dguv.de/de/ihr_partner/unternehmen/beitragsberechnung/index.jsp

## Disclaimer

This Guide and its outputs are provided for informational and computational purposes only and do not constitute tax, legal, or financial advice. Open Accountants and its contributors accept no liability for any errors, omissions, or outcomes arising from the use of this Guide. All outputs must be reviewed and signed off by a qualified professional (such as a Steuerberater or Lohnbuchhalter in Germany) before implementation.

The formulas and constants in this Guide are taken from the statutes and from the finance ministry's own Programmablaufplan for 2026. They are not taken from third-party code.

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
