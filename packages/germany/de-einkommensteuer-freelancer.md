---
name: de-einkommensteuer-freelancer
description: Computes Einkommensteuer for Freiberufler including Betriebsausgaben, Sonderausgaben, and progressive tax brackets.
jurisdiction: DE
tax_year: 2026
last_updated: 2026-09-19
review_status: pending_review
drafted_by: OpenAccountants
approved_by: pending
tier: 2
license: AGPL-3.0-or-later (code) / OpenAccountants Guide License v1.0 (content)
---

# Income tax for the self-employed in Germany (Einkommensteuer for Freiberufler and Gewerbetreibende)

How Germany taxes the profit of one self-employed person: who is a Freiberufler and who runs a trade, how profit is found, the income tax tariff, the solidarity surcharge, the main deductions, loss relief, prepayments, the yearly return, and what a late return costs. It is for an individual who lives in Germany and works on their own account. Figures are for tax year 2026. Statute figures are read from the consolidated federal law pages; § 52(1) EStG says that text first applies for assessment period 2026. Two sources carry another year. The finance ministry's tax booklet is the 2025 edition, the latest: it gives the church tax range and the marginal rates as percentages. ELSTER's instructions are those for the 2025 return, the latest published: they give the form names. The 2026 pension cap is from the pension insurer's page of 20 April 2026, because the statute prints no amount.

## Section 1: Quick Reference

| Field | Value |
| --- | --- |
| Country | Germany |
| Tax | Einkommensteuer (income tax), a yearly tax on the calendar year (§ 2(7) EStG). Solidarity surcharge and church tax come on top (Section 6) |
| Who this Guide covers | One individual, resident in Germany, with income from self-employed work (§ 18 EStG) or from a trade (§ 15 EStG) |
| Profit method | Cash-basis EÜR (§ 4(3) EStG) or balance sheet (§ 4(1), § 5 EStG). Section 3 |
| Tariff | Five zones in § 32a(1) EStG. Section 5 |
| Trade tax | Only a trade pays it. Part is credited against income tax (§ 35 EStG). Sections 2 and 13 |
| Return | Electronic: ESt 1 A, Anlage S or Anlage G, Anlage EÜR, Anlage Vorsorgeaufwand. Section 11 |
| Tax authority | Local Finanzamt |
| Status | Drafted from the official pages. No accountant has reviewed it yet |

## Section 2: Freiberufler or Gewerbetreibender

The split decides trade tax, the registration route and the bookkeeping duty. It does not change the income tax tariff.

- **Freiberufler (§ 18(1) no. 1 EStG).** Self-employed scientific, artistic, writing, teaching or educational work, and the professions the law names: doctors, dentists, vets, lawyers, notaries, patent attorneys, surveyors, engineers, architects, commercial chemists, auditors, tax advisers, consulting economists and business economists, sworn accountants, tax agents, Heilpraktiker, Dentisten, physiotherapists (Krankengymnasten), journalists, photo reporters, interpreters, translators, ship pilots (Lotsen) "und ähnlicher Berufe" (and similar professions). See https://www.gesetze-im-internet.de/estg/__18.html
- **Staff.** A Freiberufler may use qualified staff, but must lead the work and answer for it through their own expertise (§ 18(1) no. 1 sentence 3 EStG).
- **Other self-employed work (§ 18(1) no. 3 EStG).** For example fees as an executor, asset manager or supervisory board member. Same type of income, same form.
- **Gewerbetreibender (§ 15(2) EStG).** A trade is an independent, lasting activity, carried on for profit and taking part in general economic life, that is not farming, not a liberal profession and not other self-employed work. Trade is what is left over. See https://www.gesetze-im-internet.de/estg/__15.html
- **Jobs the list does not name.** Whether a job is a "similar profession" is decided case by case. The official pages read for this Guide do not list such jobs. Refer it (last section).

| Point | Freiberufler (§ 18 EStG) | Gewerbetreibender (§ 15 EStG) |
| --- | --- | --- |
| Trade tax | None. Only a trade is subject to it (§ 2(1) GewStG) | Yes, above the allowance below. Credited in part against income tax (Section 13) |
| Registration (§ 138 AO) | Tell the tax office within one month of starting | Tell the municipality within one month of opening; it informs the tax office |
| Start-up details (§ 138(1b) AO) | Sent electronically to the tax office | The same |
| Bookkeeping duty by size (§ 141 AO) | None. § 141 AO names commercial businesses and farmers only | Can start once a limit below is crossed and the tax office has given notice |
| Profit method | EÜR at any size, unless books are kept by choice | EÜR as long as no law demands books and none are kept |
| Form for the profit | Anlage S | Anlage G |

**Trade tax allowance**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__11.html |
| Allowance taken off the trade income of individuals and partnerships, per business per year | EUR 24,500 | § 11(1) GewStG: "um einen Freibetrag in Höhe von 24 500 Euro" |

It is an allowance, not a cliff: only trade income above it is taxed. The rest of trade tax is in `de-trade-tax`.

**Tax-law bookkeeping duty for a trade**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__141.html |
| Total turnover of the single business in the calendar year: the duty can start above | EUR 800,000 | § 141(1) no. 1 AO: "von mehr als 800 000 Euro im Kalenderjahr" |
| Profit from the trade in the financial year: the duty can start above | EUR 80,000 | § 141(1) no. 4 AO: "einen Gewinn aus Gewerbebetrieb von mehr als 80 000 Euro im Wirtschaftsjahr" |

