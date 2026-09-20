---
name: de-trade-tax
description: Use this skill whenever asked about German Trade Tax (Gewerbesteuer / GewSt) for self-employed Gewerbetreibende. Trigger on phrases like "Gewerbesteuer", "trade tax Germany", "GewSt", "Hebesatz", "Gewerbeertrag", "Steuermessbetrag", "Freibetrag 24500", "Gewerbesteuer Anrechnung", "§35 EStG", "trade tax credit", "Hinzurechnungen", "Kürzungen", "GewSt 1 A", or any question about German municipal trade tax obligations. Covers the Gewerbeertrag computation, EUR 24,500 Freibetrag, 3.5% Steuermesszahl, Hebesatz by municipality, Anrechnung on Einkommensteuer (4.0x credit under §35 EStG), Hinzurechnungen and Kürzungen, effective rate analysis, and Vorauszahlungen. ALWAYS read this skill before touching any Gewerbesteuer work.
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

# Trade tax in Germany (Gewerbesteuer)

How German trade tax (Gewerbesteuer, GewSt) works for a sole proprietor or a partnership that runs a commercial business (Gewerbebetrieb): who pays it, how trade income is worked out, the allowance, the base rate, the municipal multiplier (Hebesatz), the credit against income tax, prepayments and the return. Companies such as a GmbH are covered only for two questions: do they pay, and do they get the allowance. Figures are for tax year 2026. Statute figures are read from the consolidated federal law pages. Two figures come from the finance ministry's tax booklet "Steuern von A bis Z", 2025 edition (Stand Januar 2025), the latest one published: the lowest multiplier, which still applies in 2026, and the church tax range. The ELSTER form pages list the trade tax return for calendar years up to 2025. The form for 2026 was not yet listed when the pages were read on 19 September 2026.

## Guide Metadata

| Field | Value |
| --- | --- |
| Jurisdiction | Germany (Bundesrepublik Deutschland) |
| Jurisdiction Code | DE |
| Primary Legislation | Gewerbesteuergesetz (GewStG) |
| Supporting Legislation | Einkommensteuergesetz (EStG) § 35 (credit), § 15 and § 18 (what a commercial business is), § 4(5b), § 51a; Gewerbesteuer-Durchführungsverordnung (GewStDV) § 25; Abgabenordnung (AO) § 1, § 108, § 138, § 149, § 152, § 184, § 233a, § 238, § 240; Solidaritätszuschlaggesetz (SolzG) § 3 |
| Tax Authority | Finanzamt: sets the base amount (Gewerbesteuermessbescheid). Municipality (Gemeinde or Stadt): sets and collects the tax (Gewerbesteuerbescheid) |
| Filing Portal | ELSTER (elster.de) |
| Validated by | Pending. Requires sign-off by a Steuerberater or Wirtschaftsprüfer |
| Tax Year | 2026 |
| Confidence Coverage | Tier 1: allowance, base rate, how the multiplier is applied, the credit rule, filing deadlines. Tier 2: sorting add-backs, reductions, business or free profession. Tier 3: Organschaft, permanent establishments abroad, apportionment between several municipalities, partnership cases beyond the basics |

## Confidence Tier Definitions

- **[T1] Tier 1: Deterministic.** Apply exactly as written. No reviewer judgement required.
- **[T2] Tier 2: Reviewer Judgement Required.** The assistant flags the point and presents options. A Steuerberater must confirm.
- **[T3] Tier 3: Out of Scope, Escalate.** Do not guess. Escalate and document.

## Step 0: Client Onboarding Questions

Before working out any Gewerbesteuer figure, you MUST know:

1. **Is the client a Gewerbetreibender or a Freiberufler?** [T1] Trade tax applies only to a commercial business. A free profession carried on by a natural person is not a commercial business and pays no trade tax. A capital company pays by legal form whatever it does (Step 1).
2. **Municipality (Gemeinde or Stadt)** [T1] It sets the multiplier. You MUST know every municipality in which the business has a permanent establishment (Betriebsstätte).
3. **Profit from the business (Gewinn aus Gewerbebetrieb)** [T1] From Anlage G, based on the EÜR or the balance sheet.
4. **Any add-backs (Hinzurechnungen)?** [T2] Interest, rents, leases, licence fees and the other items in Step 3.
5. **Any reductions (Kürzungen)?** [T2] For example property tax on real property held in the business, profit shares from partnerships, donations (Step 4). Any trade losses carried forward?
6. **Legal form** [T1] Sole proprietor (Einzelunternehmen), partnership (Personengesellschaft) or company. It decides whether there is an allowance and whether there is an income tax credit.
7. **Trade tax prepayments already paid** [T1] Vorauszahlungen paid to the municipality for the year.

**If the client is a natural person who carries on a free profession within § 18 EStG and nothing else, STOP. Trade tax does not apply. For a partnership check the partnership rows in Step 1 first. A capital company pays trade tax whatever it does, a free profession included (§ 2(2) GewStG). Older material tells you to confirm free profession status with a "classification letter" from the Finanzamt. No page read for this Guide names such a letter. What exists is the client's own start-up questionnaire (Fragebogen zur steuerlichen Erfassung) and, if the tax office sees a commercial business, a base amount notice (Step 1).**

## Step 1: Who Must Pay Gewerbesteuer? [T1]

- **Legislation.** § 2 GewStG: https://www.gesetze-im-internet.de/gewstg/__2.html and § 15 EStG: https://www.gesetze-im-internet.de/estg/__15.html and § 18 EStG: https://www.gesetze-im-internet.de/estg/__18.html

**GewSt Obligation by Category**

