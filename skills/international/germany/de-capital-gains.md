---
name: de-capital-gains
description: "Use this skill for any German capital gains tax question. Trigger on: \"Abgeltungsteuer\", \"capital gains Germany\", \"CGT Germany\", \"Kapitalertragsteuer\", \"Sparer-Pauschbetrag\", \"sell shares Germany\", \"German exit tax\", \"Wegzugsbesteuerung\", \"leaving Germany tax shares\", \"crypto Germany CGT\", \"German investment gains\", \"German shareholder 1% rule\". Covers Abgeltungsteuer flat rate, annual exemption, offsetting losses, exit tax on departure."
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

# Capital gains tax in Germany (Abgeltungsteuer)

How Germany taxes a private investor on gains from shares, bonds, funds and derivatives, on large shareholdings, on crypto and other private sales, and on leaving the country with shares. It is for individuals who hold these assets privately, not in a business. Figures are for tax year 2026. The statute figures are read from the consolidated federal law pages. The church tax range is from the finance ministry's tax booklet, 2025 edition, the latest one published.

## Section 1: Quick Reference

| Field | Value |
| --- | --- |
| Country | Germany |
| System | Abgeltungsteuer: a flat tax on private investment income, withheld by German banks as Kapitalertragsteuer |
| Rate | Flat income tax rate plus solidarity surcharge, plus church tax for members. See the rates tables below |
| Annual allowance (Sparer-Pauschbetrag) | See the allowance table in Section 3 |
| Loss offsetting | Investment losses only offset investment income. Share losses only offset share gains |
| Large shareholdings | Not under the flat tax. Partial-income method, Section 5 |
| Crypto and other private sales | Not under the flat tax. Holding period rules, Section 7 |
| Exit tax | Yes, on leaving Germany with a qualifying shareholding or a large fund holding, Section 6 |
| Primary legislation | Einkommensteuergesetz (EStG) §17, §20, §23, §32d, §52; Außensteuergesetz (AStG) §6, §21; Investmentsteuergesetz (InvStG) §16, §19, §20, §21, §56 |
| Tax authority | Local Finanzamt. Bundeszentralamt für Steuern for central procedures |
| Verified by | Pending. German Steuerberater sign-off required |

**Flat tax rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__32d.html |
| Income tax on private investment income | 25% | §32d(1) sentence 1 EStG: "beträgt 25 Prozent" |

**Solidarity surcharge**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__4.html |
| Solidarity surcharge, charged on the tax and not on the income | 5.5% | §4 SolzG: "Der Solidaritätszuschlag beträgt 5,5 Prozent der Bemessungsgrundlage" |

**Church tax**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Church tax for members, charged on the tax and not on the income | 8% or 9% | Set by each state's church tax rules: "beträgt je nach Bundesland 8 oder 9 Prozent" |

The surcharge and the church tax are each a share of the flat tax, so the total burden is the flat rate raised by those shares. For a church member the flat tax itself is reduced first, by the formula in §32d(1) EStG on the page linked in the flat tax table. The official pages do not print a single combined rate, so this Guide does not state one.

## Section 2: What is Taxed: Abgeltungsteuer