- **Either limit is enough** ("or"). The duty starts only with the financial year after the tax office's notice (§ 141(2) AO).
- **Other laws count too.** Whoever must keep books under another law, for example a merchant under the Handelsgesetzbuch, must do so for tax as well (§ 140 AO). See `germany-bookkeeping`.

## Section 3: How profit is found

For a trade and for self-employed work the taxed income is the profit (§ 2(2) EStG).

| Criterion | EÜR (§ 4(3) EStG) | Balance sheet (§ 4(1), § 5 EStG) |
| --- | --- | --- |
| Who | Anyone not bound by law to keep books who also keeps none. Always open to a Freiberufler | Traders bound to keep books, and anyone who keeps books by choice |
| Profit is | Business receipts less business expenses | The change in business net assets over the year, plus withdrawals, less contributions |
| Timing | Cash basis: receipts when they arrive, expenses when paid (§ 11 EStG) | Accruals |
| Sent as | Anlage EÜR, electronically (§ 60(4) EStDV) | Balance sheet and P&L, electronically (§ 5b EStG) |

- **Year end.** Regularly recurring receipts and payments that arrive a short time before or after the year end count in the year they belong to (§ 11 EStG).
- **The EÜR is not pure cash.** Depreciation and the low-value asset rules must be followed. The cost of fixed assets that do not wear out, of shares, of securities, and of land and buildings held as current assets counts only when the sale proceeds arrive or the asset is withdrawn. Fixed assets go into a running register. Money collected and paid out in another's name and for their account is left out. See https://www.gesetze-im-internet.de/estg/__4.html
- **One Anlage EÜR per business**, with the fixed asset schedule (Anlage AVEÜR) as a necessary part. Paper only in hardship cases. See the ministry letter of 1 September 2026 at https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2
- **Never deductible.** Income tax and other personal taxes (§ 12 no. 3 EStG) and trade tax (§ 4(5b) EStG).

Records, the chart of accounts and the limits on gifts and entertainment are in `germany-bookkeeping`.

## Section 4: From profit to taxable income

§ 2 EStG sets the order. See https://www.gesetze-im-internet.de/estg/__2.html

1. Work out the income of each type: profit for a trade or self-employed work; receipts less expenses for a job, letting and the rest.
2. Add them up and take off a few personal reliefs: the total income (Gesamtbetrag der Einkünfte, § 2(3)).
3. Take off loss deductions (Section 9), special expenses (Section 8) and extraordinary burdens: the income (Einkommen, § 2(4)).
4. Take off child allowances and other amounts: the taxable income (zu versteuerndes Einkommen, § 2(5)). The tariff works on this number, not on turnover or profit.
5. Apply the tariff (Section 5) and take off tax reductions such as the trade tax credit (Section 13): the income tax to be assessed (§ 2(6)).
6. Prepayments and tax withheld are credited. The rest is due within one month of the assessment notice; a part that matches overdue prepayments is due at once (§ 36(4) EStG). See https://www.gesetze-im-internet.de/estg/__36.html

Flat-taxed investment income stays outside this chain (§ 2(5b) EStG). See `de-capital-gains`.

## Section 5: The 2026 tariff (§ 32a EStG)

Five zones of taxable income, each with a formula. The law says it applies "ab dem Veranlagungszeitraum 2026". Boundaries are for one person assessed alone.

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__32a.html |
| Zone 1, basic allowance (Grundfreibetrag): no tax on taxable income up to | EUR 12,348 | § 32a(1) no. 1: "bis 12 348 Euro (Grundfreibetrag): 0" |
| Zone 2 starts at | EUR 12,349 | no. 2: "von 12 349 Euro bis 17 799 Euro: (914,51 • y + 1 400) • y" |
| Zone 2 ends at | EUR 17,799 | Same line |
| Zone 3 starts at | EUR 17,800 | no. 3: "von 17 800 Euro bis 69 878 Euro: (173,10 • z + 2 397) • z + 1 034,87" |
| Zone 3 ends at | EUR 69,878 | Same line |
| Zone 4 starts at. From here the formula uses the factor 0.42 (printed as 0,42) | EUR 69,879 | no. 4: "von 69 879 Euro bis 277 825 Euro: 0,42 • x" |
| Zone 4 ends at | EUR 277,825 | Same line |
| Zone 5 starts at. From here the formula uses the factor 0.45 (printed as 0,45) | EUR 277,826 | no. 5: "von 277 826 Euro an: 0,45 • x" |

The formulas, in English notation (the statute prints a decimal comma and a space between thousands). The result is the income tax in euro.

~~~
Zone 1: tax = 0
Zone 2: tax = (914.51 * y + 1,400) * y
Zone 3: tax = (173.10 * z + 2,397) * z + 1,034.87
Zone 4: tax = 0.42 * x - 11,135.63
Zone 5: tax = 0.45 * x - 19,470.38
~~~