| Category | Trade tax? | Where it says so |
| --- | --- | --- |
| A standing commercial business run in Germany, that is, with a permanent establishment in Germany. A commercial business is an independent, lasting activity, carried on to make a profit and open to the general market, that is not farming or forestry, not a free profession and not other self-employed work | YES | § 2(1) GewStG with § 15(2) EStG |
| Free professions (Freiberufler): independent scientific, artistic, writing, teaching or educational work, and the professions the law names: doctors, dentists, vets, lawyers, notaries, patent attorneys, surveyors, engineers, architects, commercial chemists, auditors, tax advisers, consulting economists, sworn accountants, tax agents, Heilpraktiker, Dentisten, physiotherapists, journalists, photo reporters, interpreters, translators, Lotsen (ship and harbour pilots; the page names no aircraft pilots) and similar professions ("und ähnlicher Berufe") | NO. Not a commercial business | § 18(1) no. 1 EStG, § 15(2) EStG. The ministry booklet: "die Ausübung eines freien Berufs bzw. eine andere selbständige Arbeit unterliegen demnach nicht der Gewerbesteuer" |
| Farming and forestry, and other self-employed work under § 18(1) no. 3 EStG (for example executor, asset manager, supervisory board member) | NO | § 15(2) EStG and the same booklet sentence |
| Capital companies (GmbH, AG, KGaA, SE), cooperatives, mutual insurance and pension fund associations | YES, always and in full, whatever they do. They pay by legal form | § 2(2) GewStG: "gilt stets und in vollem Umfang" |
| Other legal persons under private law and associations without legal personality | Only as far as they run a commercial operation (wirtschaftlicher Geschäftsbetrieb), farming and forestry excepted | § 2(3) GewStG |
| A partnership that ALSO carries on a commercial activity of its own | YES. The whole activity of the partnership counts as a commercial business, whether the commercial part makes a profit or a loss (Abfärbung) | § 15(3) no. 1 EStG, first case, with § 2(1) sentence 2 GewStG |
| A partnership with no commercial activity of its own that receives commercial income from a share in another partnership | For INCOME TAX its whole activity counts as commercial (§ 15(3) no. 1 EStG, second case). For TRADE TAX do not answer from the statute text alone. A Federal Fiscal Court ruling of 6 June 2019 (file number IV R no. 30/16, written in Germany without the "no."; Bundessteuerblatt 2020 II page 649) has consequences for trade tax. The state finance ministries at first did not apply it beyond the single case. Their decree of 5 November 2025 withdraws that: the trade tax principles of the ruling are "in allen offenen Fällen über den entschiedenen Einzelfall hinaus allgemein anzuwenden". The decree does not restate the ruling, and the ruling itself was not read for this Guide. [T3] Refer to a Steuerberater | State decree of 5 November 2025: https://www.bundesfinanzministerium.de/Content/DE/Standardartikel/Themen/Steuern/Steuerarten/Gewerbesteuer/2025-11-05-gle-aufhebung-gle-01-10-20-anl.pdf?__blob=publicationFile&v=3 |
| A partnership with no commercial activity of its own, whose only personally liable partners are capital companies and which only they or non-partners may manage (gewerblich geprägte Personengesellschaft) | YES, in full | § 15(3) no. 2 EStG |
| Travelling trade (Reisegewerbe) run in Germany | YES. The municipality at the centre of the activity levies the tax | § 35a GewStG |
| Businesses on the exemption list | NO, as far as the list goes. One entry covers a business whose only activity is making and selling power from a solar plant of up to 30 kilowatts installed on, at or in a building | § 3 GewStG, the solar entry is no. 32 |

See § 3 GewStG at https://www.gesetze-im-internet.de/gewstg/__3.html and § 35a GewStG at https://www.gesetze-im-internet.de/gewstg/__35a.html

- **Who owes the tax.** The entrepreneur for whose account the business is run. If a partnership runs the business, the partnership itself owes the tax, not the partners (§ 5 GewStG): https://www.gesetze-im-internet.de/gewstg/__5.html
- **IT consultants are not named in § 18 EStG.** Older material lists them as Freiberufler. The statute does not. Whether an IT consultant counts as an engineer, as a similar profession or as a commercial business depends on the facts. [T2]
- **Abfärbung is a partnership rule.** § 15(3) no. 1 EStG names partnerships only. It does not name a sole proprietor. The statute text has no minimum amount below which a small commercial part is ignored. That does not prove there is none in practice: the legacy text gave a court-made minimum limit, and the ministry's income tax handbook, where such a limit would be printed, could not be read for this Guide. Never tell a client that a small commercial part infects the whole partnership, or that it is too small to matter, without a Steuerberater (see EC3).

### Freiberufler vs Gewerbetreibender: Key Distinction

- **The test** is the wording of § 15(2) EStG in the table above: an activity that meets the four marks is a commercial business unless it is farming or forestry, a free profession or other self-employed work.
- **Start-up notice.** Whoever opens a commercial business tells the municipality on the official form, and the municipality informs the tax office without delay. Whoever takes up a free profession tells the tax office directly. Both then send the tax office further information about the facts that matter for tax, electronically. The form for a sole proprietor on ELSTER's form list is called "Fragebogen zur steuerlichen Erfassung für Einzelunternehmen". The notices are due within one month of the event. See § 138(1), (1b) and (4) AO: https://www.gesetze-im-internet.de/ao_1977/__138.html and the ELSTER form list: https://www.elster.de/eportal/formulare-leistungen/alleformulare
- **Who decides.** The tax office decides on trade tax liability when it sets the base amount. § 184(1) AO: "Mit der Festsetzung der Steuermessbeträge wird auch über die persönliche und sachliche Steuerpflicht entschieden." See https://www.gesetze-im-internet.de/ao_1977/__184.html The legacy text said "the Finanzamt's classification letter is definitive". No page read for this Guide names such a letter.

**WARNING:** The line between a free profession and a commercial business is fact-specific. An IT consultant who sells or resells software or hardware is likely to be running a commercial business. One who does engineering-type work may fall under § 18 EStG. [T2] if the classification is unclear.

## Step 2: Gewerbeertrag Computation [T1]

- **Legislation.** § 6 and § 7 GewStG: https://www.gesetze-im-internet.de/gewstg/__6.html and https://www.gesetze-im-internet.de/gewstg/__7.html
- **Gewerbeertrag definition.** The tax base is the trade income (Gewerbeertrag). It is the profit from the business as worked out under the Income Tax Act or the Corporation Tax Act, increased and reduced by the amounts in § 8 and § 9 GewStG.
- **Which year.** The collection period (Erhebungszeitraum) is the calendar year. If the business is liable for only part of the year, that part is the period (§ 14 GewStG): https://www.gesetze-im-internet.de/gewstg/__14.html A business that must keep books under the Commercial Code and has a financial year different from the calendar year counts its trade income in the collection period in which the financial year ends (§ 10(2) GewStG): https://www.gesetze-im-internet.de/gewstg/__10.html
- **Trade tax is not an expense.** Trade tax and the charges on it are not business expenses (§ 4(5b) EStG), so the profit you start from has not been reduced by trade tax: https://www.gesetze-im-internet.de/estg/__4.html

### Formula

- **Gewerbeertrag formula.** Gewerbeertrag = profit from the business + Hinzurechnungen (§ 8 GewStG) less Kürzungen (§ 9 GewStG) less trade losses carried forward (§ 10a GewStG). Then Step 5.

### Starting Point

| Legal Form | Starting Point |
| --- | --- |
| Einzelunternehmen (sole proprietor) | Profit from Anlage G (EÜR or balance sheet) |
| Personengesellschaft (partnership) | Profit from the separate and uniform determination (gesonderte und einheitliche Feststellung). Under § 15(1) no. 2 EStG the pay a partner receives from the partnership for work, for loans or for the use of assets is part of the commercial income, so it is inside the profit that trade tax starts from |

## Step 3: Hinzurechnungen (Add-Backs) [T2]

- **Legislation.** § 8 GewStG: https://www.gesetze-im-internet.de/gewstg/__8.html

Certain financing, rental and licence costs that were deducted in working out the profit are partly added back. The rule in § 8 no. 1 GewStG has three steps, in the statute's own order.

**Hinzurechnungen Add-Back Rates**

The law prints every share in WORDS ("ein Viertel", "einem Fünftel", "der Hälfte"). No percentages are printed, so none are printed here.

| Item, § 8 no. 1 GewStG | Share of the cost that goes into the sum |
| --- | --- |
| a) Interest and other payments for debt (Entgelte für Schulden). This includes discounts given outside the ordinary course of business for early payment, and discount amounts on selling bills and other money claims | in full |
| b) Annuities and permanent burdens (Renten und dauernde Lasten). Pension payments under a pension promise given directly by the employer do not count | in full |
| c) Profit shares of a silent partner | in full |
| d) Rent, lease and leasing payments for movable fixed assets owned by someone else | one fifth. Only half of that for electric vehicles, certain plug-in hybrids and bicycles that are not motor vehicles |
| e) Rent, lease and leasing payments for immovable fixed assets owned by someone else | one half |
| f) Payments for the time-limited use of rights, above all concessions and licences. Not licences that only entitle the business to pass derived rights on to third parties. Not payments that are the base for the artists' social levy (§ 25 Künstlersozialversicherungsgesetz) | one quarter |

