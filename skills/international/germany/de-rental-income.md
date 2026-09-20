---
name: de-rental-income
description: Use this skill whenever asked about German rental income taxation (Vermietung und Verpachtung). Trigger on phrases like "Mieteinnahmen", "Vermietung", "Verpachtung", "Anlage V", "§21 EStG", "AfA", "Abschreibung", "Werbungskosten Vermietung", "Hausgeld", "Grundsteuer deduction", "Erhaltungsaufwand", "Herstellungskosten", "verbilligte Vermietung", "Möblierungszuschlag", "rental income Germany", "German property tax deduction", "depreciation German property", "Verlustverrechnung", "rental loss Germany", or any question about computing, filing, or optimising income from letting immovable property in Germany. Covers Anlage V structure, AfA depreciation rates, Werbungskosten, repairs vs improvements, reduced-rent rules, furnished premium, and loss offset. ALWAYS read this skill before touching any German rental income work.
version: 1.0
jurisdiction: DE
tax_year: 2026
last_updated: 2026-09-19
review_status: pending_review
drafted_by: OpenAccountants
approved_by: pending
depends_on:
  - de-income-tax
category: international
tier: 2
license: AGPL-3.0-or-later (code) / OpenAccountants Guide License v1.0 (content)
---

# Rental income tax in Germany (Vermietung und Verpachtung)

How Germany taxes an individual on income from letting land, buildings and flats that are held as private assets (Einkünfte aus Vermietung und Verpachtung, § 21 EStG): what counts as income, which costs can be deducted, building depreciation, works soon after a purchase, cheap lets to relatives, losses, and where it all goes on the return. It is for private landlords and the people who prepare their returns. Figures are for tax year 2026. The statute figures are read from the consolidated federal law pages. The form names, the line numbers, the forecast test in Section 4 and the official example in Section 8 come from the tax administration's instructions for the 2025 income tax return on ELSTER, the latest published: the 2026 forms were not out when this was written. The finance ministry's tool for splitting a purchase price is dated March 2026.

## Section 1: Quick Reference

| Field | Value |
| --- | --- |
| Country | Germany (Bundesrepublik Deutschland) |
| Tax | Einkommensteuer auf Einkünfte aus Vermietung und Verpachtung |
| Who this Guide covers | Individuals who let property they hold as private assets. Letting income that belongs to another kind of income, for example a property held in a business, is taxed there and not under § 21 (§ 21(3) EStG) |
| Currency | EUR only |
| Tax year | Calendar year (1 January to 31 December) |
| How the income is measured | Receipts less income-related costs (Werbungskosten), § 2(2) EStG. Cash basis: rent counts when received, costs when paid (§ 11 EStG) |
| Primary legislation | Einkommensteuergesetz (EStG) § 21 (rental income), § 7(4) to (5b) and § 7b (depreciation), § 9 (Werbungskosten) |
| Supporting legislation | EStG §§ 2, 6(1) no. 1a (works soon after purchase), 10d (loss carry-back and carry-forward), 11 (cash basis), 21(2) (cheap letting), 23 (sale within ten years); EStDV § 82b (spreading larger maintenance costs); UStG § 4 no. 12 and § 9 (VAT); AO § 149 (filing dates) |
| Tax authority | Finanzamt (local tax office) |
| Filing portal | ELSTER (elster.de) |
| Filing deadline | Seven months after the end of the calendar year. If a tax adviser prepares the return: the last day of February of the second calendar year after the tax year. The tax office can ask for an advised return earlier. See § 149(2) to (4) AO at https://www.gesetze-im-internet.de/ao_1977/__149.html |
| Tax form | Anlage V to the income tax return, one for each built-on property. Anlage V-FeWo is filed as well for holiday flats and short-term lets. Anlage V-Sonstige covers shares in property or heirs' communities, subletting of rented rooms, land without buildings and the letting of rights. See Section 10 |
| Reviewed by | Pending. Sign-off by a German Steuerberater is required |

**Employees with rental income: when a return is compulsory**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__46.html |
| An employee whose wages had tax withheld is assessed, and so must file a return, if the positive sum of income that was not subject to wage tax (rental income counts) is MORE THAN this amount in the year. A filing trigger, not an exemption. § 46(2) lists other triggers too | EUR 410 | § 46(2) no. 1 EStG: "jeweils mehr als 410 Euro beträgt" |
| For an employee who is assessed, such income is taken off taxable income again if it is NOT MORE THAN this amount in total. Above it, relief is phased out under § 46(5) EStG | EUR 410 | § 46(3) EStG: "insgesamt nicht mehr als 410 Euro betragen" |

Both rows are only for people with employment income. Other filing duties, for example for people with no wages, are in the German income tax Guide, `de-einkommensteuer-freelancer`.

### Income Tax Rates

Net rental income is added to the client's other income and taxed under the normal income tax tariff. Solidarity surcharge and, for church members, church tax come on top. The tariff is not repeated here: use `de-einkommensteuer-freelancer`. The legacy version of this Guide carried a 2025 tariff table. It was removed so that two Guides cannot disagree.

### Rental Income Formula

- **Rental Income Formula.** Einnahmen (rent received, plus the running costs the tenant pays on top, called Umlagen or Nebenkosten) less Werbungskosten (deductible costs: depreciation, loan interest, maintenance, insurance and so on) = Einkünfte aus Vermietung und Verpachtung (net rental income or loss). See § 2(2) EStG at https://www.gesetze-im-internet.de/estg/__2.html
- **Umlagen count on both sides.** What the tenant pays for running costs is income. The running costs the landlord pays are Werbungskosten. The return shows both (Section 10).
- **Cash basis.** Rent is income of the calendar year in which it is received. Costs are deducted in the year in which they are paid. Regularly recurring items paid shortly before or after the turn of the year count in the year they belong to. Rent RECEIVED in advance for the use of property for more than five years MAY be spread evenly over the period it covers: a choice (§ 11(1) sentence 3 EStG). Costs PAID in advance for such use for more than five years MUST be spread over that period (§ 11(2) sentence 3 EStG). See § 11 EStG at https://www.gesetze-im-internet.de/estg/__11.html
- **VAT, if the let is taxed** (Section 9.4). The 2025 return instructions treat VAT received as rental income (line 27) and have the input VAT on building costs and on spread maintenance costs entered as a cost (lines 80 to 82).

Net rental income is added to all other income and taxed under the tariff (see Income Tax Rates above).

### Conservative Defaults

| Ambiguity | Default |
| --- | --- |
| Unknown completion date of the building (Fertigstellung) | STOP. The depreciation rate depends on it |
| Unknown Grundstücksanteil (land share of the price) | STOP. Land is not depreciable |
| Unknown whether Erhaltungsaufwand or Herstellungskosten | Treat as Herstellungskosten (capitalise, do not deduct at once) |
| Unknown ratio of the rent to the local market rent | STOP. It decides whether costs are cut |
| Unknown whether the building is used for housing | Ask. For a privately held building the depreciation rate in Section 2.1 does not depend on it, but § 21(2), § 7(5a), § 7b and § 82b EStDV apply only to housing |
| Unknown whether the property is a private or a business asset | STOP. A business asset is outside this Guide |