- **x** is the taxable income, rounded down to a full euro. **y** is one ten-thousandth of the part of x above the basic allowance. **z** is one ten-thousandth of the part of x above the end of zone 2.
- **Method.** Find the zone that holds x, work out y or z if needed, apply that zone's formula, round the tax down to a full euro. This Guide prints no worked amounts.
- **Joint assessment (splitting).** Spouses assessed together pay twice the tax that the tariff gives for half of their joint taxable income (§ 32a(5) EStG). The statute prints no doubled boundaries, so none are stated here. Spouses may choose it if both are fully liable to German tax and do not live apart for good (§ 26 EStG); registered partners are treated like spouses (§ 2(8) EStG). § 32a(6) EStG extends it to a widowed person for the year after the death, if the couple met the § 26 conditions when the spouse died.
- **Special rules can change the result:** § 32b (progression clause), § 32d (flat tax on investment income), § 34 (extraordinary income such as a gain on selling the business), § 34a (retained profits). They are outside this Guide.

**Marginal rates as percentages**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Entry rate: marginal rate on the first taxed euro | 14% | Booklet, 2025 edition: "Zonen von 14 Pro- zent (Eingangssteuersatz)" |
| Top rate: marginal rate through zone 4 | 42% | Booklet, 2025 edition: "bis auf 42 Prozent (Spitzensteuersatz) an" |
| Highest rate: marginal rate in zone 5 | 45% | Booklet, 2025 edition: "auf dann 45 Prozent (Reichensteuer)" |

The 2026 statute prints no percentages, only the two factors. The percentages are from the booklet's 2025 edition; its 2025 boundaries must not be used for 2026. They are marginal rates: each applies to the next euro, not to the whole income. Through zones 2 and 3 the marginal rate rises steadily from the entry rate to the top rate.

## Section 6: Solidarity surcharge and church tax

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__3.html |
| Single assessment: surcharge only if the income tax it is based on is more than | EUR 20,350 | § 3(3) no. 2 SolzG: "in anderen Fällen 20 350 Euro übersteigt" |
| Joint assessment (splitting): the same test, per couple | EUR 40,700 | § 3(3) no. 1 SolzG: "Einkommensteuergesetzes 40 700 Euro" |

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__4.html |
| Surcharge rate, charged on the income tax and not on the income | 5.5% | § 4 SolzG: "Der Solidaritätszuschlag beträgt 5,5 Prozent der Bemessungsgrundlage" |
| Cap: the surcharge is not more than this share of the amount by which the base exceeds the limit | 11.9% | § 4 SolzG: "Er beträgt nicht mehr als 11,9 Prozent des Unterschiedsbetrages" |

- **The limit is on the tax, not on the income.** The base is the assessed income tax, worked out with the child allowances taken off; for the limit test the tax on investment income under § 32d(3) and (4) EStG is left out.
- **A limit with a sliding zone, not an allowance.** Up to the limit there is no surcharge. Above it the surcharge is the rate on the whole base, but never more than the cap.
- **Year.** § 6(27) SolzG starts these limits in assessment period 2026; the ministry booklet prints lower 2025 limits. See https://www.gesetze-im-internet.de/solzg_1995/__6.html
- **Prepayments** carry the surcharge too (§ 3(1) no. 2 SolzG).

**Church tax**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Church tax for members, charged on the income tax and not on the income | 8% or 9% | Booklet, 2025 edition: "beträgt je nach Bundesland 8 oder 9 Prozent" |

The rate depends on the federal state and is set by church tax rules that are not on the federal pages. Its base is the income tax worked out with the child allowances taken off in every case and without the trade tax credit of § 35 EStG (§ 51a(2) EStG), so that credit does not lower a trader's church tax. See https://www.gesetze-im-internet.de/estg/__51a.html Church tax paid is a special expense (§ 10(1) no. 4 EStG), except on flat-taxed investment income. The official pages print no combined rate of income tax, surcharge and church tax, so none is stated here.

## Section 7: Business expenses a freelancer meets

Business expenses are the costs caused by the business (§ 4(4) EStG). § 4(5) EStG limits some. The costs of a home office room, gifts and entertainment must be recorded one by one and apart from other expenses, or the deduction is lost (§ 4(7) EStG).

**Working from home**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__4.html |
| Room that is the centre of all business and professional work: yearly flat amount in place of the actual costs | EUR 1,260 | § 4(5) no. 6b: "pauschal ein Betrag von 1 260 Euro (Jahrespauschale)" |
| Day rate for each calendar day worked mainly at home | EUR 6 | § 4(5) no. 6c: "ein Betrag von 6 Euro (Tagespauschale)" |
| Yearly cap on the day rates | EUR 1,260 | § 4(5) no. 6c: "höchstens 1 260 Euro im Wirtschafts- oder Kalenderjahr" |

- **Room is the centre.** Actual room costs, or the flat amount in their place. The flat amount falls by one twelfth for each full month in which the room is not the centre.
- **Room is not the centre.** No room costs at all; only the day rate is left.
- **Day rate.** For a calendar day on which the work is done mainly at home and no first place of work outside the home is visited. No separate room is needed. If no other workplace is available for good, it is also allowed on a day with work away or at the first place of work.
- **One rate per day** for the whole business and professional activity of the person. No day rate so far as room costs under no. 6b, or the home's costs within a second household, are deducted.