### Hinzurechnungen Freibetrag

**Trade tax: add-back of financing costs**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__8.html |
| Allowance taken off the sum of the items above before anything is added back | EUR 200,000 | § 8 no. 1 GewStG: "soweit die Summe den Betrag von 200 000 Euro übersteigt" |

- **Step 1: add up the items, each at the share in the table of shares.**
- **Step 2: take off the allowance** in the table. It is an allowance on the SUM, not a cliff: if the sum is at or below the allowance, nothing is added back; if it is above, only the part above counts.
- **Step 3: add back one quarter** of what is left.
- **Electric vehicles: contract date.** The half share in letter d applies only to payments under contracts made after 31 December 2019. For contracts made before 1 January 2025 an electric range of 60 kilometres is enough for a plug-in hybrid, where the statute otherwise asks for 80 kilometres or emissions of at most 50 grams of carbon dioxide per kilometre. The half share applies for the last time in collection period 2030. See § 36(4) GewStG: https://www.gesetze-im-internet.de/gewstg/__36.html
- **Correction.** The legacy text printed the shares as percentages and left out letters b and c and the electric vehicle rule. Other older material says a flat share of rent and a flat share of interest is added back. That skips the different shares per item and the allowance.
- **Other add-backs in § 8 GewStG**, each only as far as it reduced the profit: profit shares and management pay of the personally liable partners of a KGaA (no. 4); dividends left out of income under § 3 no. 40 EStG or § 8b(1) KStG, unless the holding meets the conditions of § 9 no. 2a or no. 7, after the related expenses (no. 5); shares in the LOSS of a partnership (no. 8); donations deducted under § 9(1) no. 2 KStG (no. 9); certain write-downs and losses on shares in a company (no. 10); foreign taxes deducted under § 34c EStG on income that is left out of or cut from trade income (no. 12). [T2] or [T3].

**Simplified:** A sole proprietor with modest financing, rent and licence costs stays below the allowance in the table, and then nothing is added back. Add-backs matter mainly for businesses with high debt, high rents or many leased assets.

**[T2] Flag for the reviewer whenever the sum of the items comes near the allowance in the table.** The legacy text named a fixed flag amount. No official page prints one, so it was removed.

## Step 4: Kürzungen (Reductions) [T2]

- **Legislation.** § 9 GewStG: https://www.gesetze-im-internet.de/gewstg/__9.html

**Kürzungen table**

| Kürzung | What the law says | Condition |
| --- | --- | --- |
| Property tax on business real property (§ 9 no. 1 sentence 1) | The Grundsteuer booked as a business expense in the collection period, for real property that belongs to the entrepreneur's business assets | This wording first applies for collection period 2025 (§ 36(4b) GewStG). The older rule, a fixed share of the Einheitswert, is no longer in the statute |
| Extended property reduction (§ 9 no. 1 sentences 2 to 6) | On request, in place of the line above: the part of the trade income that comes from managing and using the business's own real property | Only for businesses that exclusively manage and use their own real property, or next to it manage their own capital assets, look after residential buildings, or build and sell houses and flats. Narrow limits for side income (power from renewable sources and charging stations; other income from tenants). Not if the property serves the business of a partner. [T3] |
| Profit shares from partnerships (§ 9 no. 2) | Shares in the profit of an OHG, a KG or another partnership in which the partners are co-entrepreneurs, if they were counted in the profit | The partnership owes its own trade tax (Step 1). The mirror rule for loss shares is § 8 no. 8 |
| Dividends from German companies (§ 9 no. 2a) | Profits from shares in a German capital company that is not exempt (and in some other bodies named there), if they were counted in the profit | The holding at the START of the collection period must be at least the share in the table below. Directly related expenses reduce the amount |
| Permanent establishment abroad (§ 9 no. 3) | The part of the trade income that falls on a permanent establishment outside Germany | [T3] |
| Donations (§ 9 no. 5) | Donations and membership fees for tax-privileged purposes (§§ 52 to 54 AO) paid from the funds of the business | Up to the share of profit in the table below, or 4 per mille of the sum of total turnover and wages and salaries of the financial year. Amounts above the cap can be used in later collection periods within the caps |
| Dividends from foreign companies (§ 9 no. 7 and no. 8) | Profits from shares in a capital company with management and seat outside Germany | No. 7: holding at the START of the collection period at least the share in the table below. No. 8 (profits that a tax treaty exempts from trade tax on condition of a minimum holding): holding of at least the same share; the text of no. 8 does not say at which date. A lower treaty threshold prevails. [T3] |

**Shares printed in § 9 GewStG**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__9.html |
| Minimum holding for the dividend reductions. No. 2a and no. 7: measured at the START of the collection period. No. 8 prints the same share without those words | 15% | § 9 no. 2a GewStG: "mindestens 15 Prozent des Grund- oder Stammkapitals beträgt" |
| Donations: cap as a share of the profit from the business, increased by the add-back under § 8 no. 9 | 20% | § 9 no. 5 GewStG: "insgesamt 20 Prozent des um die Hinzurechnungen nach § 8 Nummer 9 erhöhten Gewinns" |

The same section prints both figures again for other rules: the first as the liability amount where a donation receipt is wrong or a donation is not used for the stated purpose (no. 5), the second as the side income limit of the extended property reduction. The rows above are the holding threshold and the donations cap only.

**Most sole proprietors:** Check the property tax line first. It applies only if the real property belongs to the business assets and the Grundsteuer on it was booked as a business expense. Premises that are only rented are not the entrepreneur's business assets, so there is no reduction for them. The legacy text gave this reduction as a fixed percentage of the Einheitswert. That rule is gone from § 9 GewStG.

### Trade losses carried forward (§ 10a GewStG)

**Gewerbeverlust**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__10a.html |
| Share of the trade income ABOVE the base that may be reduced by losses carried forward | 60% | § 10a sentence 2 GewStG: "ist bis zu 60 Prozent um nach Satz 1 nicht berücksichtigte Fehlbeträge" |

- **The rule.** Trade income is reduced by the losses (Fehlbeträge) of EARLIER collection periods, without limit up to a base the statute prints as "1 Million Euro". Trade income above that base may be reduced only up to the share in the table.
- **Forward only.** § 10a GewStG speaks only of losses from earlier collection periods. The page has no carry-back.
- **Not the income tax share.** Income tax loss use above its base is capped at a different, higher share (§ 10d EStG). Do not mix the two.
- **Separate determination.** The loss that can be carried forward is determined separately at the end of each collection period. A business with such a determination must file a return (Step 10).
- **Partnerships.** The partnership's loss is allocated to the partners by the general profit sharing key of the partnership agreement, without advance profit shares. For the deduction, the partnership's trade income and the "1 Million Euro" base are allocated to the partners the same way, by the key for the year of deduction. A change of partners is [T3].
- **Transfer of the business.** If a business passes as a whole to another entrepreneur, the new one cannot use the losses of the business taken over (§ 10a sentence 8 with § 2(5) GewStG).
- **Companies.** § 8c and § 8d KStG apply to the losses. [T3]