- **Abgeltungsteuer scope.** The flat tax applies to private investment income under §20 EStG: gains from selling shares, bonds, fund units and ETFs; dividends; interest; gains from derivatives, CFDs and options.
- **Not in scope.** Crypto assets and other private sales fall under §23 EStG (Section 7). Shareholdings at or above the threshold in Section 5 fall under §17 EStG. Assets held in a business are outside this Guide.
- **Final withholding tax nature.** German banks withhold the tax automatically and it settles the liability. Income taxed this way is not added to the progressive income tax base.
- **Bought before 2009.** The flat tax on sale gains only covers shares bought after 31 December 2008. A gain on shares bought earlier is outside the flat tax and is not taxed, unless the holding is substantial (Section 5): §17 EStG has no such start date. This covers shares only. Bonds follow a different start rule. See §52(28) EStG at https://www.gesetze-im-internet.de/estg/__52.html Fund units bought before 2009 and never held in a business have their own rule: growth up to 31 December 2017 is tax-free, and later growth is taxed only above the allowance in the table at the end of this section. That allowance is given once, not each year: the tax office records what is left until it is used up. Units within §21(2a) and (2b) of the InvStG in force to 31 December 2017 are not covered.
- **Working out the gain.** The gain is the sale proceeds, less the costs directly tied to the sale, less the purchase cost. Amounts not in euro are converted into euro: the sale proceeds at the sale date and the purchase cost at the purchase date. For securities of the same kind held in one custody account, fund units included, the first lots bought count as the first lots sold. See §20(4) EStG at https://www.gesetze-im-internet.de/estg/__20.html
- **Option to use the progressive rate (Günstigerprüfung).** On request in the return, investment income is taxed at the client's normal rate instead, when that gives a lower total tax. See §32d(6) EStG at https://www.gesetze-im-internet.de/estg/__32d.html
- **Income with no German withholding must be declared.** Gains and income paid by a foreign bank or broker, with no German tax withheld, go in the income tax return. See §32d(3) EStG at https://www.gesetze-im-internet.de/estg/__32d.html

**Funds and ETFs: part of the income is tax-free (Teilfreistellung)**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/invstg_2018/__20.html |
| Equity funds (Aktienfonds), share of income that is tax-free for a private investor | 30% | §20(1) InvStG: "Steuerfrei sind bei Aktienfonds 30 Prozent der Erträge" |
| Property funds (Immobilienfonds), tax-free share | 60% | §20(3) InvStG: "Bei Immobilienfonds sind 60 Prozent der Erträge steuerfrei" |
| Foreign property funds (Auslands-Immobilienfonds), tax-free share | 80% | §20(3) InvStG: "Bei Auslands-Immobilienfonds sind 80 Prozent der Erträge steuerfrei" |

Mixed funds get half of the equity fund share. The law states it as "die Hälfte" and gives no number. Higher shares apply to units held in a business or by a company; those are outside this Guide.

When fund units are sold, the gain is reduced by the advance lump sums (Vorabpauschalen) already taxed while the units were held. A German bank does this itself. With a foreign broker the client must do it. See §19(1) InvStG at https://www.gesetze-im-internet.de/invstg_2018/__19.html The tax-free share in the table cuts a loss, and the related costs, by the same share. See §21 InvStG at https://www.gesetze-im-internet.de/invstg_2018/__21.html

**Fund units bought before 2009**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/invstg_2018/__56.html |
| One-time allowance for taxable gains on fund units bought before 2009 and never held in a business (growth from 1 January 2018 on). What is left carries on until used up | EUR 100,000 | §56(6) InvStG: "soweit der Gewinn aus der Veräußerung von bestandsgeschützten Alt-Anteilen 100 000 Euro übersteigt" |

## Section 3: Annual Exemption (Sparer-Pauschbetrag)

Each individual has an annual allowance against investment income:

**Sparer-Pauschbetrag allowance table**

| Status | Allowance | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__20.html |
| Single individual | EUR 1,000 | §20(9) sentence 1 EStG: "ein Betrag von 1 000 Euro abzuziehen (Sparer-Pauschbetrag)" |
| Jointly assessed couple | EUR 2,000 | §20(9) sentence 2 EStG: "ein gemeinsamer Sparer-Pauschbetrag von 2 000 Euro" |

- **Allowance coverage and carry-forward.** The allowance covers all investment income together (dividends, interest and gains). It replaces the running costs of investing, such as custody or advice fees: §20(9) rules out deducting those. The purchase cost and the costs of the sale itself still reduce the gain under §20(4) EStG. An unused allowance cannot be carried forward to a later year, but an allowance the banks did not fully use in the year can be claimed in that year's return under §32d(4) EStG.
- **Freistellungsauftrag.** Instruct each German bank to apply the allowance, split across banks up to the limit in the table. The order is only valid with the client's tax identification number. See §44a(2a) EStG at https://www.gesetze-im-internet.de/estg/__44a.html