**Trips to the business premises, and meals on business trips**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__9.html |
| Commuting allowance per full kilometre of the one-way distance, per working day on which the premises are visited | EUR 0.38 | § 9(1) sentence 3 no. 4: "von 0,38 Euro anzusetzen, höchstens jedoch 4 500 Euro im Kalenderjahr" |
| Yearly cap. Not so far as the person uses their own car or a car provided to them | EUR 4,500 | § 9(1) sentence 3 no. 4: "höchstens jedoch 4 500 Euro im Kalenderjahr" |
| Meals in Germany: calendar day with 24 hours away | EUR 28 | § 9(4a) no. 1: "28 Euro für jeden Kalendertag" |
| Meals in Germany: day of arrival and day of departure of a trip with an overnight stay, each | EUR 14 | § 9(4a) no. 2: "jeweils 14 Euro für den An- und Abreisetag" |
| Meals in Germany: day without an overnight stay, more than eight hours away | EUR 14 | § 9(4a) no. 3: "14 Euro für den Kalendertag, an dem der Arbeitnehmer ohne Übernachtung" |

- **The employee rules apply to the owner.** § 4(5) no. 6 EStG applies the commuting allowance to trips between home and the business premises; § 4(5) no. 5 EStG applies the meal amounts to business trips.
- **One rate from the first kilometre.** Older material shows a lower rate for the first twenty kilometres; the 2026 text has a single rate. One-way distance, not the round trip. Not for flights.
- **Business car.** If these trips are made in a car that is a business asset, its costs are already business expenses. § 4(5) no. 6 sentence 3 EStG then adds back the part above the commuting allowance, measured by the list price method or, where private use is found by logbook or by the actual share, by the actual costs of these trips. `germany-bookkeeping` describes the list price method and the logbook, not this add-back.
- **Meals.** Only the flat amounts count, never the real bill for one's own meal. Eight hours or less gives nothing. At the same place of work they stop after three months. Abroad, country amounts set by the ministry apply.
- **Business trips by car** are not commuting: every kilometre driven counts. For a private car used for the business, the ministry's instructions for the 2026 EÜR form allow either the share of the actual costs or a flat 30 cents for each full kilometre. That is the higher of the two mileage rates the federal travel cost act prints for a car, the one in its § 5(2): https://www.gesetze-im-internet.de/brkg_2005/__5.html § 9(1) sentence 3 no. 4a EStG gives employees the highest rate of that act; § 4(5) EStG does not apply that number to the owner, so for the owner the flat rate rests on the instructions. The instructions print it for a private car only. Private use of a business car is in `germany-bookkeeping`.

**Equipment: low-value assets (GWG)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__6.html |
| A movable fixed asset that wears out and can be used on its own may be expensed in full in the year of purchase if its cost, less any input VAT contained in it, is not more than | EUR 800 | § 6(2): "für das einzelne Wirtschaftsgut 800 Euro nicht übersteigen" |
| Such an asset goes into a special running register if its value is more than | EUR 250 | § 6(2) sentence 4: "deren Wert 250 Euro übersteigt" |

Tested asset by asset; a choice, not a duty. § 6(2a) EStG offers a yearly pool in its place (see `germany-bookkeeping`). Everything else is depreciated evenly over its useful life, by months in the year of purchase (§ 7(1) EStG). For movable fixed assets bought after 30 June 2025 and before 1 January 2028, falling yearly amounts are allowed (§ 7(2) EStG). See https://www.gesetze-im-internet.de/estg/__7.html

**Investment deduction and special depreciation (§ 7g EStG)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__7g.html |
| Share of the expected cost of a future movable fixed asset that may be taken off profit in advance | 50% | § 7g(1): "bis zu 50 Prozent der voraussichtlichen Anschaffungs- oder Herstellungskosten" |
| Profit limit: only if the profit of that year, before the deduction, is not more than | EUR 200,000 | § 7g(1) sentence 2 no. 1(b): "200 000 Euro nicht überschreitet" |
| Cap on the sum of open deductions of the year and the three years before, per business | EUR 200,000 | § 7g(1) sentence 4: "darf je Betrieb 200 000 Euro nicht übersteigen" |
| Special depreciation on top of normal depreciation, in total over the year of purchase and the four years after | 40% | § 7g(5): "Sonderabschreibungen bis zu insgesamt 40 Prozent der Anschaffungs- oder Herstellungskosten" |

- **The profit limit is a cliff**, for EÜR and balance sheet businesses alike. The cap in the third row is a different rule with the same number.
- **Three years to invest.** If the asset is not bought by the end of the third financial year after the deduction, the deduction is undone in the year it was taken and that assessment is changed (§ 7g(3) EStG).
- **Year of purchase.** Up to the same share of the real cost may be added back to profit, but not more than the deductions still open; the asset's cost may then be cut by up to the amount added back (§ 7g(2) EStG).
- **Use.** Until the end of the financial year after purchase the asset must be let, or used only or almost only for the business in a German establishment; if not, the relief is reversed (§ 7g(4) EStG).
- **Special depreciation** needs a profit within the limit in the year before the purchase, and the asset must be let, or used only or almost only for the business in a German establishment, in the year of purchase and the year after (§ 7g(6) EStG). § 52(16) EStG ties its share to assets bought after 31 December 2023.
- **Sent electronically** with the profit figures. A deduction may create or raise a loss.