## Step 5: Freibetrag [T1]

- **Legislation.** § 11(1) GewStG: https://www.gesetze-im-internet.de/gewstg/__11.html

**Freibetrag by Entity Type**

| Entity Type | Freibetrag | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__11.html |
| Natural persons (sole proprietors) and partnerships (Personengesellschaften) | EUR 24,500 | § 11(1) sentence 3 no. 1 GewStG: "um einen Freibetrag in Höhe von 24 500 Euro" |
| Businesses within § 2(3) GewStG (associations and other private-law legal persons with a commercial operation), certain exempt bodies named in § 11(1) no. 2, and businesses of public-law legal persons | EUR 5,000 | § 11(1) sentence 3 no. 2 GewStG: "um einen Freibetrag in Höhe von 5 000 Euro" |
| Capital companies (GmbH, AG) outside that list | none | § 11(1) names no allowance for them |

- **Freibetrag formula.** First round the trade income DOWN to full hundreds of euros. Then take off the allowance, but never more than the rounded trade income: the result cannot go below zero.
- **What kind of limit.** It is an allowance, not a cliff: only the trade income above it is taxed. It is given per collection period. It is taken off the trade income of the business. ELSTER states that a sole proprietor with several businesses of different kinds files a separate return for each business: https://www.elster.de/eportal/formulare-leistungen/alleformulare/gewst
- **Below Freibetrag rule.** If the rounded trade income is not more than the allowance in the table, the base amount is nil and no trade tax is due.
- **Short periods.** § 11 GewStG does not say that the allowance is cut when the business was liable for only part of the year.

## Step 6: Steuermessbetrag [T1]

- **Legislation.** § 11(2) GewStG and § 14 GewStG.

**Steuermesszahl (federal constant)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__11.html |
| Base rate (Steuermesszahl) applied to the trade income left after Step 5 | 3.5% | § 11(2) GewStG: "Die Steuermesszahl für den Gewerbeertrag beträgt 3,5 Prozent" |

- **Steuermessbetrag formula.** Steuermessbetrag (base amount) = trade income after rounding and allowance, times the base rate in the table.
- **Not the tax rate.** The base rate is not the trade tax rate. The tax is the base amount times the municipal multiplier (Step 7).
- **Home workers.** § 11(3) GewStG gives a reduced base rate for Hausgewerbetreibende and persons treated like them. Not covered here.

The Finanzamt sets the base amount after the end of the collection period in the Gewerbesteuermessbescheid (§ 14 GewStG, § 184 AO) and passes it to the municipality. The municipality then applies its multiplier.

## Step 7: Hebesatz and Final GewSt [T1]

- **Legislation.** § 16 GewStG: https://www.gesetze-im-internet.de/gewstg/__16.html and § 4 GewStG: https://www.gesetze-im-internet.de/gewstg/__4.html
- **Gewerbesteuer formula.** Gewerbesteuer = Steuermessbetrag times Hebesatz, where the Hebesatz is a percentage.
- **Who sets it.** The municipality in which the business has a permanent establishment. The multiplier must be the same for all businesses in the municipality. The decision to set or change it is taken by 30 June of a calendar year with effect from the start of that year. After that date it can only be set at or below the last level (§ 16(3) and (4) GewStG).

**Minimum Hebesatz: collection period 2026**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Lowest multiplier for collection period 2026. It applies where the municipality has not set a higher one | 200% | Ministry booklet, 2025 edition, chapter Gewerbesteuer: "Er beträgt mindestens 200 Prozent" |

**Minimum Hebesatz: from collection period 2027**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__16.html |
| Lowest multiplier from collection period 2027 on. NOT the 2026 figure | 280% | § 16(4) sentence 2 GewStG: "Er beträgt 280 Prozent, wenn die Gemeinde nicht einen höheren Hebesatz bestimmt hat" |

- **Why two figures.** The statute page already shows the text as changed by the law of 29 June 2026. § 36(5b) GewStG says that this version of § 16(4) sentence 2 first applies for collection period 2027: https://www.gesetze-im-internet.de/gewstg/__36.html For 2026 the older floor still applies. The older floor is printed as a digit in the ministry booklet, 2025 edition, and in the amending law of 29 June 2026 itself, which says that in § 16(4) sentence 2 the older figure is replaced by the one printed today. Federal Law Gazette 2026 I no. 197: https://www.recht.bund.de/bgbl/1/2026/197/regelungstext.pdf?__blob=publicationFile
- **Only a floor.** Each municipality sets its own multiplier. The floor says nothing about what a given municipality charges.

### Hebesätze: Major Cities (list removed)

This Guide does not list city multipliers. The legacy list of ten cities for 2025 was removed. Multipliers are set by each municipality and are printed on no federal page this Guide may cite, so none of them could be proven. Read the multiplier from the municipality's own trade tax notice (Gewerbesteuerbescheid) or from its decision on the multiplier for the year in question.

**WARNING:** Multipliers change. A municipality can change its multiplier for the current year until 30 June. Never quote a multiplier from memory, and never from this Guide.

## Step 8: Anrechnung on Einkommensteuer (§35 EStG) [T1]

- **Legislation.** § 35 EStG: https://www.gesetze-im-internet.de/estg/__35.html

A sole proprietor, and a partner of a commercial partnership, gets a reduction of income tax for the trade tax on the business. The statute prints the factor in WORDS ("das Vierfache", four times), so it is written in words here.

### Formula

- **Anrechnungsbetrag formula.** The reduction is the LOWEST of three amounts: (a) four times the base amount (Steuermessbetrag) set for the business for the collection period that matches the income tax year; (b) the trade tax actually payable; (c) the maximum reduction amount (Ermäßigungshöchstbetrag).
- **Credit multiple.** § 35(1) no. 1 EStG: "um das Vierfache des ... festgesetzten Steuermessbetrags". For a partner it is four times the partner's SHARE of the base amount (§ 35(1) no. 2).
- **Cap at the trade tax.** § 35(1) sentence 5 EStG: "Der Abzug des Steuerermäßigungsbetrags ist auf die tatsächlich zu zahlende Gewerbesteuer beschränkt." This cap matters whenever the trade tax is lower than four times the base amount. The legacy formula left it out.
- **Maximum reduction amount.** Income tax is reduced only as far as it falls on the commercial income inside taxable income. The statute's formula: the sum of the positive commercial income, divided by the sum of all positive income, times the reduced tariff tax. "Commercial income" means profits and profit shares that are subject to trade tax.
- **Partners.** A partner's share of the base amount follows the partner's share of profit under the general profit sharing key. Advance profit shares are not counted. The base amount, the trade tax actually payable and each partner's share are determined separately and uniformly (§ 35(2) EStG).
- **Notices.** The base amount notice and the trade tax notice are base notices (Grundlagenbescheide) for the reduction (§ 35(3) EStG). The income tax assessment follows them.
- **Companies.** § 35 EStG reduces income tax. A GmbH pays corporation tax and has no such reduction.

### Effective Rate Analysis