## Section 2: AfA Depreciation (§ 7 Abs. 4 EStG)

### 2.1 Linear AfA Rates

The rate depends on when the building was COMPLETED, not on when the client bought it. The base is the building's acquisition or production cost. The same rules apply to condominiums and to parts of a building that are separate assets (§ 7(5b) EStG).

| Building | AfA rate per year | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__7.html |
| Completed after 31 December 2022 | 3% | § 7(4) sentence 1 no. 2(a) EStG: "nach dem 31. Dezember 2022 fertiggestellt worden sind, jährlich 3 Prozent" |
| Completed before 1 January 2023 and after 31 December 1924 | 2% | § 7(4) sentence 1 no. 2(b) EStG: "vor dem 1. Januar 2023 und nach dem 31. Dezember 1924 fertiggestellt worden sind, jährlich 2 Prozent". The rate for most existing rented homes |
| Completed before 1 January 1925 | 2.5% | § 7(4) sentence 1 no. 2(c) EStG: "vor dem 1. Januar 1925 fertiggestellt worden sind, jährlich 2,5 Prozent" |
| NOT a private letting case: a building that belongs to BUSINESS assets, is not used for housing, building application after 31 March 1985 | 3% | § 7(4) sentence 1 no. 1 EStG: "soweit sie zu einem Betriebsvermögen gehören und nicht Wohnzwecken dienen". Shown only so that it is not mixed up with the first row. Outside this Guide |

- **A privately held shop or office follows the three date rows.** The three date rows apply to every building that does not meet the business-asset row, whether it is used for housing or not. The legacy version of this Guide gave one rate for "commercial" buildings of any date. That rate is only for business assets.
- **Useful lives.** The statute prints rates, not useful lives. It prints years in one place: if the ACTUAL useful life is shorter than 33 years (first and last row), 50 years (second row) or 40 years (third row), depreciation that matches the actual useful life may be taken instead (§ 7(4) sentence 2 EStG). The 2025 return instructions add that this is for justified exceptional cases and that the shorter life must be proven to the tax office. They point to the finance ministry's letter of 22 February 2023 for the proof.
- **Older buildings on staged rates (§ 7(5) EStG).** A building that the owner built, or bought by the end of the year of completion, under a building application or purchase contract made before 1 January 2006 (housing; earlier cut-off dates for other buildings) may be on the older staged declining rates of § 7(5) EStG in place of the table above. The stages are printed in § 7(5) and in the 2025 return instructions under lines 33 to 35. ASK which method the past returns used before picking a rate from the table. Whether a change of method is allowed is not on the pages read: refer.
- **Acquired for free.** A person who got the building or flat for free uses the rate that would apply to the previous owner if that person still owned it (2025 return instructions, lines 33 to 35).

### 2.2 Degressive AfA (§ 7 Abs. 5a EStG)

In place of the straight-line rate for buildings completed after 2022, a declining-balance rate may be chosen for a building, so far as it is used for HOUSING:

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__7.html |
| Fixed rate on the remaining book value (Restwert) each year | 5% | § 7(5a) sentence 4 EStG: "Prozentsatz in Höhe von 5 Prozent vom jeweiligen Buchwert (Restwert)" |

All of these conditions must hold (§ 7(5a) EStG):

- The building is in Germany, another EU member state or an EEA state.
- The client built it, or bought it by the end of the year in which it was completed.
- If built: construction began after 30 September 2023 and before 1 October 2029. The start is the date in the notice of the start of construction (Baubeginnsanzeige) that state law requires. It is NOT the date of the building application. Where state law requires no such notice, the client must declare that the start was reported to the building authority of his own accord.
- If bought: the binding purchase contract was made after 30 September 2023 and before 1 October 2029.

Other points from the same paragraph: the first-year amount is cut by months (Section 2.4). No extraordinary write-down is allowed while this method is used. A switch to straight-line depreciation is allowed. After the switch, depreciation is worked out from the remaining value and the rate that fits the remaining useful life. The legacy version said the rule started with the "Bauantrag": the statute says the start of construction.

### 2.3 AfA Basis (Bemessungsgrundlage)

- **AfA Basis (Bemessungsgrundlage).** Purchase price plus acquisition side costs (the legacy list: Grunderwerbsteuer, notary, land register, and the broker if the buyer pays) = total acquisition cost. Split it between land and building. Only the building share (Gebäudeanteil) is depreciated. Land (Grund und Boden) is never depreciated. Side costs are part of acquisition cost under § 255(1) HGB: https://www.gesetze-im-internet.de/hgb/__255.html
- **How to split (Kaufpreisaufteilung).** The finance ministry says a total price for built-on land is split by the ratio of the market values of the land and of the building, and NOT by the residual method ("nicht nach der sogenannten Restwertmethode, sondern nach dem Verhältnis der Verkehrswerte oder Teilwerte"). Its free tool (Arbeitshilfe, version of March 2026) either makes the split or tests whether an existing split is plausible: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Berechnung-Aufteilung-Grundstueckskaufpreis.html
- **Methods seen in practice (legacy list).** 1. A split agreed in the purchase contract, if it is at arm's length. 2. The ministry's Arbeitshilfe. 3. An expert valuation (Gutachten). The Finanzamt may challenge a split if the building share looks too high.
- **Condominiums.** A maintenance reserve (Erhaltungsrücklage) bought together with the flat is NOT part of the depreciation base (2025 return instructions, lines 33 to 41).
- **Grants.** A grant received towards acquisition or production cost is taken off the depreciation base and entered in line 89 (2025 return instructions).
- **Own home turned into a let.** Depreciation must then be worked out for the first time (2025 return instructions).

### 2.4 AfA Start

- **AfA start and pro-rata rule.** Depreciation starts with acquisition or completion. In that first year the yearly amount is cut by one twelfth for each full month BEFORE the month of acquisition or completion (§ 7(1) sentence 4 EStG). § 7(5a) says this sentence applies to the declining-balance method. § 7(4), the straight-line rule for buildings, does not repeat the sentence, but the tax administration cuts the first year there too. The finance ministry's letter of 21 May 2025 on § 7b EStG shows straight-line depreciation under § 7(4) sentence 1 no. 2 in its example 7 and notes: "bei Fertigstellung nach dem 31. Januar wäre eine zeitanteilige Kürzung der linearen AfA im Jahr der Fertigstellung erforderlich". So do NOT take a full-year amount in the year of purchase or completion unless that was in January. The note speaks of completion because its example is a new build. § 7(1) sentence 4 names acquisition and production side by side. Only the old staged rates of § 7(5) EStG are taken in full in the first year (§ 7(5) sentence 3: "Absatz 1 Satz 4 gilt nicht"). See https://www.gesetze-im-internet.de/estg/__7.html and https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-05-21-anwendungsschreiben-7b-estg-neu.pdf?__blob=publicationFile&v=5
- **End.** Depreciation runs until the cost is fully written off (§ 7(4) sentence 1 EStG: "bis zur vollen Absetzung"), or until the property is sold (legacy text).

### 2.5 Special depreciation for new rental homes (§ 7b EStG)