**From the ministry's instructions for the 2026 EÜR form**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2 |
| Writing or journalism as the main self-employed work: flat share of business receipts in place of actual expenses | 30% | Line 24: "pauschal 30 % der Betriebseinnahmen, maximal 3.600 € jährlich" |
| Yearly cap on that flat amount | EUR 3,600 | Same sentence |
| Scientific, artistic or writing work on the side, and side-line teaching and examining: flat share of business receipts | 25% | Line 24: "pauschal 25 % der Betriebseinnahmen" |
| Yearly cap on that flat amount | EUR 900 | Same sentence |
| Investment deduction: lowest share of business use that still counts as "almost only" (at least this much) | 90% | Line 89: "fast ausschließlich (mindestens 90 %) betrieblich genutzt" |

The flat shares are a choice and replace all actual business expenses of that activity. They rest on a ministry letter of 6 April 2023 that the instructions cite, not on the statute.

## Section 8: Special expenses: pension and health insurance

Private costs: they do not reduce the profit. They are taken off the total income (Section 4) and go on Anlage Vorsorgeaufwand.

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.deutsche-rentenversicherung.de/DRV/DE/Ueber-uns-und-Presse/Presse/Meldungen/2026/260420-vorsorgen-und-steuern-sparen |
| Highest deductible pension contributions in 2026, single person | EUR 30,826 | Pension insurer, 20 April 2026: "2026 beträgt der Höchstbetrag 30.826 Euro für Ledige und 61.652 Euro für Verheiratete" |
| The same for a married couple | EUR 61,652 | Same sentence |

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__10.html |
| Share of pension contributions within the cap that is deductible, from 2023 on | 100% | § 10(3) sentence 6: "ab dem Kalenderjahr 2023 beträgt er 100 Prozent" |
| Statutory health insurance with a claim to sick pay: the contribution is cut by this share before it is deducted | 4% | § 10(1) no. 3(a) sentence 4: "ist der jeweilige Beitrag um 4 Prozent zu vermindern" |
| Yearly cap for health, long-term care and other insurance together (§ 10(1) no. 3 and 3a), unless the next row applies; basic health and long-term care contributions above the cap are still deducted in full (sentence 4) | EUR 2,800 | § 10(4) sentence 1: "können je Kalenderjahr insgesamt bis 2 800 Euro abgezogen werden" |
| Lower cap for a person who, wholly or partly without own expense, has a claim to have sickness costs refunded or paid in full or in part, or for whose health insurance tax-free payments under § 3 no. 9, 14, 57 or 62 EStG are made | EUR 1,900 | § 10(4) sentence 2: "Der Höchstbetrag beträgt 1 900 Euro bei Steuerpflichtigen" |

- **Pension contributions (§ 10(1) no. 2 EStG).** To the statutory pension insurance, to a professional pension scheme with comparable benefits, and to a private contract that pays only a lifelong monthly annuity not before age 62. Rights under such a contract must not be inheritable, transferable, lendable against, saleable or payable as a lump sum.
- **The cap in the statute.** § 10(3) EStG ties it to the highest contribution to the miners' pension insurance, rounded up to a full euro, doubled for spouses assessed together. The statute prints no amount; the amount above is the pension insurer's, not the tax administration's.
- **With a job as well.** The employer's tax-free share of pension contributions is added to the person's own contributions before the cap is applied, and taken off again from the deductible result (§ 10(1) no. 2 sentence 6 and § 10(3) sentence 5 EStG).
- **Basic health and long-term care cover is deductible in full.** If those contributions alone are above the cap, they are deducted in full and nothing is left for other insurance (§ 10(4) sentence 4 EStG). For private health insurance only the part for benefits at the statutory level counts.
- **Other insurance (no. 3a)**, such as unemployment, accident, liability and term life cover, counts only while the cap has room.
- **Which cap.** § 3 no. 62 EStG is an employer's contribution for an employee, no. 14 the pension insurer's subsidy for a pensioner, no. 57 the payments of the artists' social fund (Künstlersozialkasse), no. 9 certain refunds under the Eighth Book of the Social Code (child day-care and foster carers). A freelancer insured through that fund, or one who also has a job with an employer's health contribution, meets the wording of the lower cap. One who pays for the whole cover alone, and has no claim to cover or refunds from another source without own expense, does not. The statute tests the claim ("ganz oder teilweise ohne eigene Aufwendungen"), not who pays the premium. Spouses assessed together get the sum of their own caps.

Contribution rates for the self-employed are in `de-social-contributions`.

## Section 9: Losses (§ 10d EStG)

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__10d.html |
| Carry-back cap, single assessment | EUR 1,000,000 | § 10d(1): "bis zu einem Betrag von 1 000 000 Euro" |
| Carry-back cap, spouses assessed together | EUR 2,000,000 | § 10d(1): "bis zu einem Betrag von 2 000 000 Euro" |
| Carry-forward: above a base of total income that the statute prints in words ("1 Million Euro"; "2 Millionen Euro" for spouses assessed together), losses are deducted only up to this share of the excess | 70% | § 10d(2): "bis zu 70 Prozent des 1 Million Euro übersteigenden Gesamtbetrags der Einkünfte" |