## Section 4: Loss Offsetting Rules

- **Loss offsetting (Verlustverrechnungstopf).** Investment losses can only be set against investment income, never against salary or other income. Losses from selling shares can only be set against gains from selling shares. Other investment losses can be set against any investment income. Unused losses carry forward to later years with no time limit. There is no carry-back. See §20(6) EStG at https://www.gesetze-im-internet.de/estg/__20.html
- **No yearly cap in the current text.** Older material mentions a yearly cap on losses from derivatives and from worthless assets. The current text of §20(6) EStG has no such cap.
- **Verlustbescheinigung.** A bank carries the client's losses forward inside that bank. To use them in the return instead, for example against gains at another bank, the client asks the bank for a loss certificate. The request cannot be withdrawn and must reach the bank by 15 December of the current year. See §43a(3) EStG at https://www.gesetze-im-internet.de/estg/__43a.html

## Section 5: Substantial Shareholdings: Different Rules

For a substantial holding in a company, a gain on sale is business-type income under §17 EStG and is NOT taxed under the Abgeltungsteuer. It is taxed under the partial-income method (Teileinkünfteverfahren) at the client's progressive income tax rate.

**When a holding is substantial**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__17.html |
| Minimum share of the company's capital, held directly or indirectly at any time in the last five years | 1% | §17(1) sentence 1 EStG: "zu mindestens 1 Prozent beteiligt war" |

**Partial-income method: the tax-free share**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__3.html |
| Share of the sale price that is tax-free | 40% | §3 Nr. 40 EStG, letter c for sales under §17: "40 Prozent" |

**Partial-income method: the deductible share of costs**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__3c.html |
| Share of acquisition cost and selling costs that may be deducted | 60% | §3c(2) EStG: "nur zu 60 Prozent abgezogen werden" |

**Allowance against the gain**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__17.html |
| Allowance against the gain, scaled down to the share of the company that was sold | EUR 9,060 | §17(3) sentence 1 EStG: "soweit er den Teil von 9 060 Euro übersteigt" |
| The allowance shrinks by the amount by which the gain exceeds this, scaled the same way | EUR 36,100 | §17(3) sentence 2 EStG: "den Teil von 36 100 Euro übersteigt" |

- **Applicability regardless of company location.** This applies whether the company is German or foreign.
- **Progressive rate.** The taxable part is added to the client's other income. The income tax tariff is not repeated here; use the German income tax Guide for the tariff.

## Section 6: Exit Tax (Wegzugsbesteuerung): CRITICAL

- **Exit tax imposition.** Germany taxes the unrealised gain on a substantial shareholding when an individual leaves (§6 AStG). See https://www.gesetze-im-internet.de/astg/__6.html
- **Qualifying holding.** Shares within §17(1) EStG, that is, the threshold in the Section 5 table.
- **Qualifying person.** An individual who was fully liable to German tax for at least seven of the last twelve years before the trigger.
- **Trigger.** Ending full German tax liability by giving up the home or habitual abode in Germany; a gift or inheritance passing the shares to a person not fully liable in Germany; or any other loss or limit of Germany's right to tax the gain.
- **What happens.** A deemed sale at market value at the moment of the trigger. The unrealised gain is taxed as if the shares had been sold.
- **Exit tax rate.** For company shares: partial-income method at the progressive rate, as in Section 5. For fund units: the deemed gain is investment income under the flat tax, with the tax-free share from Section 2. The partial-income method does not apply to funds. See §16(3) InvStG at https://www.gesetze-im-internet.de/invstg_2018/__16.html No tax is withheld on the deemed gain, so it is assessed in the return.
- **Payment.** On request the tax can be paid in seven equal annual instalments, with no interest. The request is normally granted only against security. The first instalment is due within one month of the assessment notice, the others on 31 July of the following years. The unpaid tax falls due within one month if an instalment is missed, the client files for insolvency, or the client does not meet the reporting duties in §6(5) AStG. If shares are sold or transferred, or distributions pass the limit in §6(4) AStG, only the matching part falls due.
- **No more interest-free deferral inside the EU or EEA.** The earlier rule that allowed an open-ended, interest-free deferral on a move within the EU or EEA is not in the current §6 AStG. The instalment rule above applies whatever the destination. A client whose exit tax was triggered before 1 January 2022 stays under the old §6 AStG, including an old deferral that is still running, but with changes: an old deferral is now also withdrawn to the extent that distributions made after 16 August 2023 pass the limit in §21(3) AStG. See §21(3) AStG at https://www.gesetze-im-internet.de/astg/__21.html
- **Return to Germany.** If the absence is only temporary and the client becomes fully liable again within seven years, the tax claim falls away, to the extent that the shares were not sold, transferred or moved into a business in the meantime, no distributions above the limit in §6(3) AStG were made, and Germany's right to tax the gain is restored at least as it stood on leaving. On request the tax office can extend the period by up to five more years if the client still intends to return. In these cases the client can also ask to pay no instalments. If the claim does not fall away in the end, interest is charged for the delay.