Removed. The legacy text worked out a trade tax rate per multiplier, a fixed credit rate, a net burden for named cities and a break-even multiplier below which trade tax was called free. No official page prints any of these. They also ignored the cap at the trade tax actually payable and the maximum reduction amount. This Guide states no combined rate, no effective burden and no break-even multiplier. Work through the steps with the client's own figures.

### Limitations on Anrechnung

| Limitation | Detail |
| --- | --- |
| Cap 1 | Not more than the trade tax actually payable (§ 35(1) sentence 5 EStG) |
| Cap 2 | Not more than the income tax that falls on the commercial income (the maximum reduction amount) |
| Low income | If the income tax that falls on the commercial income is low, the four-times amount can be higher than Cap 2. The part above the cap is not used |
| No carry-forward | § 35 EStG has no rule that carries an unused amount to another year or pays it out |
| Church tax | The reduction does NOT lower church tax. § 51a(2) sentence 3 EStG: "§ 35 ist bei der Ermittlung der festzusetzenden Einkommensteuer nach Satz 1 nicht anzuwenden" |
| Solidarity surcharge | § 3(2) SolzG measures the surcharge on the income tax that would be assessed if the child allowances of § 32(6) EStG were counted in every case, and § 2(6) EStG defines the income tax to be assessed as the tariff income tax less the tax reductions. § 3 SolzG has no sentence that switches § 35 off. The legacy text said the reduction does not lower the surcharge. The pages read do not support that. [T2] |

See § 51a EStG: https://www.gesetze-im-internet.de/estg/__51a.html and § 3 SolzG: https://www.gesetze-im-internet.de/solzg_1995/__3.html and § 2 EStG: https://www.gesetze-im-internet.de/estg/__2.html

## Step 9: GewSt Vorauszahlungen (Advance Payments) [T1]

- **Legislation.** § 19, § 20 and § 21 GewStG: https://www.gesetze-im-internet.de/gewstg/__19.html and https://www.gesetze-im-internet.de/gewstg/__20.html

**GewSt Vorauszahlungen details**

| Aspect | Detail |
| --- | --- |
| Due dates | 15 February, 15 May, 15 August and 15 November. A business with a financial year different from the calendar year pays during the financial year that ends in the collection period, if it was founded, became liable or changed its financial year after 31 December 1985 (§ 19(1)) |
| Each payment | In principle one quarter of the tax from the LAST assessment. The statute says "ein Viertel" (§ 19(2)) |
| Rounding and minimum | Each single prepayment is rounded down to full euros. It is set only if it reaches the amount in the table below (§ 19(5)) |
| Adjustment | The MUNICIPALITY may adjust prepayments to the tax it expects for the period, until the end of the 15th month after the collection period. The Finanzamt may set an expected base amount for prepayment purposes, and the municipality is then bound by it. An increase set after the period is due within one month of the prepayment notice (§ 19(3)) |
| New business | The first prepayments are set the same way, from the expected tax (§ 19(4)) |
| Settlement | Prepayments are credited against the tax for the period. A balance due is payable within one month of the tax notice, and at once as far as it matches prepayments that were due and not paid. An overpayment is set off or paid back after the notice (§ 20) |

**Minimum prepayment**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__19.html |
| A single prepayment is set only if it is at least | EUR 50 | § 19(5) GewStG: "Sie wird nur festgesetzt, wenn sie mindestens 50 Euro beträgt" |

- **Correction.** The legacy text applied this minimum to the yearly tax. The statute applies it to each single prepayment. The legacy text also said the Finanzamt adjusts prepayments. Under § 19(3) the municipality does; the Finanzamt can only set the base amount for that purpose.

## Step 10: Filing and Deadlines [T1]

- **Legislation.** § 14a GewStG: https://www.gesetze-im-internet.de/gewstg/__14a.html and § 25 GewStDV: https://www.gesetze-im-internet.de/gewstdv_1955/__25.html and § 149 AO: https://www.gesetze-im-internet.de/ao_1977/__149.html

**Filing requirements and deadlines**

| Requirement | Rule |
| --- | --- |
| The return | Declaration for setting the base amount (Gewerbesteuererklärung, form GewSt 1 A). ELSTER lists what it contains: the trade tax return, the declaration for the separate determination of the trade loss, the declaration for the donations carry-forward, and Anlage EMU for partner-related loss offsetting |
| Filing method | Electronically through the official interface. On request the tax office can waive this to avoid undue hardship; then the paper form is signed by hand (§ 14a GewStG) |
| Deadline without an adviser | Seven months after the end of the calendar year (§ 149(2) AO), so for collection period 2026 the end of July 2027. If the last day of a period is a Saturday, a Sunday or a public holiday, the period ends on the next working day (§ 108(3) AO): https://www.gesetze-im-internet.de/ao_1977/__108.html 31 July 2027 is a Saturday, so the period ends on Monday 2 August 2027. § 25(2) GewStDV adds that the return is due at the latest at the time set by the highest state finance authorities |
| Deadline with a tax adviser | The last day of February of the SECOND calendar year after the tax period (§ 149(3) no. 3 AO names this return), so for collection period 2026 the last day of February 2028. The tax office can call a return in earlier with four months' notice (§ 149(4) AO) |
| Several municipalities | Also an apportionment declaration (form GewSt 1 D), filed together with GewSt 1 A as a second form: https://www.elster.de/eportal/formulare-leistungen/alleformulare/gewstzerl |
| Several businesses | A separate return for each independent business. A sole proprietor with several businesses of different kinds files one return per business: https://www.elster.de/eportal/formulare-leistungen/alleformulare/gewst |

The special, later deadlines of Art. 97 § 36 EGAO cover tax periods 2020 to 2024 only. They do not apply to 2026: https://www.gesetze-im-internet.de/aoeg_1977/art_97__36.html

**Who must file a return**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstdv_1955/__25.html |
| Every business liable to trade tax whose trade income in the collection period was MORE than | EUR 24,500 | § 25(1) no. 1 GewStDV: "den Betrag von 24 500 Euro überstiegen hat" |
| Other private-law legal persons and associations with a commercial operation, businesses of public-law legal persons, and partly exempt businesses: trade income MORE than | EUR 5,000 | § 25(1) no. 3 to 5 GewStDV: "den Betrag von 5 000 Euro überstiegen hat" |

Also bound to file, whatever the amount: capital companies and cooperatives that are not exempt (no. 2 and 3); every business for which a trade loss carry-forward was determined at the end of the previous period (no. 6); every business the tax office asks for a return (no. 7).

**Late filing surcharge for this return**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__152.html |
| Flat surcharge for each started month of delay, for declarations to set the trade tax base amount and for apportionment declarations | EUR 25 | § 152(6) AO: "der eingetretenen Verspätung 25 Euro" |
| Highest surcharge for one return | EUR 25,000 | § 152(10) AO: "darf höchstens 25 000 Euro betragen" |

- **Discretion or automatic.** The tax office MAY set a surcharge for any late return. It MUST set one if the return is not filed within 14 months after the end of the calendar year, unless the deadline was extended (§ 152(1), (2), (3) no. 1 and (6) AO). For this return § 152(6) carries over only no. 1 of § 152(3). The let-outs of § 152(3) no. 2 and no. 3 (tax set at nil or below, tax not above the prepayments and the credited withholding amounts) are not carried over.
- **Who gets it.** The surcharge goes to the municipality. The multiplier is not applied to it (§ 14b GewStG): https://www.gesetze-im-internet.de/gewstg/__14b.html
- **Same number, other rule.** The highest surcharge has the same digits as the owner amount used for apportionment in EC5. They are different rules.