- **First inside the year.** A business loss is first set against the person's other income of the same year. § 10d EStG deals with what is left.
- **Carry-back.** To the year before, up to the cap; what still cannot be used goes to the second year before. It is taken off that year's total income ahead of special expenses, and a final assessment is changed for it. On request it is left out, but only as a whole.
- **Carry-forward.** The rest is taken off the total income of later years: without limit up to the base, above it up to the share in the table. The statute prints no time limit.
- **Separate notice.** The tax office fixes the remaining loss at each year end (§ 10d(4) EStG). A person with such a notice must file a return for the next year (§ 56 EStDV).
- **Trade tax is different.** § 10a GewStG only carries losses forward, with its own share. See `de-trade-tax`.

## Section 10: Prepayments (§ 37 EStG)

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__37.html |
| Prepayments are set only if they come to at least this much in the calendar year | EUR 400 | § 37(5): "mindestens 400 Euro im Kalenderjahr" |
| And at least this much for one due date | EUR 100 | § 37(5): "mindestens 100 Euro für einen Vorauszahlungszeitpunkt betragen" |
| After the year has ended, prepayments are raised only if the increase is at least | EUR 5,000 | § 37(5) sentence 2: "im Fall des Absatzes 4 auf mindestens 5 000 Euro beläuft" |

- **Due dates.** 10 March, 10 June, 10 September and 10 December (§ 37(1) EStG).
- **Who sets them.** The tax office, by notice. As a rule they follow the income tax of the last assessment, after credit for tax withheld. Both minimums in the table must be met ("and").
- **Adjustment.** The tax office can adjust them to the tax it expects for the year, until the end of the fifteenth calendar month after that year. The longer periods of the pandemic years ended with 2024 (§ 52(35d) EStG).
- **Raised after the year end.** The increase is added to the last prepayment and is due within one month of the notice (§ 37(4) EStG).
- **First year.** There is no last assessment yet. `de-estimated-tax` covers how the tax office sets prepayments for a new business.

More on planning the quarterly amounts is in `de-estimated-tax`.

## Section 11: The return: forms, electronic filing, deadlines

**Forms.** ELSTER's instructions for the 2025 return name them; those for 2026 were not yet published. See https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025

| Form | What goes on it |
| --- | --- |
| Hauptvordruck ESt 1 A | The main form of the return |
| Anlage S | Income from self-employed work: profit, gain on selling the business or part of it, side-line work |
| Anlage G | Income from a trade: profit, gain on selling the business or part of it, and the data for the § 35 EStG credit |
| Anlage EÜR with Anlage AVEÜR | The cash-basis accounts, one set per business (Section 3) |
| Anlage Vorsorgeaufwand | Insurance contributions (Section 8) |
| Anlage Sonderausgaben | Church tax, donations, own training costs |

- **Who must file (§ 56 EStDV).** A person not assessed jointly and without wages must file if the total income was more than the basic allowance in Section 5. For spouses assessed together without wages the test is twice the basic allowance; the rule prints no amount. A return is also due if a remaining loss was fixed at the end of the year before, and whenever the tax office asks (§ 149(1) AO). See https://www.gesetze-im-internet.de/estdv_1955/__56.html
- **Electronic filing is a duty (§ 25(4) EStG)** when there is income from farming, a trade or self-employed work. The tax office can waive it on request in hardship cases. ELSTER says registration can take up to two weeks. See https://www.gesetze-im-internet.de/estg/__25.html
- **Exception next to a job.** § 25(4) EStG leaves out the cases of § 46(2) no. 2 to 8 EStG. ELSTER's instructions put it this way: no duty if the person also has wages with tax withheld and the positive sum of income without wage tax is not more than the amount in the next table.

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__46.html |
| An employee must be assessed, and so must file, if the positive sum of income that was not subject to wage tax is more than | EUR 410 | § 46(2) no. 1: "jeweils mehr als 410 Euro beträgt" |
| If an employee is assessed and such income is in total not more than this, it is taken off the income again and stays untaxed | EUR 410 | § 46(3): "insgesamt nicht mehr als 410 Euro betragen" |

Both rows apply only to a person who also has wages with wage tax withheld: the first is a filing trigger, the second a hardship relief for small side income. A self-employed person without wages gets nothing from them. Above the amount, § 46(5) EStG lets a regulation phase the tax in.

**Deadlines for the 2026 return (§ 149 AO).** See https://www.gesetze-im-internet.de/ao_1977/__149.html

- **Without an adviser.** Seven months after the end of the calendar year: the end of July 2027. That day is a Saturday, and a period that ends on a Saturday, Sunday or public holiday ends on the next working day (§ 108(3) AO). See https://www.gesetze-im-internet.de/ao_1977/__108.html
- **With a tax adviser** or another person allowed to give tax help: the last day of February of the second year after the tax year, so the last day of February 2028 (§ 149(3) AO).
- **Older, later dates no longer apply.** The longer pandemic periods ended with tax year 2024 (Art. 97 § 36 EGAO). See https://www.gesetze-im-internet.de/aoeg_1977/art_97__36.html
- **Extension (§ 109 AO).** Possible. For an adviser's return, beyond the end of February only if the person was prevented through no fault of their own. See https://www.gesetze-im-internet.de/ao_1977/__109.html
- **Early request (§ 149(4) AO).** The tax office may ask for an adviser's return earlier, with four months' notice, for example if the return of the year before was late or missing, if a business was opened or closed in the year, or by random pick.