**Fund units are covered too**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/invstg_2018/__19.html |
| Fund units count if the investor held at least this share of the fund's issued units in the last five years | 1% | §19(3) InvStG: "mindestens 1 Prozent der ausgegebenen Investmentanteile gehalten hat" |
| Or if the acquisition cost of the units held in the fund is at least | EUR 500,000 | §19(3) InvStG: "deren Anschaffungskosten mindestens 500 000 Euro betragen" |

Either test only counts if the client's taxable gains on the fund units are positive overall (§19(3) sentence 2 number 1 InvStG).

This is a major planning point for anyone leaving Germany with a significant company shareholding or a large fund position.

## Section 7: Crypto Assets

Crypto assets used as a means of payment, such as Bitcoin and Ether, are taxed as private sales under §23 EStG when held privately, not under the Abgeltungsteuer:

- **Sold within one year of purchase.** The gain is taxed at the client's progressive rate. Banks do not withhold; it goes in the return.
- **Sold after more than one year.** The sale is outside §23 and the gain is not taxed.
- **The yearly limit is a cliff, not an allowance.** Gains stay tax-free only if the client's total gain from all private sales in the calendar year is below the limit in the table. If the total reaches the limit, the whole gain is taxed, not just the part above it.
- **Losses.** Losses from private sales only offset gains from private sales, with carry-back and carry-forward under §23(3) EStG.
- **Each swap is a sale.** The ministry's ruling on crypto assets of 6 March 2025 treats a swap of one crypto asset for another as a sale and a new purchase, so the one-year period starts again. See https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2

**Private sales limit**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__23.html |
| Total yearly gain from private sales must be below this to stay tax-free | EUR 1,000 | §23(3) sentence 5 EStG: "weniger als 1 000 Euro betragen hat" |

The same section taxes private sales of land and buildings within ten years of purchase, with an exception for a home the client lived in. Property is outside this Guide.

See `de-crypto-tax` for full crypto analysis.

## The method, step by step

1. Sort each asset into its regime: private investment income under §20 EStG (flat tax), a substantial shareholding under §17 EStG (Section 5), or a private sale under §23 EStG such as crypto (Section 7). The rules and rates differ for each. https://www.gesetze-im-internet.de/estg/__20.html
2. For flat tax income, check what the German banks already withheld and whether a Freistellungsauftrag used the allowance in Section 3. https://www.gesetze-im-internet.de/estg/__44a.html
3. List income with no German withholding, for example from a foreign broker. It must go in the return under §32d(3) EStG. https://www.gesetze-im-internet.de/estg/__32d.html
4. Offset losses in the order the law allows: share losses against share gains only, other investment losses against any investment income. If losses sit at one bank and gains at another, ask the bank with the losses for a loss certificate by 15 December. https://www.gesetze-im-internet.de/estg/__43a.html
5. Test whether the progressive rate gives a lower tax (Günstigerprüfung under §32d(6) EStG) and request it in the return if so. Investment income is reported on Anlage KAP of the income tax return. https://www.gesetze-im-internet.de/estg/__32d.html
6. For a substantial shareholding, apply the partial-income method from Section 5 and add the taxable part to the client's other income. https://www.gesetze-im-internet.de/estg/__17.html
7. For crypto and other private sales, check each holding period, add up the year's gains and losses, and test the total against the limit in Section 7. https://www.gesetze-im-internet.de/estg/__23.html
8. If the client is leaving Germany or giving shares to someone abroad, test the exit tax conditions in Section 6 before the move, not after. https://www.gesetze-im-internet.de/astg/__6.html