**Late payment surcharge**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__240.html |
| Surcharge for each started month in which a tax is not paid by its due date, on the overdue tax after rounding down | 1% | § 240(1) AO: "ein Säumniszuschlag von 1 Prozent des abgerundeten rückständigen Steuerbetrags" |
| The overdue tax is first rounded down to the next amount divisible by | EUR 50 | § 240(1) AO: "abzurunden ist auf den nächsten durch 50 Euro teilbaren Betrag" |

No surcharge is charged for a delay of up to three days (§ 240(3) AO). The second figure is the same number as the minimum prepayment in Step 9. They are different rules.

**Interest on trade tax set late**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__238.html |
| Interest per month on a difference under § 233a AO, in favour of or against the taxpayer | 0.15% | § 238(1a) AO: "0,15 Prozent für jeden Monat" |
| The same rate as the statute prints it per year | 1.8% | § 238(1a) AO: "das heißt 1,8 Prozent für jedes Jahr" |

§ 233a(1) AO names trade tax. Interest starts 15 months after the end of the calendar year in which the tax arose, and only full months count. It does not apply to prepayments. See https://www.gesetze-im-internet.de/ao_1977/__233a.html The collection rules of the AO apply to trade tax that a municipality administers (§ 1(2) no. 5 AO): https://www.gesetze-im-internet.de/ao_1977/__1.html

### Example: the order of the computation

The legacy example (a sole proprietor in Berlin with a stated profit) was removed. It used a city multiplier that no allowed page prints and showed amounts that were computed, not read from a page. The order of the steps is kept, without amounts:

~~~
Step 1: Profit from the business (income tax rules)        = P
Step 2: + add-backs, Step 3 (sum of items, less allowance,
          one quarter of the rest, plus other add-backs)   = H
Step 3: - reductions, Step 4                               = K
Step 4: - trade losses carried forward (section 10a)       = V
Step 5: = trade income, rounded DOWN to full hundreds of euros
Step 6: - allowance (Step 5 table; natural persons and partnerships)
Step 7: x base rate (Step 6 table)      = base amount (Steuermessbetrag)
Step 8: x multiplier of the municipality = trade tax
Step 9: income tax reduction = four times the base amount,
        but not more than the trade tax actually payable,
        and not more than the income tax on the commercial income
~~~

Trade tax is not a business expense, so it is not deducted from P.

## Step 12: Edge Case Registry

### EC1: Freiberufler reclassified as Gewerbetreibender [T2]

**Situation:** An IT consultant was treated as a Freiberufler for three years. After a tax audit the Finanzamt treats the activity as a commercial business.
**Resolution:** The tax office sets base amounts for the years it can still assess, and the municipality sets trade tax on them. The base amount notice and the trade tax notice are base notices for the § 35 EStG reduction (§ 35(3) EStG), so the income tax assessments follow them. The limitation rules of the AO were not read for this Guide. [T2] flag for a Steuerberater: large financial and compliance impact.

### EC2: Gewerbeertrag below Freibetrag [T1]

**Situation:** A sole proprietor's trade income is below the allowance in the Step 5 table.
**Resolution:** The base amount is nil and no trade tax is due. A return is still required if a trade loss carry-forward was determined at the end of the previous period, or if the tax office asks for one (§ 25(1) no. 6 and no. 7 GewStDV). The legacy text added "recommended to file anyway". No official page says that, so it was removed.

### EC3: Abfärbetheorie (infection theory) for mixed activity [T2]

**Situation:** A free professional (an architect) also sells building materials, which is a commercial activity.
**Resolution:** It depends on who carries on the two activities. If a PARTNERSHIP does, § 15(3) no. 1 EStG treats its whole activity as a commercial business, whether the commercial part makes a profit or a loss. The statute text has no minimum amount. If ONE PERSON does, § 15(3) no. 1 EStG does not apply by its wording: it names partnerships only. How the two activities of one person are told apart is not on the pages read. The legacy text applied the rule to a sole architect and gave a minimum limit as a share of turnover and an amount. No readable allowed page prints that limit, so its figures were removed. The limit may still exist in case law and in the ministry's income tax handbook, which could not be read. Do not conclude from its absence here that every small commercial part infects the partnership. [T2] flag for a Steuerberater in every mixed case.

### EC4: Anrechnung exceeds ESt on Gewerbe income [T1]

**Situation:** A sole proprietor in a municipality with a low multiplier has little income tax on the commercial income.
**Resolution:** Apply both caps of § 35(1) EStG. The reduction cannot be more than the trade tax actually payable, and it cannot be more than the income tax that falls on the commercial income. The part of the four-times amount above the lower cap is not used. § 35 EStG has no carry-forward.

### EC5: Client moves municipality mid-year [T2]

**Situation:** The business moves its only permanent establishment from one municipality to another during the year.
**Resolution:** The base amount is apportioned. § 28(1) sentence 2 GewStG says apportionment also applies where a permanent establishment was moved from one municipality to another within a collection period. The scale is wages (§ 29 GewStG). For a business that is not run by a legal person, a fixed yearly amount is counted for the owners who work in the business, so there is a scale even with no employees. The legacy text said the municipality at year end "typically applies" for a sole proprietor without employees. The statute does not say that. [T2] flag for a Steuerberater. See https://www.gesetze-im-internet.de/gewstg/__28.html and https://www.gesetze-im-internet.de/gewstg/__29.html

**Apportionment: amount counted for working owners**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__31.html |
| Yearly amount counted as wages, in total, for the owners or co-entrepreneurs who work in a business not run by a legal person | EUR 25,000 | § 31(5) GewStG: "insgesamt 25.000 Euro jährlich anzusetzen" |

The statute does not say how this amount is split between two municipalities after a move. If the scale gives a plainly unfair result, another scale is used, and the municipalities can agree a split with the taxpayer (§ 33 GewStG): https://www.gesetze-im-internet.de/gewstg/__33.html

### EC6: GewSt Vorauszahlung significantly exceeds actual liability [T1]

**Situation:** The prepayments for the year are higher than the trade tax finally set.
**Resolution:** The prepayments are credited against the tax. The difference is set off or paid back after the trade tax notice is issued (§ 20(3) GewStG). For the running year, ask the municipality to adjust the prepayments (§ 19(3) GewStG).

### EC7: Sole proprietor with significant interest expenses [T2]

**Situation:** The business deducted loan interest in its EÜR.
**Resolution:** Interest goes into the sum in Step 3 in full. If the sum of all items, each at its share, is not above the allowance in the Step 3 table, nothing is added back. If it is above, one quarter of the excess is added back. Rents, leases and licence fees go into the same sum, so check them together. [T2] flag when the sum comes near the allowance.

### EC8: Gewerbeanmeldung vs Finanzamt registration [T1]

**Situation:** The client registered the business with the municipality but sent nothing to the Finanzamt.
**Resolution:** Trade tax attaches to running a standing commercial business in Germany (§ 2(1) GewStG), not to a registration. The legacy text said the liability "arises from the Gewerbeanmeldung". That is not what § 2 says. Under § 138(1) AO the municipality informs the tax office of the opening without delay. The client must still send the tax office the further information (the start-up questionnaire) electronically, within one month of opening (§ 138(1b) and (4) AO).