## Section 12: A late return and interest

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__152.html |
| Late filing surcharge for each started month of delay, as a share of the assessed tax less prepayments and creditable tax withheld | 0.25% | § 152(5) AO: "0,25 Prozent der festgesetzten Steuer"; sentence 2 sets the base for yearly returns |
| Minimum for each started month, for a yearly return such as income tax | EUR 25 | § 152(5) sentence 2 AO: "mindestens jedoch 25 Euro für jeden angefangenen Monat" |
| Highest surcharge for one return | EUR 25,000 | § 152(10) AO: "darf höchstens 25 000 Euro betragen" |

- **May be set** for any late or missing return, unless the person shows that the delay is excusable (§ 152(1) AO).
- **Must be set** if a yearly return is not filed within 14 months after the end of the calendar year, or not by the date of an early request (§ 152(2) AO).
- **The "must" falls away (§ 152(3) AO)** if the deadline was extended, the tax is set at zero or below, or the assessed tax is not more than the prepayments plus the tax withheld.

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__238.html |
| Interest on tax paid after an assessment, and on refunds (§ 233a AO), per month | 0.15% | § 238(1a) AO: "0,15 Prozent für jeden Monat" |
| The same rate per year, as the statute prints it | 1.8% | § 238(1a) AO: "das heißt 1,8 Prozent für jedes Jahr" |

Interest starts 15 months after the end of the calendar year in which the tax arose and ends when the assessment takes effect (§ 233a(2) AO). It is charged on the assessed tax less tax withheld and less the prepayments set before interest starts. Only full months count. Prepayments themselves carry no such interest. See https://www.gesetze-im-internet.de/ao_1977/__233a.html Tax paid after its due date also carries a late payment surcharge for each started month (§ 240 AO): https://www.gesetze-im-internet.de/ao_1977/__240.html

## Section 13: Trade tax credit against income tax (§ 35 EStG)

Only for a Gewerbetreibender. A Freiberufler pays no trade tax and gets no credit.

- **What is credited.** The income tax is reduced by four times the trade tax base amount (Gewerbesteuer-Messbetrag) set for the business for the same year. The statute prints the multiple in words ("das Vierfache").
- **First limit.** Only the part of the income tax that falls on the trade income can be reduced. The statute's formula: the sum of positive trade income, divided by the sum of all positive income, times the tariff income tax after certain other reductions.
- **Second limit.** Never more than the trade tax actually payable.
- **Same year only.** The page prints no rule that refunds an unused credit or carries it to another year.
- **Where.** The data go on Anlage G. See https://www.gesetze-im-internet.de/estg/__35.html

## The method, step by step

1. Decide the type of income: § 18 EStG or § 15 EStG (Section 2). Register within one month under § 138 AO. https://www.gesetze-im-internet.de/ao_1977/__138.html
2. Decide how profit is found: EÜR under § 4(3) EStG unless books must be kept or are kept by choice. For a trade, test the § 141 AO limits and check for a notice. https://www.gesetze-im-internet.de/ao_1977/__141.html
3. Work out the profit. Apply the limits of § 4(5) EStG (Section 7) and keep the separate records of § 4(7) EStG. https://www.gesetze-im-internet.de/estg/__4.html
4. Treat each fixed asset under § 6(2) EStG or depreciate it under § 7 EStG. Test § 7g EStG against the profit limit. https://www.gesetze-im-internet.de/estg/__7g.html
5. Send the Anlage EÜR for each business electronically under § 60(4) EStDV. https://www.gesetze-im-internet.de/estdv_1955/__60.html
6. Go from profit to taxable income in the order of § 2 EStG: other income, loss deduction under § 10d EStG, special expenses under § 10 EStG, child allowances. https://www.gesetze-im-internet.de/estg/__10.html and https://www.gesetze-im-internet.de/estg/__10d.html
7. Apply the tariff of § 32a(1) EStG, or the splitting method of § 32a(5) EStG for spouses assessed together. https://www.gesetze-im-internet.de/estg/__32a.html
8. For a trade, take off the credit of § 35 EStG. Test the solidarity surcharge limit of § 3 SolzG on the income tax. Add church tax for a member, on the base of § 51a(2) EStG, which ignores the § 35 credit. https://www.gesetze-im-internet.de/solzg_1995/__3.html
9. Send the return electronically under § 25(4) EStG within the deadline of § 149 AO. https://www.gesetze-im-internet.de/ao_1977/__149.html
10. Check the assessment notice and the new prepayment notice under § 37 EStG. Pay each prepayment by its due date. https://www.gesetze-im-internet.de/estg/__37.html

## Ask the client first

- What exactly do you do, and on what training or qualification is it based? Is a trade registered (Gewerbeanmeldung)?
- Do you keep books and a balance sheet, or use the EÜR? Has the tax office sent a notice to start keeping books?
- Do you also have a job, a pension, rental income or investment income in the same year?
- Are you married or in a registered partnership, and do you want joint assessment? Do you have children?
- Are you a member of a church that collects church tax, and in which federal state do you live?
- How are you insured for health and old age: statutory, private, a professional pension scheme, the artists' social fund?

## When to refuse or refer