On top of the normal depreciation in 2.1 or 2.2, extra depreciation may be claimed for NEW rental flats in the year of acquisition or production and the three years after it:

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__7b.html |
| Extra depreciation per year, of the assessment base, for four years | 5% | § 7b(1) EStG: "Sonderabschreibungen bis zu jährlich 5 Prozent der Bemessungsgrundlage" |
| NEW window (building application or building notice after 31 December 2022 and before 1 October 2029): cost per square metre of living space must not be more than this. A CLIFF: above it, no special depreciation at all | EUR 5,200 | § 7b(2) sentence 2 no. 2 EStG: "5 200 Euro je Quadratmeter Wohnfläche nicht übersteigen" |
| NEW window: the most that counts as assessment base per square metre. A cap on the base, not a cliff | EUR 4,000 | § 7b(3) no. 2 EStG: "maximal 4 000 Euro je Quadratmeter Wohnfläche" |
| OLD window (application or notice after 31 August 2018 and before 1 January 2022): cost cliff per square metre | EUR 3,000 | § 7b(2) sentence 2 no. 1 EStG: "3 000 Euro je Quadratmeter Wohnfläche nicht übersteigen" |
| OLD window: the most that counts as assessment base per square metre | EUR 2,000 | § 7b(3) no. 1 EStG: "maximal 2 000 Euro je Quadratmeter Wohnfläche" |

- **Conditions (all must hold).** The building work creates new flats that did not exist before. The flat is in an EU member state, or in a state that gives administrative assistance to the extent the statute requires (§ 7b(1) sentence 4). If bought, it is bought by the end of the year of completion, and then only the buyer can claim. The flat is let for housing, against payment, in the year of acquisition or production and the NINE years after it. Short-term accommodation of guests is not housing. For the new window the building must also meet the "Effizienzhaus 40" standard with sustainability class, proven by the "Qualitätssiegel Nachhaltiges Gebäude".
- **No application or notice between 1 January 2022 and 31 December 2022 qualifies.** The statute leaves that year out.
- **Last year for claims under the 2019 version.** § 52(15a) EStG: special depreciation under § 7b in the version of the law of 4 August 2019 can be claimed for the last time for assessment period 2026, even if the four years have not run out. The finance ministry's letter of 21 May 2025 (paragraph 16) confirms that this end date is for the OLD window, that is works with a building application or notice "nach dem 31. August 2018 und vor dem 1. Januar 2022". From assessment period 2027 nothing more can be claimed in those cases, even if the four years have not run out. § 52(15a) sets no such end date for the new window. See https://www.gesetze-im-internet.de/estg/__52.html and the letter in Sources.
- **It is taken back** with effect for the past if the flat is not let for housing for the ten years, if it is sold within that time and the gain is not taxed, or if later costs push the cost per square metre over the cliff within the three years after the year of acquisition or production (§ 7b(4) EStG).
- **After the four years.** Where the special depreciation was claimed, normal depreciation does not simply carry on. It is then worked out from the remaining value: for straight-line depreciation with the rate that fits the arithmetical remaining useful life, for the declining-balance method with its own rate (§ 7a(9) EStG; ministry letter of 21 May 2025, paragraph 66). Refer the computation.
- **EU de minimis rules.** For the new window they apply only to claimants with farming, business or self-employment income (§ 7b(5) sentence 2 EStG), so not to a private landlord. For the old window the 2025 return instructions treat the relief as de minimis aid and ask for a checklist from the ministry's letter of 21 May 2025.

## Section 3: Werbungskosten (Deductible Expenses)

Werbungskosten are costs to get, secure and keep the income (§ 9(1) EStG). Costs of a flat or room are deductible only if the client earns rent from it or intends to in future. Costs of a flat the client lives in, or lets somebody use for free, are not deductible (2025 return instructions, lines 33 to 84). See https://www.gesetze-im-internet.de/estg/__9.html

### 3.1 Fully Deductible Expenses

| Expense | German term | Notes |
| --- | --- | --- |
| Mortgage interest (Schuldzinsen) | Darlehenszinsen | Interest only. Principal repayment is NOT deductible. Deductible so far as the loan is economically linked to the let property (§ 9(1) sentence 3 no. 1 EStG). A loan discount (Damnum, Disagio) at market level is deductible when paid (§ 11(2) sentence 4 EStG) |
| AfA depreciation | Absetzung für Abnutzung | Rates in Section 2. § 9(1) sentence 3 no. 7 EStG, which also names the § 7b special depreciation |
| Property tax | Grundsteuer | § 9(1) sentence 3 no. 2 EStG: taxes on land, other public charges and insurance premiums, so far as they relate to a building that serves to earn income |
| Building insurance | Gebäudeversicherung | Fire, storm, water damage. Same provision |
| Landlord liability insurance | Haus- und Grundbesitzerhaftpflicht | Same provision |
| Property management | Hausverwaltung | Monthly management fees |
| Accountancy fees | Steuerberatungskosten | The part that relates to the rental income |
| Legal fees (tenancy disputes) | Rechtsanwaltskosten | Revenue legal costs |
| Advertising for tenants | Inseratskosten | Property portal, newspaper |
| Travel to the property | Fahrtkosten | Actual cost, or the flat rate per kilometre DRIVEN in the table below. The legacy version said "one way": see the note under that table |
| Bank account fees | Kontoführungsgebühren | For the rent account. The official example puts them in lines 76 to 78 of the 2025 form |
| Running costs passed on to the tenant | Umgelegte Kosten | Deductible, because the Umlagen received are income. Lines 73 to 75 of the 2025 form |
| Condominium charges (Hausgeld) not passed on to the tenant | Nicht umlagefähiges Hausgeld | Deductible, EXCEPT the part that goes into the maintenance reserve. See 3.3 |

**Travel by car**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/brkg_2005/__5.html |
| Flat rate per kilometre driven by car, in place of actual cost | 30 cents | § 5(2) BRKG: "beträgt die Wegstreckenentschädigung 30 Cent je Kilometer zurückgelegter Strecke" |

§ 9(1) sentence 3 no. 4a EStG allows the highest mileage rate of the federal travel cost act in place of actual cost, and § 9(3) EStG applies that rule to rental income. Every kilometre driven counts. If the property were the client's first place of activity (erste Tätigkeitsstätte), the commuting allowance of § 9(1) sentence 3 no. 4 EStG would apply instead, which counts the one-way distance only. When a let property is a first place of activity is not settled on the pages read: ask the accountant.

### 3.2 Erhaltungsaufwand vs Herstellungskosten

| Erhaltungsaufwand (Revenue Repair) | Herstellungskosten (Capital Improvement) |
| --- | --- |
| Keeps or restores the existing condition | Creates something new, extends the building, or improves it substantially beyond its original condition (§ 255(2) HGB) |
| Deductible at once as Werbungskosten | Must be capitalised and depreciated via AfA |
| Larger amounts may be spread evenly over two to five years (§ 82b EStDV, conditions below) | Added to the AfA basis |
| Painting, replacing a broken heating system like for like, fixing a roof leak | Adding a balcony, converting the attic, installing a lift |
| Replacing old windows with equivalent ones | Works that lift the flat or building to a higher standard. The 2025 return instructions say the standard is judged above all by the heating, sanitary and electrical installations and the windows |