### EC9: Kirchensteuer interaction with GewSt Anrechnung [T1]

**Situation:** The client is a church member. Does the § 35 EStG reduction also lower church tax?
**Resolution:** No. For church tax the income tax is worked out as if § 35 EStG did not exist (§ 51a(2) sentence 3 EStG). For the solidarity surcharge the pages read point the other way: see the table in Step 8. The legacy text said the surcharge is also computed before the reduction. [T2]

**Church tax rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Church tax for members, charged on the income tax. Set by each state's church tax rules | 8% or 9% | Ministry booklet, 2025 edition: "beträgt je nach Bundesland 8 oder 9 Prozent" |

## Step 13: Reviewer Escalation Protocol

When the assistant identifies a [T2] situation:

~~~
REVIEWER FLAG
Tier: T2
Client: [name]
Situation: [description]
Issue: [what is ambiguous]
Options: [possible treatments]
Recommended: [most likely correct treatment and why]
Action Required: Steuerberater must confirm before advising client.
~~~

When the assistant identifies a [T3] situation:

~~~
ESCALATION REQUIRED
Tier: T3
Client: [name]
Situation: [description]
Issue: [outside the scope of this Guide]
Action Required: Do not advise. Refer to Steuerberater. Document gap.
~~~

## Step 14: Test Suite

The legacy tests carried computed amounts and city multipliers that no allowed page prints. Each test now checks the rule, not an amount.

### Test 1: Standard computation, Berlin

**Input:** Sole proprietor in Berlin, profit above the allowance, no add-backs, no reductions, no losses.
**Expected output:** The assistant does not quote a multiplier for Berlin. It asks for the trade tax notice or the city's decision. It then follows the order shown in the example under Step 10: round down to full hundreds, take off the allowance, apply the base rate, apply the multiplier. The income tax reduction is four times the base amount, limited by both caps in Step 8.

### Test 2: Below Freibetrag

**Input:** Sole proprietor in Hamburg, trade income below the allowance in the Step 5 table.
**Expected output:** Base amount nil. No trade tax. No reduction under § 35 EStG, because there is no base amount. A return only if § 25(1) no. 6 or no. 7 GewStDV applies.

### Test 3: Low Hebesatz, full offset

**Input:** Sole proprietor in a municipality with a low multiplier. The trade tax actually payable is lower than four times the base amount. There is enough income tax on the commercial income.
**Expected output:** The reduction is limited to the trade tax actually payable (§ 35(1) sentence 5 EStG). The rest is not used and is not carried forward. The assistant states the floor with its year: the 2026 figure from the ministry booklet, and the higher figure only from collection period 2027.

### Test 4: Munich, high Hebesatz

**Input:** Sole proprietor in Munich, profit well above the allowance, no add-backs, no reductions.
**Expected output:** The assistant reads the multiplier from the city's notice. It compares four times the base amount with the trade tax actually payable. Where the trade tax is higher, the part above four times the base amount is not covered by the reduction. The assistant does not state an "effective rate".

### Test 5: Freiberufler (no GewSt)

**Input:** Self-employed architect working alone, no other activity.
**Expected output:** Architects are named in § 18(1) no. 1 EStG. Not a commercial business. Trade tax does not apply and no trade tax return is required.

### Test 6: Vorauszahlungen computation

**Input:** The last trade tax assessment shows a tax for the year. No adjustment has been made.
**Expected output:** Four prepayments, each one quarter of that tax, rounded down to full euros, due on 15 February, 15 May, 15 August and 15 November. Each is set only if it reaches the minimum in the Step 9 table.

### Test 7: Anrechnung limited by low ESt

**Input:** Sole proprietor whose income tax on the commercial income is lower than four times the base amount and lower than the trade tax.
**Expected output:** The reduction equals the income tax that falls on the commercial income (the maximum reduction amount). The rest is not used.

## PROHIBITIONS

- NEVER apply Gewerbesteuer to a natural person whose only activity is a free profession within § 18 EStG. A capital company pays by legal form even with a free profession (§ 2(2) GewStG), and for a partnership the rows on § 15(3) EStG in Step 1 decide.
- NEVER quote a municipal multiplier from memory or from this Guide. Read it from the municipality's notice or decision for the year.
- NEVER state the multiplier floor without its year. The figure printed today in § 16(4) GewStG starts in collection period 2027.
- NEVER forget the allowance in the Step 5 table for sole proprietors and partnerships, and NEVER give it to a GmbH or AG.
- NEVER print the add-back shares of § 8 no. 1 GewStG as percentages. The law gives them in words, and each item has its own share.
- NEVER add anything back before the sum of the items has passed the allowance in the Step 3 table.
- NEVER use a fixed percentage of the Einheitswert as the property reduction. § 9 no. 1 GewStG now deducts the Grundsteuer booked as a business expense.
- NEVER leave out the two caps on the § 35 EStG reduction: the trade tax actually payable, and the income tax on the commercial income.
- NEVER work out a combined rate, an "effective burden" or a break-even multiplier.
- NEVER apply the § 35 EStG reduction to church tax.
- NEVER carry an unused § 35 EStG amount forward.
- NEVER use the income tax loss share for trade tax losses, and NEVER carry a trade loss back.
- NEVER classify a mixed-activity client without flagging the point for Steuerberater review.

## The method, step by step

1. Decide whether there is a commercial business: § 2 GewStG with § 15(2) and § 18 EStG. A company pays by legal form (§ 2(2) GewStG). A free profession does not pay. https://www.gesetze-im-internet.de/gewstg/__2.html
2. Check the start-up notices: opening a commercial business is reported to the municipality, and the further information goes to the tax office electronically within one month (§ 138 AO). https://www.gesetze-im-internet.de/ao_1977/__138.html
3. Take the profit from the business as worked out for income tax (§ 7 GewStG). Trade tax itself is not a business expense (§ 4(5b) EStG). https://www.gesetze-im-internet.de/gewstg/__7.html
4. Work out the add-backs of § 8 GewStG: the sum of the items at their shares, less the allowance, one quarter of the rest, then the other add-backs. https://www.gesetze-im-internet.de/gewstg/__8.html
5. Work out the reductions of § 9 GewStG, above all the Grundsteuer on business real property and profit shares from partnerships. https://www.gesetze-im-internet.de/gewstg/__9.html
6. Deduct trade losses carried forward under § 10a GewStG, within the base and the share in Step 4. https://www.gesetze-im-internet.de/gewstg/__10a.html
7. Round the trade income down to full hundreds of euros, take off the allowance, and apply the base rate to get the base amount (§ 11 GewStG). https://www.gesetze-im-internet.de/gewstg/__11.html
8. Read the multiplier of each municipality with a permanent establishment from that municipality's own notice or decision, and apply it (§ 16 GewStG). With several municipalities, the base amount is apportioned first (§ 28 GewStG, form GewSt 1 D). https://www.gesetze-im-internet.de/gewstg/__16.html
9. File the return GewSt 1 A electronically through ELSTER (§ 14a GewStG) by the deadline in § 149 AO, if § 25 GewStDV requires a return. https://www.elster.de/eportal/formulare-leistungen/alleformulare/gewst
10. Pay the prepayments on the four due dates of § 19 GewStG and the balance within one month of the trade tax notice (§ 20 GewStG). https://www.gesetze-im-internet.de/gewstg/__19.html
11. In the owner's or partner's income tax return, claim the reduction of § 35 EStG: four times the base amount, within both caps. https://www.gesetze-im-internet.de/estg/__35.html