## Ask the client first

- Are the assets held privately or in a business?
- When was each holding bought? Was any of it bought before 2009?
- Do you hold, or did you hold at any time in the last five years, a share of a company's capital at or above the threshold in Section 5?
- Is any account with a bank or broker outside Germany, so that no German tax was withheld?
- Are you a member of a church that collects church tax, and in which federal state do you live?
- For crypto and other private sales: what are the purchase and sale dates of each lot, and were there swaps between assets?
- Are you planning to leave Germany, or to give shares to someone who lives abroad?

## When to refuse or refer

- Exit tax (§6 AStG, and §19(3) InvStG for fund units): it needs the holding history and a market valuation. Refer to a German Steuerberater before the client leaves.
- Shares or fund units held in a business, or held by a company.
- Sales of land and buildings.
- Any case that turns on a tax treaty, including foreign tax credits on investment income.
- Crypto activity beyond buying and selling, such as mining, staking or lending. See `de-crypto-tax`.
- Tokens that work like securities. They can be investment income under §20 EStG instead (ministry ruling on crypto assets of 6 March 2025, paragraphs 81 and 82).
- The exact church tax rate for a client: it is set by state church tax rules, which are not on the federal pages.

## Section 8: Sources

- EStG §20 (investment income): https://www.gesetze-im-internet.de/estg/__20.html
- EStG §32d (flat tax): https://www.gesetze-im-internet.de/estg/__32d.html
- EStG §17 (substantial shareholdings): https://www.gesetze-im-internet.de/estg/__17.html
- EStG §23 (private sales): https://www.gesetze-im-internet.de/estg/__23.html
- EStG §3 Nr. 40 and §3c (partial-income method): https://www.gesetze-im-internet.de/estg/__3.html and https://www.gesetze-im-internet.de/estg/__3c.html
- EStG §43a and §44a (loss certificate, exemption order): https://www.gesetze-im-internet.de/estg/__43a.html and https://www.gesetze-im-internet.de/estg/__44a.html
- SolzG §4 (solidarity surcharge): https://www.gesetze-im-internet.de/solzg_1995/__4.html
- AStG §6 (exit tax): https://www.gesetze-im-internet.de/astg/__6.html
- InvStG §16, §19, §20, §21 and §56 (fund units): https://www.gesetze-im-internet.de/invstg_2018/__16.html and https://www.gesetze-im-internet.de/invstg_2018/__19.html and https://www.gesetze-im-internet.de/invstg_2018/__20.html and https://www.gesetze-im-internet.de/invstg_2018/__21.html and https://www.gesetze-im-internet.de/invstg_2018/__56.html
- EStG §52 (start date of the flat tax on sale gains): https://www.gesetze-im-internet.de/estg/__52.html
- AStG §21 (transition rule for exit tax): https://www.gesetze-im-internet.de/astg/__21.html
- Finance ministry ruling on the flat tax, 14 May 2025 (Einzelfragen zur Abgeltungsteuer): https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Abgeltungsteuer/2025-05-14-einzelfragen-zur-abgeltungsteuer.pdf?__blob=publicationFile&v=2
- Finance ministry ruling on crypto assets, 6 March 2025: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2

> **Working paper only.** Exit tax (§6 AStG) analysis requires shareholding history and market value determination. Engage a German Steuerberater before departing Germany with a shareholding at or above the Section 5 threshold, or a fund holding at or above the Section 6 thresholds.

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