- **Bought in a poor state.** Works after a purchase that restore parts which do not function and are essential for use (the instructions' examples: a defective heating system, a building made uninhabitable by water or fire) are ACQUISITION cost, not maintenance. So are works for a change of use done before the first use, for example turning a flat into an office (2025 return instructions, lines 55 to 72).
- **Spreading larger maintenance costs (§ 82b EStDV).** A choice, only for a building that is not a business asset and is used mainly for housing: the floor area of the rooms used for housing must be more than half of the total usable area. The cost is spread evenly over two to five years. If the building is sold, moved into a business or no longer used to earn income during that time, the rest is deducted in that year. Co-owners must all use the same period. See https://www.gesetze-im-internet.de/estdv_1955/__82b.html Separately, the 2025 return instructions allow the same spread whatever the use of the building for certain works in redevelopment areas and on listed buildings (§§ 11a and 11b EStG). Refer.

**Works soon after purchase (anschaffungsnahe Herstellungskosten)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__6.html |
| Repair and modernisation works carried out within THREE YEARS after the building was acquired become production cost of the building if their cost WITHOUT VAT is MORE THAN this share of the acquisition cost of the BUILDING | 15% | § 6(1) no. 1a EStG: "ohne die Umsatzsteuer 15 Prozent der Anschaffungskosten des Gebäudes übersteigen" |

- **15% Rule (Anschaffungsnahe Herstellungskosten).** Read every word of the row above. The test is a CLIFF, not an allowance: if the costs are over the limit, ALL of them are capitalised, not only the part above it. The costs of the whole three years are added together. They are counted without VAT. They are compared with the acquisition cost of the building only, not of the land (Section 2.3). Exactly at the limit is not over it. § 9(5) sentence 2 EStG applies the rule to rental income.
- **Not counted** (§ 6(1) no. 1a sentence 2 EStG): costs of extensions, which are production cost anyway, and maintenance work that usually comes up every year. The 2025 return instructions give servicing costs as the example.
- **Consequence.** The costs are added to the building's depreciation base and written off at the building's rate. Costs that would otherwise be maintenance are caught too.

### 3.3 Non-Deductible Items

| Item | Reason |
| --- | --- |
| Principal repayments (Tilgung) | Loan repayment, not an expense |
| Grunderwerbsteuer (on acquisition) | Part of acquisition cost, so it goes into the split in Section 2.3 |
| Contributions to the owners' community's maintenance reserve (Erhaltungsrücklage) | Not deductible when paid in. Deductible only when the community spends the money on maintenance (2025 return instructions, lines 55 to 72). The legacy version did not say this |
| Costs of a flat the client lives in or lets someone use for free | No rental income from it |
| The unpaid part of a cheap let | See Section 4 |
| Private living costs | Not related to the rental activity |
| Fines and penalties (Bußgelder) | § 9(5) with § 4(5) no. 8 EStG |
| Income tax itself | Tax on income |

The legacy version listed the tenant-reimbursable part of the Hausgeld as non-deductible. That was wrong: the costs passed on are deducted, and the Umlagen received are declared as income (3.1 and Section 10).

## Section 4: Verbilligte Vermietung (Reduced-Rent Letting, § 21 Abs. 2 EStG)

The rule is about letting a HOME for living in. It applies to any tenant, but it mostly bites on lets to relatives.

**The two limits in the statute**

| Rent as a share of the local market rent | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__21.html |
| LESS THAN this share: the let is split into a paid part and an unpaid part. Costs are deductible only for the paid part | 50% | § 21(2) sentence 1 EStG: "weniger als 50 Prozent der ortsüblichen Marktmiete" |
| AT LEAST this share, for a home let on a permanent basis: the let counts as fully paid. All costs are deductible | 66% | § 21(2) sentence 2 EStG: "mindestens 66 Prozent der ortsüblichen Miete, gilt die Wohnungsvermietung als entgeltlich" |

For rent that is at least the lower share but less than the higher one, the statute prints no rule. The tax administration's instructions fill the gap:

**Between the two limits: the forecast test (instructions for the 2025 return)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025 |
| Lower end of the forecast band. Rent of AT LEAST this share, and less than the share in the next row, of the local market rent including running costs that can be passed on: costs need not be split ONLY IF no loss is expected over the period of the let. Reaching this share is NOT enough on its own | 50% | "Sie müssen die Aufwendungen nicht aufteilen, wenn das Entgelt mindestens 50 % , jedoch weniger als 66 % der ortsüblichen Marktmiete einschließlich umlagefähiger Kosten beträgt" |
| Upper end of the forecast band: rent of LESS THAN this share. Inside the band the surplus forecast (Überschussprognose) decides. At or above this share the instructions ask for no split and no forecast | 66% | "und im Zeitraum der Vermietung voraussichtlich kein Verlust erwirtschaftet wird (Überschussprognose" |

- **What is compared.** The instructions compare the agreed and paid rent INCLUDING the Umlagen paid with the local market rent INCLUDING the running costs that can be passed on. Comparing cold rent with cold rent, as the legacy example did, is not the official method.
- **If a split is needed.** Costs are split in the ratio of the agreed rent to the local market rent. On the 2025 form all costs are entered in full in lines 33 to 84. The percentage by which they are to be cut goes in line 87. If only part of the property is let cheaply, an amount goes in line 88. The tax office makes the cut.
- **If the forecast is negative.** The instructions state the forecast as a condition for not splitting. They do not spell out the opposite case in so many words. The forecast itself follows paragraph 33 onward of the ministry's letter of 8 October 2004, which could not be read on an allowed page. Refer the forecast to the accountant.
- **Ortsübliche Marktmiete.** In principle taken from the local rent index (Mietspiegel). If there is none, or it cannot be used, the instructions name three ways as examples ("zum Beispiel"), each with equal rank: a reasoned report by a publicly appointed and sworn expert (§ 558a(2) no. 3 BGB), information from a rent database (§ 558a(2) no. 2 with § 558e BGB), or the rents of at least three comparable flats (§ 558a(2) no. 4 BGB).
- **Not covered.** § 21(2) speaks only of a home let for living in, so cheap lets of commercial space are outside it. Its second sentence, the higher limit, speaks only of homes let on a permanent basis ("auf Dauer angelegter Wohnungsvermietung").

## Section 5: Möblierungszuschlag (Furnished Premium)

If a property is let furnished:

- A Möblierungszuschlag (furniture surcharge) can be charged as part of the rent. It is rental income.
- For the comparison in Section 4 the statute looks at the payment for letting the home and at the local market rent. No official page read for this Guide says how a furniture surcharge is brought into the local market rent. The legacy version offered two estimates (from the furniture's monthly depreciation, or a percentage uplift). They are removed, because no allowed official page supports them. Ask the accountant.
- The furniture itself is depreciated over its normal useful life under § 7(1) EStG. The 2025 return instructions give a fitted kitchen as the example (lines 42 to 45). The legacy version's ten-year life and yearly rate are on no official page read for this Guide and were removed.
- An item that can be used on its own may be deducted in full in the year it is bought if it costs no more than the limit below. § 9(1) sentence 3 no. 7 EStG applies the rule to rental income. The instructions put such items in lines 80 to 82.

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__6.html |
| Cost per item, less the VAT amount contained in it, must NOT be more than this. Per item. A choice, not a duty | EUR 800 | § 6(2) sentence 1 EStG: "für das einzelne Wirtschaftsgut 800 Euro nicht übersteigen" |

## Section 6: Transaction Pattern Library

Line numbers are those of Anlage V for 2025 (Section 10). "Relatives" means the separate lines for flats let to relatives.

### 6.1 Income Patterns (Credits)

| Pattern | Treatment | Notes |
| --- | --- | --- |
| MIETE, KALTMIETE, MONATSMIETE | Rental income (Einnahmen) | Base rent without Umlagen. Homes: lines 13 to 15. Other rooms: lines 16 to 18. Flats let to relatives: line 19 |
| NEBENKOSTEN, BETRIEBSKOSTEN, HAUSGELD (tenant portion) | Rental income | Umlagen received, always in full: line 20 (relatives: line 22). Pass-through costs are income AND expense |
| NACHZAHLUNG NEBENKOSTEN | Rental income | Back-payment from the yearly settlement: line 21 (relatives: line 23). A refund paid to the tenant goes in the same line with a minus sign |
| KAUTION, MIETKAUTION | EXCLUDE if refundable | Security deposit. It becomes taxable rent when it is kept and set off against unpaid rent, running costs or damage: line 25 |
| MÖBLIERUNGSZUSCHLAG | Rental income | Furniture premium. Part of the rent |
| UMSATZSTEUER (received, taxed lets only) | Rental income | Line 27 |

### 6.2 Expense Patterns (Debits)

| Pattern | Category | Anlage V Line | Notes |
| --- | --- | --- | --- |
| DARLEHENSZINSEN, HYPOTHEKENZINSEN, BANKZINSEN | Schuldzinsen | Lines 46 to 48 | Mortgage interest. Deductible so far as linked to the let property |
| GRUNDSTEUER | Grundsteuer | Lines 73 to 75 if passed on to the tenant, otherwise lines 76 to 78 | Municipal property tax |
| HAUSVERWALTUNG, VERWALTUNGSKOSTEN | Hausverwaltung | Lines 76 to 78 | Management fee, not passed on |
| GEBÄUDEVERSICHERUNG, WOHNGEBÄUDEVERSICHERUNG | Versicherung | Lines 73 to 75 if passed on, otherwise lines 76 to 78 | Building insurance |
| REPARATUR, INSTANDHALTUNG, HANDWERKER | Erhaltungsaufwand | Lines 55 to 72 | Revenue repairs. First check the rule for works soon after purchase (3.2) |
| MAKLERGEBÜHR (tenant search) | Maklerkosten | Lines 80 to 82 | Deductible when looking for a new tenant |
| HAUSGELD (nicht umlagefähig) | Verwaltungskosten | Lines 76 to 78 | Without the part that goes into the maintenance reserve (3.3) |
| HAUSGELD settlement with the property manager | Umgelegte Kosten | Lines 73 to 75 | Back-payment or refund from the yearly settlement, without the maintenance reserve |
| STEUERBERATER (Anlage V) | Steuerberatung | Lines 80 to 82 | Tax adviser fees for the rental income |
| GRUNDBUCH, NOTAR (mortgage) | Geldbeschaffungskosten | Lines 49 to 51 | Costs of raising the loan, if it finances the let property |
| GARTENPFLEGE, WINTERDIENST | Betriebskosten | Lines 73 to 75 if passed on, otherwise lines 76 to 78 | |
| FAHRTKOSTEN (to property) | Fahrtkosten | Lines 80 to 82 | Per kilometre driven, see the travel table in 3.1 |
| KONTOFÜHRUNG (rent account) | Kontoführungsgebühren | Lines 76 to 78 | As in the official example |

Of the rows above, the 2025 instructions name only these: loan interest (lines 46 to 48), costs of raising the loan (lines 49 to 51, the line only, not what belongs in it), maintenance (lines 55 to 72), the settlement with the property manager (lines 73 to 75) and, in the official example, account fees (lines 76 to 78). Lines 80 to 82 are for costs that fit none of lines 33 to 79. Every other row above (Grundsteuer, management fee, building insurance, broker, Hausgeld not passed on, tax adviser, land register and notary for the loan, garden and winter service, travel) is this Guide's reading of the line headings, not a quote. A management fee could equally sit in lines 80 to 82. All lines add up in line 83, so the choice of line does not change the result.

### 6.3 Exclusions

| Pattern | Treatment |
| --- | --- |
| TILGUNG, DARLEHENSRÜCKZAHLUNG | EXCLUDE. Principal repayment |
| GRUNDERWERBSTEUER (on purchase) | Add to acquisition cost. Not an immediate expense |
| INTERNAL TRANSFER, EIGENES KONTO | EXCLUDE |
| KAUTION RÜCKZAHLUNG | EXCLUDE. Deposit refund |
| ERHALTUNGSRÜCKLAGE (payment into the reserve) | EXCLUDE until the community spends it on maintenance |
| EINKOMMENSTEUER, KIRCHENSTEUER, SOLI | EXCLUDE. Personal taxes |

## Section 7: Verlustverrechnung (Loss Offset)

| Rule | Value or detail | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__10d.html |
| Horizontal loss offset | Rental losses offset other rental income of the same year | |
| Vertical loss offset | Rental losses offset OTHER kinds of income (employment, self-employment) of the same year | This happens inside the sum of income, § 2(3) EStG |
| Loss carry-back (Verlustrücktrag), single assessment | EUR 1,000,000 | § 10d(1) EStG: "bis zu einem Betrag von 1 000 000 Euro". First to the year immediately before. What cannot be used there goes to the second year before. The legacy version said one year |
| Loss carry-back, jointly assessed spouses | EUR 2,000,000 | § 10d(1) EStG: "bis zu einem Betrag von 2 000 000 Euro". Per couple |
| Waiving the carry-back | On request, and only as a whole | § 10d(1) sentence 6 EStG: "insgesamt abzusehen" |
| Loss carry-forward (Verlustvortrag): share of the total income ABOVE the base that may be offset in a year | 70% | § 10d(2) EStG: "bis zu 70 Prozent des 1 Million Euro übersteigenden Gesamtbetrags der Einkünfte". No time limit. Up to the base the offset is unlimited. The statute prints the base in words: one million euros, and two million euros for jointly assessed spouses. This version applies from assessment period 2024 (§ 52(18b) EStG). The legacy version gave a lower share |
| Remaining loss carry-forward | Fixed by a separate notice at the end of each year | § 10d(4) EStG |
| Liebhaberei risk | Legacy text: if a property shows losses year after year with no realistic prospect of a surplus, the Finanzamt may treat it as a hobby and deny the deductions | No allowed page read for this Guide sets out this test. For a home let permanently at or above the higher share in Section 4, the statute treats the let as fully paid. Refer doubtful cases |

- **Limits on losses from certain schemes.** § 21(1) sentence 2 EStG applies § 15a and § 15b EStG (limited liability and tax deferral models) to rental income by analogy. Refer these cases.
- The ability to offset rental losses against salary income is a core feature of German property tax planning, above all in the early years, when depreciation plus loan interest often exceed the rent.

## Section 8: Worked Examples

The legacy version carried four examples with invented amounts. An amount in this library must be printed on an official page, and invented inputs are on none. Examples 1, 2 and 4 are therefore walk-throughs without amounts: the reader's own figures go in. Example 3 now uses the official example from the 2025 return instructions, with its amounts as printed.

### Example 1: Standard Residential Letting (Post-2022 Building)

**Input.** A flat completed after 31 December 2022, bought with one price for land and building, let all year at the market rent. The client pays loan interest, Grundsteuer, building insurance and a management fee.

1. Split the total acquisition cost between land and building (Section 2.3).
2. Depreciation: the building share times the rate in the first row of the table in 2.1. In the year of purchase, see Section 2.4 for the cut by months.
3. Income: the rent received plus the Umlagen received.
4. Costs: interest, depreciation, the running costs passed on, and the costs not passed on.
5. If costs are higher than income, the loss is set against the client's other income of the same year, for example salary (Section 7).

### Example 2: Older Building with Erhaltungsaufwand

**Input.** A building completed between 1925 and 2022, so the second row of the table in 2.1 applies. The heating system is replaced like for like. That is Erhaltungsaufwand.

1. If the building was bought in the last three years, run the test in Example 4 first. If the heating did not work when the building was bought and is essential for use, the cost is acquisition cost (3.2).
2. Otherwise the cost is deductible in the year it is paid.
3. Choice: if the building is not a business asset and is used mainly for housing, the client may spread a larger cost evenly over two to five years (§ 82b EStDV). Each year then takes an equal part. The spread amounts go in the maintenance lines of Anlage V (lines 55 to 72 of the 2025 form).
4. If the building is sold during that time, the rest is deducted in the year of sale.

### Example 3: Verbilligte Vermietung to Family Member

This is the official example from the 2025 return instructions. A couple let a flat cheaply to the wife's parents. All amounts are per month unless the row says otherwise.

| Step | Amount | Note |
| --- | --- | --- |
| Source | all figures below | https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025 |
| Agreed cold rent | EUR 270 | "beträgt die monatliche Kaltmiete 270 €" |
| Umlagen agreed and paid on top | EUR 150 | "(Umlagen) in Höhe von 150 €" |
| Local market rent without Umlagen | EUR 900 | "60 Quadratmeter mal 15 € je Quadratmeter = 900 €" |
| Local market rent plus running costs that can be passed on | EUR 1,050 | "900 € ortsübliche Marktmiete zuzüglich 150 € umlagefähige Kosten = 1.050 €" |
| Agreed rent plus Umlagen | EUR 420 | "270 € vereinbarte Miete zuzüglich 150 € umlagefähige Kosten = 420 €" |
| Paid share of the let | 40.00% | "vermieten die Wohnung zu 40,00 % entgeltlich (420 € / 1.050 € )". Below the lower limit in Section 4, so costs must be split |
| Unpaid share, entered in line 87 | 60.00% | "und zu 60,00 % unentgeltlich (prozentualer Kürzungsanteil)" |
| Rental income of the year (rent plus Umlagen), line 32 | EUR 5,040 | "Die Summe der Einnahmen in Höhe von 5.040 €" |
| Costs of the year, entered in full, line 83 | EUR 4,920 | "Die Summe der abzugsfähigen Werbungskosten in Höhe von 4.920 €" |
| Cut made by the tax office | EUR 2,952 | "kürzt die Summe der Werbungskosten in Höhe von 4.920 € (Zeile 83) von Amts wegen um 60,00 % (2.952 € )" |
| Costs allowed | EUR 1,968 | "berücksichtigt folglich nur 1.968 €" |
| Net rental income of the year in the tax assessment, both spouses together | EUR 3,072 | "jeweils 1.536 € (zusammen 3.072 € )" |

- **Same facts, rent between the two limits.** No split if no loss is expected over the period of the let. The forecast goes to the accountant (Section 4).
- **Same facts, rent at or above the higher limit.** No split. All costs are deductible.
- The legacy example compared cold rent with cold rent and said that a fixed share of the costs is deductible when the forecast fails. Neither point is on an official page read for this Guide.

### Example 4: Anschaffungsnahe Herstellungskosten (15% Rule)

**Input.** A property is bought. Within three years the client renovates the bathroom and the kitchen.

1. Find the acquisition cost of the BUILDING (Section 2.3). The land share does not count.
2. Add up the cost, WITHOUT VAT, of all repair and modernisation works carried out in the three years after the acquisition. Leave out extensions and the maintenance that usually comes up every year.
3. Compare the total with the share in the table in 3.2.
4. Over the limit: ALL of these costs are production cost. They are added to the building's depreciation base and written off at the building's rate, even if each job on its own would be Erhaltungsaufwand.
5. Not over the limit: judge each job under the normal rules in 3.2.
6. The test looks at the three years together, so costs already deducted in an earlier year are affected when a later job tips the total over the limit. How the earlier assessment is corrected is for the accountant.

## Section 9: Edge Cases

### 9.1 Leerstand (Vacancy)

- **Vacancy deduction rule.** Official wording: costs of a flat are Werbungskosten only if the client earns rent from it or intends to earn rent from it in future (2025 return instructions, lines 33 to 84). Legacy practice note, not from an official page: keep evidence of the intention to let again, such as a listing on a property portal, an agent's mandate and a reasonable asking rent. A long vacancy with no sign of marketing may lead the Finanzamt to deny the costs.

### 9.2 Ferienwohnung (Holiday Let)

- **Holiday let special rules.** Holiday flats and other short-term lets need Anlage V-FeWo as well as Anlage V. The form asks for the days of own use, of letting and of vacancy. Days of own use include days on which the flat was left to others for free. Short stays for servicing, cleaning, renovation or a general check do not count as own use.
- **Own use possible at any time.** Vacancy days are split, by estimate, in the ratio of actual own use to actual letting.
- **Own use limited to set times** (for example when an agent does the letting): only the reserved time counts as own use, and vacancy counts as letting time.
- **Never used by the owner.** If the flat is let only to changing holiday guests and kept ready for them the rest of the time, the form asks for the letting days that are usual in that place.
- The instructions point to the ministry's letter of 8 October 2004 for further details. That letter could not be read on an allowed page, so this Guide does not say when the tax office tests the intention to make a surplus on a holiday flat. Refer holiday homes with own use. Source for this section: https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025

### 9.3 Spekulationssteuer (10-Year Rule)

- **10-year speculation tax rule.** Selling land, a building or a flat is a private sale (privates Veräußerungsgeschäft) if the time between acquisition and sale is NOT MORE THAN ten years (§ 23(1) sentence 1 no. 1 EStG). After that the sale is outside § 23. Buildings put up, extended or fitted out within the period are included. See https://www.gesetze-im-internet.de/estg/__23.html
- **Own-use exception, in the statute's words.** Outside the rule are assets that were used ONLY for the owner's own housing between acquisition or completion and sale, OR were used for the owner's own housing in the year of sale and the two years before it. A flat that was let right up to the sale meets neither test. The legacy version put the second test as two full calendar years plus the year of sale: the statute does not say "full".
- **Depreciation raises the gain.** The gain is the sale price less the acquisition or production cost and less the income-related costs (Werbungskosten) of the sale (§ 23(3) sentence 1 EStG). The cost is REDUCED by the depreciation, increased deductions and special depreciation that were deducted from rental income (§ 23(3) sentence 4 EStG). So every euro of AfA claimed comes back as gain on a sale within the period.
- **Acquired for free.** For a person who got the property for free as a single successor (the statute's word is "Einzelrechtsnachfolger", as with a gift), the previous owner's acquisition counts (§ 23(1) sentence 3 EStG). The sentence does not name heirs: ask the accountant.
- **The yearly limit is a cliff, not an allowance.** See the table. At the limit or above it, the whole gain is taxed. The gain is taxed under the normal tariff.
- **On a sale, also check:** the rest of a spread maintenance cost (3.2), and whether § 7b special depreciation is taken back (2.5).

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__23.html |
| Gains stay tax-free only if the total gain from all private sales in the calendar year is LESS THAN this | EUR 1,000 | § 23(3) sentence 5 EStG: "weniger als 1 000 Euro betragen hat" |

This is not a rental income issue but is often relevant. Loss rules and other private sales are in `de-capital-gains`.

### 9.4 Umsatzsteuer (VAT) on Commercial Lettings

- **Letting is VAT-exempt.** The letting of land and buildings is exempt (§ 4 no. 12 sentence 1 letter a UStG). NOT exempt: rooms kept ready for the short-term accommodation of guests, parking spaces for vehicles, short-term letting on campsites, and fixtures that are operating equipment (§ 4 no. 12 sentence 2). See https://www.gesetze-im-internet.de/ustg_1980/__4.html
- **VAT on commercial lettings.** The landlord may waive the exemption and charge VAT if the let is to another business for its business (§ 9(1) UStG). For lets of land this is allowed only so far as the tenant uses, or intends to use, the property ONLY for sales that do not rule out input VAT deduction. The landlord must prove this (§ 9(2) UStG). A tenant whose own sales rule out input VAT deduction blocks the option for that space. A let to a private tenant cannot be taxed, because § 9(1) needs a tenant that is a business. See https://www.gesetze-im-internet.de/ustg_1980/__9.html
- **Old buildings.** § 9(2) does not apply to certain buildings that were started before 1 June 1984 or before 11 November 1993 and completed before the dates in § 27(2) UStG. See https://www.gesetze-im-internet.de/ustg_1980/__27.html
- **Effect (legacy text).** A landlord who opts can recover input VAT on building and renovation costs. For the income tax return see the VAT bullet in Section 1.
- VAT returns, the small-business rule and short-term lets that are taxed are outside this Guide: see `germany-vat-return`.

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ustg_1980/__12.html |
| Standard VAT rate, on the net rent of a taxed let | 19% | § 12(1) UStG: "Die Steuer beträgt für jeden steuerpflichtigen Umsatz 19 Prozent der Bemessungsgrundlage" |

## Section 10: Anlage V Key Lines

Line numbers of Anlage V for the 2025 return, as the official instructions print them. The legacy version carried the line numbers of an older form, and every one of them has moved. Check the 2026 form when it is published. Source: https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025

| Zeile | Content |
| --- | --- |
| Zeile 6 | File number from the property tax base notice (Grundsteuermessbescheid) |
| Zeile 7 and 8 | Dates: purchase contract and transfer of ownership, or completion. Line 8: sale or transfer of the property |
| Zeile 10 | Kind of use. A holiday flat or short-term let also needs Anlage V-FeWo |
| Zeile 11 and 12 | Living space, and the part used by the owner, left to others for free or used as a holiday flat |
| Zeile 13 to 15 | Mieteinnahmen für Wohnungen (rent for homes, without Umlagen) |
| Zeile 16 to 18 | Rent for other rooms, without Umlagen and VAT |
| Zeile 19 | Rent for flats let to relatives, without Umlagen |
| Zeile 20 to 24 | Umlagen and Nebenkosten received. Line 21: back-payment or refund from the yearly settlement. Lines 22 and 23: relatives |
| Zeile 25 to 28 | Other income: deposit kept (line 25), sites let for antennas and the like (line 26), VAT received (line 27) |
| Zeile 29 to 31 | Grants from public funds for maintenance, and cost subsidies |
| Zeile 32 | Total income |
| Zeile 33 to 35 | AfA für Gebäude (§ 7(4) to (5a) EStG) |
| Zeile 36 to 38 | Special depreciation under § 7b EStG |
| Zeile 39 to 41 | Increased deductions under §§ 7h and 7i EStG |
| Zeile 42 to 45 | AfA for assets that are not buildings (furniture, fitted kitchen) |
| Zeile 46 to 48 | Schuldzinsen (loan interest) |
| Zeile 49 to 51 | Geldbeschaffungskosten (costs of raising the loan) |
| Zeile 55 to 72 | Erhaltungsaufwendungen (maintenance), including amounts spread over two to five years |
| Zeile 73 to 75 | Running costs passed on to the tenants |
| Zeile 76 to 78 | Running costs not passed on to the tenants |
| Zeile 80 to 82 | Other costs, low-cost items deducted at once, and input VAT of a taxed let |
| Zeile 83 | Total deductible Werbungskosten |
| Zeile 85 and 86 | Surplus or loss, and how it is shared between spouses or co-owners |
| Zeile 87 and 88 | Cheap let: percentage cut (line 87) or amount of the cut (line 88) |
| Zeile 89 | Grants towards acquisition or production cost |

## PROHIBITIONS

- NEVER depreciate the land share (Grundstücksanteil). Only the building is depreciable.
- NEVER pick the depreciation rate by the purchase date. It follows the completion date of the building (Section 2.1).
- NEVER use the business-asset rate for a privately held building, whatever it is used for.
- NEVER deduct mortgage principal repayments (Tilgung). Only interest is deductible.
- NEVER deduct at once the repair and modernisation costs of the first three years when they are over the limit in 3.2. All of them must be capitalised.
- NEVER allow full Werbungskosten for a home let below the lower limit in Section 4. Split them.
- NEVER deduct payments into a condominium's maintenance reserve before the money is spent.
- NEVER tell a client that a sale is tax-free without checking the ten-year period and the depreciation already claimed (Section 9.3).
- NEVER ignore the Liebhaberei risk for properties with lasting losses and no surplus in sight.
- NEVER present rental income computations as definitive. Always label them as estimated.

## The method, step by step

1. Check that the income is rental income from private assets under § 21 EStG. Property held in a business, and income that belongs to another kind of income, is outside (§ 21(3)). https://www.gesetze-im-internet.de/estg/__21.html
2. Pick the forms: Anlage V for each built-on property, plus Anlage V-FeWo for a holiday flat or short-term let, or Anlage V-Sonstige for shares in a community, subletting or land without buildings. https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025
3. Add up what was received in the calendar year: rent, Umlagen, settlement back-payments, deposits kept, VAT received (§ 11 EStG, cash basis). https://www.gesetze-im-internet.de/estg/__11.html
4. Fix the depreciation base. Split the total acquisition cost between land and building, using the ministry's tool or to test an agreed split. https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Berechnung-Aufteilung-Grundstueckskaufpreis.html
5. Pick the depreciation rate by the building's completion date under § 7(4) EStG. Check whether the declining-balance method of § 7(5a) is open, and cut the first year by months where Section 2.4 says so. https://www.gesetze-im-internet.de/estg/__7.html
6. For a new-build flat, test the special depreciation of § 7b EStG: window, cost cliff, base cap, ten years of letting for housing. For the old window, 2026 is the last year. https://www.gesetze-im-internet.de/estg/__7b.html
7. Sort building costs into maintenance and production cost. For a building bought in the last three years, run the test of § 6(1) no. 1a EStG over all three years together, without VAT, against the building's cost. https://www.gesetze-im-internet.de/estg/__6.html
8. For larger maintenance costs on a mainly residential building, decide whether to spread them over two to five years under § 82b EStDV. https://www.gesetze-im-internet.de/estdv_1955/__82b.html
9. List the other Werbungskosten paid in the year: interest, property tax, insurance, management, travel, costs passed on and not passed on (§ 9 EStG). Leave out payments into a maintenance reserve. https://www.gesetze-im-internet.de/estg/__9.html
10. For every home, compare the rent including Umlagen with the local market rent including running costs that can be passed on (§ 21(2) EStG). Below the lower limit, enter the cut in line 87 (2025 form). Between the limits, send the forecast to the accountant. https://www.gesetze-im-internet.de/estg/__21.html
11. Work out the surplus or loss for each property and share it between co-owners (lines 85 and 86 of the 2025 form). A loss is set against other income of the year. What is left goes back and then forward under § 10d EStG. https://www.gesetze-im-internet.de/estg/__10d.html
12. File with the income tax return by the dates in § 149 AO. https://www.gesetze-im-internet.de/ao_1977/__149.html
13. If the property was sold, or a sale is planned, test the ten-year period of § 23 EStG and add back the depreciation claimed. https://www.gesetze-im-internet.de/estg/__23.html

If the order is wrong, the result is wrong: the building share (step 4) must be fixed before the three-year test (step 7), because the test measures against the building's cost, and costs must be complete (step 9) before the cheap-let cut (step 10), because the cut applies to their total.

## Ask the client first

- When was the building completed, and when did you buy it (date of the contract and date ownership passed)? This sets the depreciation rate, the three-year window for works and the ten-year period for a sale. Which depreciation method and rate did past returns use?
- Do you hold the property privately or in a business? Is it used for housing?
- How was the price split between land and building, and who made the split?
- What rent and what Umlagen does the tenant pay, and what is the local market rent for a flat like this? Is the tenant a relative?
- What works have been done since the purchase, when, and what did they cost without VAT?
- Is it a holiday flat or a short-term let, do you ever use it yourself, and do you charge VAT on the rent?

## When to refuse or refer

- Property held in a business, a partnership that trades, or so many purchases and sales that the activity may be a trade (gewerblicher Grundstückshandel).
- Landlords who do not live in Germany, and property outside Germany (Anlage AUS, tax treaties).
- The surplus forecast for rent between the two limits in Section 4, and any case where the tax office doubts the intention to make a surplus.
- Holiday homes that the owner also uses, and short-term lets with hotel-like services, which may be a trade and may carry VAT.
- A claim that the building's actual useful life is shorter than the statute assumes (expert report, ministry letter of 22 February 2023).
- Special depreciation under § 7b EStG where the conditions are in doubt or the relief may be taken back, and increased deductions for listed buildings and redevelopment areas (§§ 7h, 7i EStG).
- Co-ownership with a separate determination of income, heirs' communities, closed property funds, usufruct (Nießbrauch) and heritable building rights (Erbbaurecht).
- Loss limits under § 15a and § 15b EStG (tax deferral models).
- How a furniture surcharge enters the market rent comparison (Section 5), and cheap lets of commercial space.
- The sale of a property: this Guide gives the ten-year rule only. The gain computation and the loss rules need an accountant. See also `de-capital-gains`.
- The VAT option beyond the basics in 9.4: input VAT corrections, mixed-use buildings, the small-business rule. See `germany-vat-return`.
- The income tax tariff, solidarity surcharge and church tax: see `de-einkommensteuer-freelancer`.

## Sources

- EStG § 21 (rental income, cheap letting): https://www.gesetze-im-internet.de/estg/__21.html
- EStG § 7 (depreciation): https://www.gesetze-im-internet.de/estg/__7.html
- EStG § 7b (special depreciation for new rental homes): https://www.gesetze-im-internet.de/estg/__7b.html
- EStG § 6 (works soon after purchase, low-cost items): https://www.gesetze-im-internet.de/estg/__6.html
- EStG § 9 (Werbungskosten): https://www.gesetze-im-internet.de/estg/__9.html
- EStG § 2 (kinds of income, surplus of receipts over costs): https://www.gesetze-im-internet.de/estg/__2.html
- EStG § 11 (cash basis): https://www.gesetze-im-internet.de/estg/__11.html
- EStG § 10d (loss carry-back and carry-forward): https://www.gesetze-im-internet.de/estg/__10d.html
- EStG § 23 (private sales): https://www.gesetze-im-internet.de/estg/__23.html
- EStG § 46 (assessment of employees): https://www.gesetze-im-internet.de/estg/__46.html
- EStG § 52 (application rules): https://www.gesetze-im-internet.de/estg/__52.html
- EStDV § 82b (spreading larger maintenance costs): https://www.gesetze-im-internet.de/estdv_1955/__82b.html
- HGB § 255 (acquisition and production cost): https://www.gesetze-im-internet.de/hgb/__255.html
- BRKG § 5 (mileage rate): https://www.gesetze-im-internet.de/brkg_2005/__5.html
- UStG § 4, § 9, § 12 and § 27 (VAT on letting): https://www.gesetze-im-internet.de/ustg_1980/__4.html and https://www.gesetze-im-internet.de/ustg_1980/__9.html and https://www.gesetze-im-internet.de/ustg_1980/__12.html and https://www.gesetze-im-internet.de/ustg_1980/__27.html
- AO § 149 (filing dates): https://www.gesetze-im-internet.de/ao_1977/__149.html
- Tax administration, instructions for the 2025 income tax return (Anlage V, Anlage V-FeWo), on ELSTER: https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025
- Finance ministry, tool for splitting a purchase price between land and building, version of March 2026: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Steuern/Berechnung-Aufteilung-Grundstueckskaufpreis.html
- Finance ministry, letter of 21 May 2025 on special depreciation under § 7b EStG: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-05-21-anwendungsschreiben-7b-estg-neu.pdf?__blob=publicationFile&v=5

## Disclaimer

This Guide and its outputs are provided for informational and computational purposes only and do not constitute tax, legal, or financial advice. Open Accountants and its contributors accept no liability for any errors, omissions, or outcomes arising from the use of this Guide. All outputs must be reviewed and signed off by a qualified professional (such as a Steuerberater or an equivalent licensed practitioner in your jurisdiction) before filing or acting upon.

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