## Ask the client first

- What exactly do you do, and do you work alone, in a partnership or through a company? Does any part of the activity involve selling goods or reselling other people's products?
- In which municipality or municipalities does the business have premises, and did it move during the year?
- What did the business pay in interest, rent and leases (movable and immovable assets separately) and licence fees in the year?
- Does the business own real property, and was Grundsteuer on it booked as a business expense? Does it hold shares in partnerships or companies?
- Was a trade loss carry-forward determined at the end of last year?
- What does the last trade tax notice show: base amount, multiplier, prepayments?

## When to refuse or refer

- The multiplier of a named municipality. It is on no federal page. Send the client to the municipality's notice or decision.
- Any combined rate, effective burden or break-even multiplier. No official page prints one.
- Organschaft (a company that counts as a permanent establishment of its parent, § 2(2) sentence 2 GewStG).
- Permanent establishments abroad, foreign dividends, controlled foreign company income (§ 7 sentences 7 and 8, § 9 no. 3, 7 and 8 GewStG).
- Apportionment between several municipalities beyond the basic rule, including wind, solar and energy storage businesses (§ 29 GewStG).
- The extended property reduction for property businesses (§ 9 no. 1 sentences 2 to 6 GewStG).
- Sale or closure of a business or of a partnership share (§ 7 sentence 2 GewStG), and loss use after a change of partners or of shareholders (§ 10a GewStG, § 8c and § 8d KStG).
- Partnerships that have opted to be taxed as companies (§ 2(8) GewStG).
- Home workers with the reduced base rate (§ 11(3) GewStG), shipping businesses, banks and insurers.
- Whether a borderline activity is a free profession, and any case with both a free profession and a commercial activity. Refer to a Steuerberater.
- The church tax rate for one client: it is set by state church tax rules, which are not on the federal pages.

## Sources

- GewStG § 2, § 3, § 4, § 5, § 6, § 7 (who pays, tax base): https://www.gesetze-im-internet.de/gewstg/__2.html and https://www.gesetze-im-internet.de/gewstg/__3.html and https://www.gesetze-im-internet.de/gewstg/__4.html and https://www.gesetze-im-internet.de/gewstg/__5.html and https://www.gesetze-im-internet.de/gewstg/__6.html and https://www.gesetze-im-internet.de/gewstg/__7.html
- GewStG § 8, § 9, § 10, § 10a (add-backs, reductions, period, losses): https://www.gesetze-im-internet.de/gewstg/__8.html and https://www.gesetze-im-internet.de/gewstg/__9.html and https://www.gesetze-im-internet.de/gewstg/__10.html and https://www.gesetze-im-internet.de/gewstg/__10a.html
- GewStG § 11, § 14, § 14a, § 14b, § 16 (base amount, return, surcharge, multiplier): https://www.gesetze-im-internet.de/gewstg/__11.html and https://www.gesetze-im-internet.de/gewstg/__14.html and https://www.gesetze-im-internet.de/gewstg/__14a.html and https://www.gesetze-im-internet.de/gewstg/__14b.html and https://www.gesetze-im-internet.de/gewstg/__16.html
- GewStG § 19, § 20 (prepayments, settlement): https://www.gesetze-im-internet.de/gewstg/__19.html and https://www.gesetze-im-internet.de/gewstg/__20.html
- GewStG § 28, § 29, § 31, § 33 (apportionment): https://www.gesetze-im-internet.de/gewstg/__28.html and https://www.gesetze-im-internet.de/gewstg/__29.html and https://www.gesetze-im-internet.de/gewstg/__31.html and https://www.gesetze-im-internet.de/gewstg/__33.html
- GewStG § 35a, § 36 (travelling trade, start dates): https://www.gesetze-im-internet.de/gewstg/__35a.html and https://www.gesetze-im-internet.de/gewstg/__36.html
- GewStDV § 25 (who must file): https://www.gesetze-im-internet.de/gewstdv_1955/__25.html
- EStG § 2, § 4, § 15, § 18, § 35, § 51a: https://www.gesetze-im-internet.de/estg/__2.html and https://www.gesetze-im-internet.de/estg/__4.html and https://www.gesetze-im-internet.de/estg/__15.html and https://www.gesetze-im-internet.de/estg/__18.html and https://www.gesetze-im-internet.de/estg/__35.html and https://www.gesetze-im-internet.de/estg/__51a.html
- SolzG § 3 (base of the solidarity surcharge): https://www.gesetze-im-internet.de/solzg_1995/__3.html
- AO § 1, § 108, § 138, § 149, § 152, § 184, § 233a, § 238, § 240: https://www.gesetze-im-internet.de/ao_1977/__1.html and https://www.gesetze-im-internet.de/ao_1977/__108.html and https://www.gesetze-im-internet.de/ao_1977/__138.html and https://www.gesetze-im-internet.de/ao_1977/__149.html and https://www.gesetze-im-internet.de/ao_1977/__152.html and https://www.gesetze-im-internet.de/ao_1977/__184.html and https://www.gesetze-im-internet.de/ao_1977/__233a.html and https://www.gesetze-im-internet.de/ao_1977/__238.html and https://www.gesetze-im-internet.de/ao_1977/__240.html
- Federal Law Gazette 2026 I no. 197 (amending law of 29 June 2026, § 16(4) sentence 2 GewStG): https://www.recht.bund.de/bgbl/1/2026/197/regelungstext.pdf?__blob=publicationFile
- State decree of 5 November 2025 (Federal Fiscal Court ruling of 6 June 2019, file number IV R no. 30/16, written in Germany without the "no."; Bundessteuerblatt 2020 II page 649): https://www.bundesfinanzministerium.de/Content/DE/Standardartikel/Themen/Steuern/Steuerarten/Gewerbesteuer/2025-11-05-gle-aufhebung-gle-01-10-20-anl.pdf?__blob=publicationFile&v=3
- EGAO Art. 97 § 36 (special deadlines, tax periods 2020 to 2024 only): https://www.gesetze-im-internet.de/aoeg_1977/art_97__36.html
- ELSTER, trade tax return GewSt 1 A, apportionment declaration GewSt 1 D, list of all forms: https://www.elster.de/eportal/formulare-leistungen/alleformulare/gewst and https://www.elster.de/eportal/formulare-leistungen/alleformulare/gewstzerl and https://www.elster.de/eportal/formulare-leistungen/alleformulare
- Finance ministry, tax booklet "Steuern von A bis Z", 2025 edition (chapters Gewerbesteuer and Kirchensteuer): https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9

## Disclaimer

This Guide and its outputs are provided for informational and computational purposes only and do not constitute tax, legal, or financial advice. Open Accountants and its contributors accept no liability for any errors, omissions, or outcomes arising from the use of this Guide. All outputs must be reviewed and signed off by a qualified professional (such as a Steuerberater or Wirtschaftsprüfer) before filing or acting upon.

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