- People with wages only and no business.
- Partnerships (GbR, OHG, KG, Partnerschaftsgesellschaft) and companies (GmbH, UG). A partnership that also does trade work is a trade as a whole (§ 15(3) no. 1 EStG).
- Whether a job that § 18 EStG does not name is a "similar profession", and how to split one person's mixed freelance and trade work. The pages read for this Guide settle neither. Refer to a Steuerberater.
- Cross-border cases: living or working abroad, tax withheld abroad, tax treaties, moving to or from Germany in the year.
- Capital gains and investment income: `de-capital-gains`. Crypto assets: `de-crypto-tax`. Rental income: `de-rental-income`.
- Working out trade tax: `de-trade-tax`. VAT, including the small-business rule: `germany-vat-return`. Payroll for the client's own staff: `de-payroll`.
- Selling or closing the business, extraordinary income (§ 34 EStG), retained profits (§ 34a EStG), the progression clause (§ 32b EStG).
- Electric and hybrid business cars, and any dispute over private use of a car.
- The exact church tax rate for a client: it is set by state church tax rules, which are not on the federal pages.
- Any request to state a tax amount or an average rate. This Guide gives the statute's formula and the method, not computed results.

## Sources

- EStG § 2, § 3, § 4, § 5, § 5b, § 6, § 7, § 7g, § 9: https://www.gesetze-im-internet.de/estg/__2.html and https://www.gesetze-im-internet.de/estg/__3.html and https://www.gesetze-im-internet.de/estg/__4.html and https://www.gesetze-im-internet.de/estg/__5.html and https://www.gesetze-im-internet.de/estg/__5b.html and https://www.gesetze-im-internet.de/estg/__6.html and https://www.gesetze-im-internet.de/estg/__7.html and https://www.gesetze-im-internet.de/estg/__7g.html and https://www.gesetze-im-internet.de/estg/__9.html
- EStG § 10, § 10d, § 11, § 12, § 15, § 18: https://www.gesetze-im-internet.de/estg/__10.html and https://www.gesetze-im-internet.de/estg/__10d.html and https://www.gesetze-im-internet.de/estg/__11.html and https://www.gesetze-im-internet.de/estg/__12.html and https://www.gesetze-im-internet.de/estg/__15.html and https://www.gesetze-im-internet.de/estg/__18.html
- EStG § 25, § 26, § 32a, § 34, § 35, § 36, § 37, § 46, § 51a, § 52: https://www.gesetze-im-internet.de/estg/__25.html and https://www.gesetze-im-internet.de/estg/__26.html and https://www.gesetze-im-internet.de/estg/__32a.html and https://www.gesetze-im-internet.de/estg/__34.html and https://www.gesetze-im-internet.de/estg/__35.html and https://www.gesetze-im-internet.de/estg/__36.html and https://www.gesetze-im-internet.de/estg/__37.html and https://www.gesetze-im-internet.de/estg/__46.html and https://www.gesetze-im-internet.de/estg/__51a.html and https://www.gesetze-im-internet.de/estg/__52.html
- EStDV § 56, § 60: https://www.gesetze-im-internet.de/estdv_1955/__56.html and https://www.gesetze-im-internet.de/estdv_1955/__60.html
- AO § 108, § 109, § 138, § 140, § 141, § 149: https://www.gesetze-im-internet.de/ao_1977/__108.html and https://www.gesetze-im-internet.de/ao_1977/__109.html and https://www.gesetze-im-internet.de/ao_1977/__138.html and https://www.gesetze-im-internet.de/ao_1977/__140.html and https://www.gesetze-im-internet.de/ao_1977/__141.html and https://www.gesetze-im-internet.de/ao_1977/__149.html
- AO § 152, § 233a, § 238, § 240: https://www.gesetze-im-internet.de/ao_1977/__152.html and https://www.gesetze-im-internet.de/ao_1977/__233a.html and https://www.gesetze-im-internet.de/ao_1977/__238.html and https://www.gesetze-im-internet.de/ao_1977/__240.html
- EGAO Art. 97 § 36: https://www.gesetze-im-internet.de/aoeg_1977/art_97__36.html
- SolzG § 3, § 4, § 6: https://www.gesetze-im-internet.de/solzg_1995/__3.html and https://www.gesetze-im-internet.de/solzg_1995/__4.html and https://www.gesetze-im-internet.de/solzg_1995/__6.html
- GewStG § 2, § 10a, § 11: https://www.gesetze-im-internet.de/gewstg/__2.html and https://www.gesetze-im-internet.de/gewstg/__10a.html and https://www.gesetze-im-internet.de/gewstg/__11.html
- Bundesreisekostengesetz § 5: https://www.gesetze-im-internet.de/brkg_2005/__5.html
- Finance ministry, EÜR form and instructions for 2026, letter of 1 September 2026: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2
- Finance ministry, tax booklet (Steuern von A bis Z), 2025 edition: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9
- ELSTER, instructions for the 2025 income tax return: https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025
- Deutsche Rentenversicherung, "Vorsorgen und Steuern sparen", 20 April 2026: https://www.deutsche-rentenversicherung.de/DRV/DE/Ueber-uns-und-Presse/Presse/Meldungen/2026/260420-vorsorgen-und-steuern-sparen

## Disclaimer

This Guide and its outputs are provided for informational and computational purposes only and do not constitute tax, legal, or financial advice. Open Accountants and its contributors accept no liability for any errors, omissions, or outcomes arising from the use of this Guide. All outputs must be reviewed and signed off by a qualified professional (such as a Steuerberater) before filing or acting upon.

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
