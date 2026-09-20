---
name: de-crypto-tax
description: Use this skill whenever asked about German cryptocurrency taxation. Trigger on phrases like "Krypto Steuer", "crypto tax Germany", "Haltefrist", "§23 EStG", "private Veräußerungsgeschäfte", "Freigrenze", "staking tax Germany", "mining income Germany", "BMF Schreiben", "DeFi tax Germany", "FIFO crypto", or any question about buying, selling, staking, mining, or lending crypto as a German tax resident. This skill covers the 1-year holding period, €1,000 Freigrenze, staking/mining classification, DeFi treatment, and the BMF guidance of 10.05.2022. ALWAYS read this skill before advising on German crypto taxation.
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

# Crypto tax in Germany

How Germany taxes a private person who buys, sells, swaps, stakes, lends or mines crypto assets (Kryptowerte). It covers the one-year holding period, the yearly limit for private sales, income from staking, lending and block creation, the order in which units count as sold, and the records the tax office expects. It is for individuals who are tax resident in Germany and hold crypto privately. Figures are for tax year 2026. The statute figures are read from the consolidated federal law pages. The rules on how to apply them come from the finance ministry's ruling on crypto assets of 6 March 2025, which replaced the ruling of 10 May 2022 and is the one in force. The form lines and the "need not be entered" rule come from the ELSTER instructions for the 2025 income tax return, the latest published: the 2026 forms are not out yet. The church tax range is from the finance ministry's tax booklet, 2025 edition.

## German Crypto Tax: Guide v2.0

Every paragraph number (Rz.) in this Guide points into the ruling of 6 March 2025: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2 Cite the 2025 version only. The legacy Guide's paragraph numbers do not match it and must not be used.

Not covered by this Guide: crypto held in a business (the ruling has separate rules for business assets); wages paid in crypto (the ruling leaves out employment income and wage tax); NFTs (the ruling says it does not deal with them, Rz. 5); people who are not tax resident in Germany; VAT. See "When to refuse or refer".

## Section 1: Quick Reference

**Section 1: Quick Reference**

| Field | Value |
| --- | --- |
| Country | Germany (Bundesrepublik Deutschland) |
| Tax | Einkommensteuer (income tax) on crypto gains and crypto income |
| Currency | EUR only |
| Tax year | Calendar year (1 January to 31 December) |
| Primary legislation | Einkommensteuergesetz (EStG) §23, §22 Nr. 3, §15, §20 |
| Key guidance | Finance ministry ruling of 6 March 2025, "Einzelfragen zur ertragsteuerrechtlichen Behandlung bestimmter Kryptowerte" (GZ: IV C 1 - S 2256/00042/064/043). It replaced the ruling of 10 May 2022 |
| Supporting legislation | Abgabenordnung (AO) §90, §147a, §149, §150, §153, §162; Kryptowerte-Steuertransparenz-Gesetz (KStTG) for platform reporting from 2026 |
| Tax authority | The local Finanzamt assesses the income tax. The Bundeszentralamt für Steuern (BZSt) receives the platform reports (Section 4.4) |
| Filing portal | ELSTER (elster.de) |
| Filing deadline | See Section 4.3 |
| Validated by | Pending. Requires sign-off by a German Steuerberater |
| Guide version | 2.0 (2026 refresh) |

### Core Rules Summary

**Core Rules Summary**

| Rule | Detail |
| --- | --- |
| Legal classification | Each crypto asset is an asset (Wirtschaftsgut). Held privately it is an "anderes Wirtschaftsgut" under §23(1) sentence 1 no. 2 EStG (Rz. 31 and 53, citing the Federal Fiscal Court judgment of 14 February 2023, IX R 3/22) |
| Taxable event | Sale for euro, swap for another crypto asset, or paying for goods or services with crypto, when not more than one year lies between purchase and sale |
| Holding period (Haltefrist) | More than one year between purchase and sale: outside §23, the gain is not taxed. The law says "nicht mehr als ein Jahr", so a sale exactly one year after purchase is still inside |
| Yearly limit (Freigrenze, §23(3) sentence 5) | See the private sales limit table below. It is a cliff, not an allowance: at or above the limit the WHOLE gain is taxed |
| Tax rate | The client's personal progressive income tax rate, plus solidarity surcharge and, for members, church tax. See "German Income Tax Rates 2026" below |
| Order of use | Individual identification comes first. Only if that is not possible: first in, first out for the holding period, and average cost for the values (first in, first out is allowed for the values as a simplification). Per wallet and per token. See 2.6 |
| Passive staking and lending income | Sonstige Einkünfte, §22 Nr. 3 EStG. Passive staking: "as a rule" (Rz. 48). Lending: Rz. 65 |
| Block creation (mining, forging) | Business income (§15 EStG) or other income (§22 Nr. 3 EStG). It depends on the facts. See 2.3 |
| No Abgeltungsteuer on payment tokens | Gains on currency or payment tokens held privately are §23 income at the personal rate, not flat tax income. Tokens that work like securities can be §20 income instead (Rz. 81 to 86) |
| Ten-year extension | Does not apply to currency or payment tokens (Rz. 63). The ruling says nothing on this point for other kinds of token |

**Private sales limit**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__23.html |
| The total gain from ALL private sales in the calendar year (crypto and any other private sales together, after setting off losses of the same year) must be BELOW this to stay tax-free. Per person | EUR 1,000 | §23(3) sentence 5 EStG: "weniger als 1 000 Euro betragen hat" |

**Private sales limit in older years**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2 |
| The same limit for assessment periods up to and including 2023. Only relevant for late or corrected returns | EUR 600 | Rz. 53: "bis Veranlagungszeitraum 2023: 600 €" |

**Other income limit**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__22.html |
| Income from services under §22 Nr. 3 (staking, lending, private block creation, airdrops received for a service, and any non-crypto income of this kind, ALL together) must be BELOW this in the calendar year to stay untaxed. A cliff. Tested on income after costs. Per person | EUR 256 | §22 Nr. 3 sentence 2 EStG: "weniger als 256 Euro im Kalenderjahr betragen haben" |

The two limits are separate. They are never added together, and using one does not use up the other. For a jointly assessed couple each limit applies to each person. The ELSTER instructions for 2025 print that sentence once for each limit; for private sales it reads "Bei einer Zusammenveranlagung gilt die Freigrenze i. H. v. 1.000 € für jede Person". See https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025

### German Income Tax Rates 2026

**German Income Tax Rates 2026**

The legacy Guide printed a full income tax table for 2025 here. It is removed. The tariff belongs to the German income tax Guide, `de-einkommensteuer-freelancer`: use it for the tariff zones and rates. Taxable crypto gains and crypto income are added to the client's other income and taxed at the client's personal progressive rate. This Guide never works out a rate.

**Basic allowance**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__32a.html |
| Basic allowance (Grundfreibetrag) 2026, single assessment. It is measured on the client's whole taxable income, not on the crypto gain alone | EUR 12,348 | §32a(1) EStG: "bis 12 348 Euro (Grundfreibetrag)" |

**Solidarity surcharge rate**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__4.html |
| Solidarity surcharge, charged on the income tax and not on the income | 5.5% | §4 SolzG: "Der Solidaritätszuschlag beträgt 5,5 Prozent der Bemessungsgrundlage" |

**Solidarity surcharge: when it is charged**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/solzg_1995/__3.html |
| Single assessment: the surcharge is charged only if the assessed INCOME TAX is above this. It is not a limit on income | EUR 20,350 | §3(3) no. 2 SolzG: "in anderen Fällen 20 350 Euro übersteigt" |
| Jointly assessed couple, per couple: same rule | EUR 40,700 | §3(3) no. 1 SolzG: "Einkommensteuergesetzes 40 700 Euro" |

**Church tax**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Church tax for members, charged on the income tax and not on the income | 8% or 9% | Ministry tax booklet, 2025 edition: "beträgt je nach Bundesland 8 oder 9 Prozent" |

- **Solidaritätszuschlag threshold.** The surcharge is a share of the income tax. It is charged only when the assessed income tax is above the limit in the table. Just above the limit it is phased in (§4 SolzG), so the full rate does not apply at once.
- **Kirchensteuer rate.** Only for members of a church that collects church tax. The rate is set by each state's church tax rules. The federal pages do not say which state uses which rate, so this Guide does not either.

**Flat tax, for comparison only**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__32d.html |
| Flat income tax rate on private investment income (Abgeltungsteuer). It does NOT apply to gains on payment tokens under §23. It is here because people ask. See `de-capital-gains` | 25% | §32d(1) sentence 1 EStG: "beträgt 25 Prozent" |

The official pages print no combined rate of income tax, surcharge and church tax, so this Guide states none.

### Conservative Defaults

**Conservative Defaults**

| Ambiguity | Default |
| --- | --- |
| Unknown acquisition date | For a gain: assume not more than one year held (taxable). For a loss: do not claim it until the purchase date is proven. Missing records count against the client (Rz. 89) |
| Unknown acquisition cost | Do not invent a cost. Flag it. Missing records count against the client (Rz. 89), and where the tax office cannot work out the base it estimates it under §162 AO (Rz. 92). As a working default until evidence is found, a cost of zero gives the highest gain |
| Unknown wallet attribution | STOP. The order-of-use rules work per wallet (Rz. 62), so the holding period cannot be worked out without the wallet history |
| Which units were sold | Individual identification first. If not possible: first in, first out for the holding period (Rz. 61). LIFO and HIFO are not named in the ruling |
| Mixed wallet (staked + unstaked) | Separate tracking required |
| Airdrop cost basis | Where the airdrop was received for a service, the cost is the value of the data or action given, which may be presumed, until shown otherwise, to equal the market price of the tokens received (Rz. 75). A value of zero is accepted only where no market price can be found at receipt (Rz. 73). The legacy Guide said the cost is always zero: that was wrong |

## Section 2: Rules and Classification

All Rz. numbers below are in the ruling of 6 March 2025: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2 The ruling sorts each crypto asset by its function, whatever it is called: currency or payment tokens (it names Bitcoin and Ether), utility tokens, security tokens, and mixed forms (Rz. 2 to 4).

### 2.1 Private Veräußerungsgeschäfte (§23 EStG)

- **Definition of private sale and gain formula.** Crypto held privately and sold when not more than one year lies between purchase and sale is a private sale (Rz. 53). Gain or loss = sale price less acquisition cost less income-related costs (Werbungskosten). See §23(3) sentence 1 EStG at https://www.gesetze-im-internet.de/estg/__23.html and Rz. 57.
- **Both a purchase and a sale are needed (Rz. 54).** A purchase is getting the asset from a third party for something in return. That covers crypto bought for euro, goods, services or other crypto, and also crypto received from block creation, lending and passive staking, and where it applies from an ICO or an airdrop.
- **Which moment counts (Rz. 55).** On a central platform: the times recorded there. For a direct purchase or sale without a middleman, for example on a decentralised platform: as a rule the times shown in the wallet. If the client wants the contract date to count, the client must prove it.
- **Costs are split (Rz. 57).** Werbungskosten must be split between taxable private sales and private sales that are not taxable, such as sales outside the one-year period.
- **Frequent trading can be a business (Rz. 52).** Repeated buying and selling, swaps included, can be a commercial activity. The ruling points to the tests for commercial securities and currency trading. This Guide does not decide that: refer.

**Taxable events:**
- Selling crypto for EUR or another state currency (Rz. 54)
- Exchanging crypto for another crypto asset, for example Bitcoin into Ether (Rz. 54)
- Paying for goods or services with crypto, including a card that swaps the client's crypto into euro at the till (Rz. 22, 54)

**Non-taxable events:**
- Moving crypto between the client's own wallets. A sale needs a transfer to a third party for something in return (Rz. 54), and this is not one. Document the move: the order-of-use rules work per wallet (Rz. 62), and the tax office can ask for wallet addresses and transaction hashes (Rz. 104)
- Buying crypto with state currency (a purchase, not a sale)
- Selling after more than one year: not taxable (Rz. 57)
- Gift: not a sale by the giver. The recipient takes over the giver's purchase date and cost (§23(1) sentence 3 EStG, Rz. 75)
- Redeeming a utility token for the product or service it stands for: not a sale (Rz. 79)
- Change output under the UTXO model: the part that flows back to the client's own key keeps the original purchase data (Rz. 56)

### 2.2 Staking as Sonstige Einkünfte (§22 Nr. 3 EStG)

**Staking treatment table**

| Aspect | Treatment |
| --- | --- |
| Classification | Passive staking (a staking pool or platform staking, WITHOUT creating blocks oneself): as a rule other income under §22 Nr. 3 EStG (Rz. 48). Creating blocks oneself as a validator (forging) follows the block creation rules in 2.3 |
| Taxable event | Receipt of staking rewards |
| Taxable amount | Market price in EUR at the time of acquisition (Rz. 48). Simplification: the time the reward is booked into the wallet on claiming may be used during the year. Rewards not yet claimed count at the latest at the end of the calendar year (Rz. 48a). A daily price is accepted if used consistently (Rz. 91) |
| Freigrenze | The other income limit in Section 1. One limit for ALL income from services together, crypto or not |
| Freigrenze behavior | A cliff: at or above the limit the entire amount is taxable. The test is on income after costs, see 3.4 |
| Holding period of rewards | Rewards count as acquired (Rz. 54). Each reward starts its own one-year period on receipt |
| Haltefrist extension | NO ten-year period for currency or payment tokens (Rz. 63). The legacy Guide cited Rz. 87 of the 2022 ruling for this |
| Masternode | Follows the rules for block creation by proof of stake (Rz. 50) |

### 2.3 Mining

**Mining classification table**

| Scenario | Classification |
| --- | --- |
| Block creation (mining or forging) that meets the business tests of §15(2) EStG: independent, lasting, done to make a profit, taking part in general economic trade | §15 EStG (Gewerbebetrieb). The ruling says block creation is NOT private asset management: it fits the picture of a service provider (Rz. 39). It is lasting when it is set up to be repeated (Rz. 36). Taking part in general trade is met already by offering computing power to the network (Rz. 38) |
| Block creation that fits no other income type, for example because it is not lasting | §22 Nr. 3 EStG, sonstige Einkünfte (Rz. 45) |
| Pool mining | A mining pool can be a co-entrepreneurship (Mitunternehmerschaft), depending on the contract. It is not one where the miner only supplies computing power to the pool operator for a fee. A staking pool is as a rule not one (Rz. 40). For §22 Nr. 3 it makes no difference whether the income comes through a mining pool, a staking pool or a cloud mining service (Rz. 46) |

The legacy Guide drew the line at "hobby, occasional, small scale" against "significant hardware". Those tests are not in the ruling. The tests are those of §15(2) EStG: https://www.gesetze-im-internet.de/estg/__15.html

**Commercial mining triggers:**
- Gewerbesteuer obligation (municipal trade tax)
- Gewerbeanmeldung required. Legacy item, not checked on an official page for this Guide
- IHK membership. Legacy item, not checked on an official page for this Guide
- Full income tax on mining income at progressive rates
- Crypto received is valued at the market price at the time of acquisition (Rz. 43). With a cash-basis account (Einnahmenüberschussrechnung) the receipt is business income, and the cost is deducted only when the crypto is sold or withdrawn (Rz. 44)
- Depreciation (AfA) allowed on mining hardware

**Private block creation that is not a business (§22 Nr. 3):**
- The other income limit in Section 1 applies, together with all other income from services (Rz. 45)
- Receipts are both the block reward and the transaction fees (Rz. 34, 46), valued at the market price at the time of acquisition (Rz. 47)
- Costs of hardware and software (where needed as depreciation) and electricity are deductible as Werbungskosten (Rz. 47)
- No Gewerbesteuer

### 2.4 Lending (Crypto Lending / DeFi Lending)

**Lending treatment table**

| Aspect | Treatment |
| --- | --- |
| Interest received | §22 Nr. 3 EStG, sonstige Einkünfte (Rz. 65) |
| Taxable amount | Market price in EUR at the time of receipt (Rz. 65). The claiming simplification of Rz. 48a applies |
| Freigrenze | The other income limit in Section 1, shared with staking and all other §22 Nr. 3 income |
| Holding period of original coins | NOT extended to ten years for currency or payment tokens (Rz. 63) |
| Crypto received as the fee | Counts as acquired. A later sale follows the private sale rules (Rz. 65, 53 and following) |
| Return of lent coins | Legacy Guide: not a taxable event. The ruling does not say this in words. It describes lending as letting someone use the crypto for a time in return for a fee (Rz. 26, 65). Unverified |

### 2.5 DeFi Specific Treatments

The ruling describes decentralised finance and decentralised platforms (Rz. 20a) but gives tax rules for only some of the activities below. Where the last column says "not addressed", the classification is the legacy Guide's own view. It is unverified: do not present it to a client as the ministry's position.

**DeFi activity classification table**

| DeFi Activity | Classification | In the 2025 ruling? |
| --- | --- | --- |
| Token swap on DEX | §23 EStG disposal + acquisition. Same as a trade on a central platform | Yes. A swap is a sale (Rz. 54). Timing comes from the wallet (Rz. 55). The extended duty to cooperate applies as a rule (Rz. 89) |
| Liquidity provision (LP) | Legacy view: putting tokens into a pool is a §23 sale and a purchase of LP tokens | Not addressed |
| LP token removal | Legacy view: a §23 sale of the LP token and a new purchase of the tokens taken out | Not addressed |
| Yield farming rewards | Legacy view: §22 Nr. 3 at market price on receipt | Not addressed by name |
| Airdrops | §22 Nr. 3 ONLY where the client had to do or give something for it, for example post about the project or hand over personal data beyond what the transfer needs (Rz. 70, 71). Where chance also decides who receives, the link between service and reward is broken or overlaid (Rz. 72). With no service at all a gift is possible, and gift tax rules apply (Rz. 74). Valued at market price at receipt, or zero where no price can be found (Rz. 73) | Yes, Rz. 70 to 75 |
| Hard forks (new coins) | No §22 Nr. 3 income. The cost of the old coins is SPLIT between old and new coins by their market prices at the fork. The new coins take the purchase date of the old coins. If the new coins have no value, the whole cost stays with the old coins. The legacy Guide said cost zero and purchase date equals fork date: that was wrong | Yes, Rz. 67, 68 |
| Wrapped tokens (e.g., WETH) | Legacy view: potentially a §23 swap. Unverified: refer. Treating it as a sale is not a safe default: a sale can also create a loss, and it restarts the one-year period (Rz. 55, 57) | Not addressed |
| NFT sale | The ruling does NOT cover NFTs (Rz. 5). The legacy Guide said "§23, same as any crypto asset". Unverified: refer | Expressly left out |
| Governance token rewards | Legacy view: §22 Nr. 3 at market price | Not addressed |
| Utility tokens | Redeeming for the product or service: not a sale (Rz. 79). Selling a purchased utility token: can be a §23 private sale, also when it is used as a means of exchange (Rz. 80) | Yes |
| Security tokens | Can be securities or other financial instruments. Current income and sale gains can then fall under §20 EStG, depending on the terms of the token (Rz. 81 to 86). Refer | Yes |

### 2.6 FIFO Method (not mandatory: the order of use)

The legacy heading said "FIFO Method (Mandatory)". That was wrong. The ruling's rules on which units count as sold (Verwendungsreihenfolge, Rz. 61 and 62) are:

- **Individual identification comes first (Einzelbetrachtung).** Where the client can show which units were sold, those units count.
- **If that is not possible, two different fallbacks apply.** For the HOLDING PERIOD, the units of that token bought first count as sold first. For the VALUES (cost), the average method applies. As a simplification the client may instead assume first in, first out for the values as well.
- **Per wallet, not across wallets.** "Es gilt eine walletbezogene Betrachtung." The legacy Guide allowed one first in, first out queue across all wallets: that option is not in the ruling.
- **Per token.** Each token name held in a wallet (Bitcoin, Ether and so on) carries its own choice.
- **Stick to it.** Inside a wallet the chosen method stays until every unit of that token in that wallet has been sold. After a full sale and a new purchase of that token, the method may be changed.
- **Document it.** The tax office may ask which method was used for which wallet and token, and for records of reallocations within wallets ("Umschichtungen innerhalb von Wallets", Rz. 103).
- LIFO and HIFO are not named anywhere in the ruling. The legacy Guide said they are "NOT permitted": the ruling does not say that in words, but it offers only the methods above.

**Per-wallet FIFO example:**
- Wallet A: bought one Bitcoin on 1 January 2025, bought one more Bitcoin on 1 June 2025
- Wallet A: sold one Bitcoin on 15 March 2026, and the client cannot show which unit it was
- For the holding period the unit bought on 1 January 2025 counts as sold. It was held more than one year, so the sale is outside §23
- If the client CAN identify the unit sold as the one bought on 1 June 2025, individual identification wins, and the sale is inside the one-year period

## Section 3: Computation

### 3.1 Gain Calculation (§23)

- **Veräußerungsgewinn formula.** Veräußerungsgewinn = Veräußerungspreis less Anschaffungskosten less Werbungskosten. See §23(3) sentence 1 EStG at https://www.gesetze-im-internet.de/estg/__23.html
- **Veräußerungspreis.** Sale for euro: the agreed price. Swap into another crypto asset: the market price of the crypto RECEIVED at the time of the swap. If that cannot be found, the market price of the crypto given up is accepted (Rz. 58). Paying for goods or services: the price agreed in euro, or, if none was stated, the market price of the crypto given up (Rz. 60).
- **Anschaffungskosten.** The euro value at purchase, for the units that count as sold under 2.6. For crypto received in a swap: the market price of the crypto given up, plus any incidental purchase costs (Rz. 59).
- **Werbungskosten.** Transaction fees paid on the sale (Rz. 59). Split between taxable and non-taxable sales (Rz. 57).
- **Market price.** The price on a trading platform or a web-based price list (Rz. 43). A documented daily price may be used instead if one source and one method are used for both cost and proceeds (Rz. 91).

### 3.2 Annual Aggregation

- **Annual aggregation steps.** Step 1: Work out the gain or loss on each sale inside the one-year period. Step 2: Add up all gains and losses from §23 sales of the year, crypto and any other private sales together, separately for each person. Step 3: Test the total against the private sales limit in Section 1. Total BELOW the limit: entirely tax-free. Total AT OR ABOVE the limit: the entire total is taxable, not just the part above it. Step 4: If taxable, the total is added to the client's other income in the income tax return (Anlage SO). Step 5: The personal income tax rate applies. See `de-einkommensteuer-freelancer` for the tariff.
- **Below the limit.** The ELSTER instructions for 2025 say gains below the limit need not be entered in Anlage SO, and ask the client to enter losses all the same. See https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025 This is the 2025 text. The 2026 instructions are not out yet.

### 3.3 Loss Treatment (§23 Abs. 3)

**Loss treatment table**

| Rule | Detail |
| --- | --- |
| Offsetting within year | §23 losses offset §23 gains of the same calendar year, up to the amount of those gains (§23(3) sentence 7 EStG) |
| Cannot offset against other income | §23 losses ONLY offset §23 gains. They cannot be set against wages, business income, investment income or §22 Nr. 3 income, and they cannot be deducted under §10d EStG in the general way. The legacy Guide called this "horizontal": that label was wrong and is removed |
| Carry-back | To §23 income of the year immediately before, under the rules of §10d EStG (§23(3) sentence 8 EStG) |
| Carry-forward | To §23 income of the following years, under the rules of §10d EStG (§23(3) sentence 8 EStG) |
| Verlustvortrag application | The loss left over is formally determined: §10d(4) EStG applies (§23(3) sentence 8). On the 2025 form the client can waive the carry-back by ticking the box in the loss line of Anlage SO; the tax office then determines the remaining loss carried forward |

Source for the table: https://www.gesetze-im-internet.de/estg/__23.html The remaining loss is determined separately at the end of the year (§10d(4) sentence 1 EStG): https://www.gesetze-im-internet.de/estg/__10d.html The ELSTER instructions for 2025 ask the client to enter losses from private sales.

### 3.4 Staking/Mining Income Computation

- **Staking/Mining income steps.** Staking, lending and private block creation income (§22 Nr. 3): Step 1: Record the market price in EUR of each reward at the time of receipt. Step 2: Add up all §22 Nr. 3 receipts of the year: staking, lending fees, private block creation, airdrops received for a service, and any non-crypto income from services. Step 3: Deduct the directly related Werbungskosten, for example hardware, software and electricity for block creation (Rz. 47). Step 4: Test the RESULT against the other income limit in Section 1. Result BELOW the limit: not taxable. Result AT OR ABOVE the limit: the entire result is taxable. Step 5: A taxable result is added to the client's other income.
- **Order of steps 3 and 4.** The legacy Guide tested the limit on the gross rewards and deducted costs afterwards. That was wrong. The limit tests "Einkünfte", and for this kind of income Einkünfte are receipts less Werbungskosten. See §22 Nr. 3 at https://www.gesetze-im-internet.de/estg/__22.html and §2(2) EStG at https://www.gesetze-im-internet.de/estg/__2.html
- **Losses.** If the costs are higher than the receipts, the excess cannot be set against other income. It reduces §22 Nr. 3 income of the year before or of later years, under the rules of §10d EStG (§22 Nr. 3 sentences 3 and 4).

## Section 4: Filing

### 4.1 ELSTER Forms

The line numbers below are those of the 2025 form, as printed in the ELSTER instructions for the 2025 income tax return: https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025 Lines move from year to year, and the 2026 form is not published yet. Follow the labels on the form, not the numbers. The legacy Guide's line numbers matched neither the 2025 form nor this page and are removed.

**ELSTER forms table**

| Form | Purpose |
| --- | --- |
| Anlage SO (Sonstige Einkünfte) | Report §23 gains and losses and §22 Nr. 3 income |
| Anlage SO, block "Leistungen", lines 14 to 21 on the 2025 form | Income from mining, forging, passive staking, lending and airdrops, where it belongs to no other income type. Line 22: loss deduction for this income |
| Anlage SO, block "Private Veräußerungsgeschäfte", lines 34 to 66 on the 2025 form | Private sales. Crypto: lines 45 to 49 plus 56 and 57, as the detailed instructions and their block heading say. The overview sentence on the same page starts at line 43, but the same page also gives line 43 to the land block, so follow the form's labels. Line 66: loss deduction for private sales |
| Anlage G (Gewerbeeinkünfte) | Commercial block creation only |
| Anlage EÜR | Einnahmen-Überschussrechnung for a business |

### 4.2 Documentation Requirements

Part III of the ruling (Rz. 87 to 105) is new in the 2025 version. For crypto held privately the general duties to cooperate apply (Rz. 100).

**Documentation requirements table**

| Document or duty | What the ruling says |
| --- | --- |
| Truthful return, duty to cooperate | Statements in the return must be true and made to the best of the client's knowledge (§150(2) AO). The client must help establish the facts (§90 AO) (Rz. 88) |
| Trade history (all exchanges), foreign platforms | Trading on a central platform run from abroad triggers the EXTENDED duty to cooperate of §90(2) AO: the client must clear up the facts and obtain the evidence. That means in particular downloading the platforms' transaction overviews regularly and in full. Missing records and lost data, for example after a platform's insolvency or a hack, count against the client. As a rule the same applies to decentralised platforms (Rz. 89). Some providers limit how long overviews can be downloaded (Rz. 29a) |
| Wallet transaction records | The blockchain data sits in the client's sphere of information. Handing over a public key alone is not enough as evidence, but it can be used to check the client's figures (Rz. 87) |
| Tax reports (Steuerreports) from private providers | Can be used as the basis of the assessment if they look plausible: no sign that costs, wallets or platforms are missing, consistent in themselves, and not at odds with what the tax office knows. As a rule the report settings (prices used, order-of-use method) and the tax reasoning behind them must be shown. Manual changes must be marked and explained (Rz. 90). The tax office can ask for the files behind the report (Rz. 101) |
| Cost basis calculations | Each private sale should be traceable on its own (the ruling says "sollten"): at least the name or ticker and the number of units, the gain with cost and proceeds or the time and price of purchase and sale, and the holding period (Rz. 102) |
| Staking reward records with timestamps | For lending and other income from services: start, end, object, fee and terms (Rz. 102). Records of income from mining, forging, passive staking, lending and airdrops, and for an airdrop the conditions under which the tokens were handed out (Rz. 103) |
| Exchange confirmations / screenshots | Screenshots from a wallet or platform account can be requested to check single items, once the office has used its own means such as a block explorer (Rz. 101). In a single case the office can also ask for the source of funds, wallet balances at 31 December of the year and of the year before, wallet addresses, transaction hashes and platform account details (Rz. 104) |
| FIFO calculation spreadsheet | Record of the order-of-use method chosen (individual identification, average or first in, first out) for each wallet and token, and of reallocations within wallets (Rz. 103) |
| Prices | Purchase and sale prices in euro with the platform or price list they were taken from, where the trade was not in euro (Rz. 103). A daily price is accepted "bis auf Weiteres" if applied consistently (Rz. 91) |
| If the base cannot be worked out | The tax office estimates it under §162 AO. The estimate must aim at the real facts and must not be used as a penalty (Rz. 92) |

**How long to keep records.** The legacy Guide said ten years under §147 AO for every record. That was wrong for a private investor: the ruling applies §147 AO to business assets (Rz. 96). For private assets the ruling prints one retention rule only (Rz. 105), that of §147a AO:

**Retention duty for high-income private persons**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__147a.html |
| Records and documents on the receipts and costs must be kept SIX years if the sum of the client's positive income from employment, investments, letting and other income under §22 EStG (which includes private sales) is MORE THAN this in a calendar year. For a jointly assessed couple each person's own sum counts. The duty starts with the calendar year AFTER the one in which the threshold was passed, and ends after five calendar years in a row below it | EUR 500,000 | §147a(1) AO: "mehr als 500 000 * Euro im Kalenderjahr beträgt" |
| The same threshold from 1 January 2027. NOT the figure for 2026 | EUR 750,000 | Footnote on the page: "am 1. Januar 2027 jeweils die Angabe „500 000“ durch die Angabe „750 000“ ersetzt" |

Below that threshold neither the ruling nor §147a AO prints a retention period for a private investor. The burden stays with the client all the same. Rz. 102 asks for the cost, the purchase time and the holding period of every sale, so the purchase record is needed whenever a unit is sold, however long ago it was bought. For context, the general assessment period is four years, ten years where tax was evaded and five where it was reduced through gross negligence: §169(2) AO at https://www.gesetze-im-internet.de/ao_1977/__169.html

**Which years the new rules cover (Rz. 106).** The ruling applies to all open cases from its publication in the Federal Tax Gazette. For assessment periods up to and including 2024 the tax office does not object to prices fixed under the 2022 version of the ruling, or to records that differ from Rz. 87 and following.

### 4.3 Filing Deadlines

**Filing deadlines table**

| Scenario | Deadline |
| --- | --- |
| Without Steuerberater | At the latest seven months after the end of the calendar year (§149(2) AO) |
| With Steuerberater | At the latest the last day of February of the second calendar year after the tax year (§149(3) AO). The tax office can ask for the return earlier (§149(4) AO) |
| Voluntary filing (Antragsveranlagung) | The legacy Guide said "up to 4 years". The general assessment period is four years (§169(2) AO). How it runs for a voluntary return is not set out on the pages read for this Guide |
| Amended return (Berichtigung) | A client who finds out, before the assessment period ends, that a return was wrong or incomplete and that tax was or may be underpaid MUST report it without delay and put it right (§153(1) AO). The legacy Guide said a return can be amended only until the notice is final: that missed the duty |

Source for the table: https://www.gesetze-im-internet.de/ao_1977/__149.html and https://www.gesetze-im-internet.de/ao_1977/__153.html The pages do not say what happens when a deadline falls on a weekend, so this Guide states no calendar date.

**Does the client have to file at all?** A person with no wages must file when total income is above the basic allowance in Section 1 (for a jointly assessed couple: above twice the basic allowance). A return is also compulsory when a remaining loss deduction was formally determined at the end of the year before (§56 sentence 2 EStDV). See §56 EStDV at https://www.gesetze-im-internet.de/estdv_1955/__56.html For employees the rule is in §46 EStG:

**Employees: when crypto income forces a return**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__46.html |
| An assessment is compulsory if the positive sum of the client's TAXABLE income that had no wage tax withheld is MORE THAN this. It is a filing trigger, not an exemption | EUR 410 | §46(2) no. 1 EStG: "jeweils mehr als 410 Euro beträgt" |
| A different rule with the same number: for an employee who is assessed, such income is taken off again, so it stays untaxed, if it is NOT MORE THAN this in total. Above it, §46(5) EStG lets a regulation soften the step up to full taxation; this Guide does not cover that regulation | EUR 410 | §46(3) EStG: "insgesamt nicht mehr als 410 Euro betragen" |

### 4.4 Platform Reporting from 2026

New since the legacy Guide. Under the Kryptowerte-Steuertransparenz-Gesetz (KStTG), which puts the eighth change to the EU directive on administrative cooperation (known as DAC8) and the OECD's crypto reporting framework into German law, crypto service providers must, under certain conditions, collect data on their customers from reporting period 2026 and send it to the BZSt, for the first time in calendar year 2027. The data is due by 31 July of the following calendar year. It includes name, address, tax residence, tax identification number, date of birth, the name of the crypto asset, and aggregated transaction volumes, split into purchases and sales against state currency, against other crypto assets, for goods and services, and other transfers. The BZSt passes the data on by 30 September to the EU central register and partner states, receives data on foreign wallets held by German tax residents in return, and forwards it to the state tax offices for the assessment. NFT transactions are reported too. See https://www.bzst.de/DE/Unternehmen/Intern_Informationsaustausch/DAC8/Verfahren/verfahren_node.html

Providers must also get a self-certification from each user. For a customer relationship that existed before 31 December 2025 the provider must have it by 1 January 2027. A user who does not supply it after a reminder and a warning is blocked from reportable transactions.

The client's own duty to declare does not depend on any of this (§150(2) AO, Rz. 88).

## Section 5: Edge Cases

### 5.1 Crypto-to-Crypto Exchanges

- **Crypto-to-crypto exchange treatment.** Every crypto-to-crypto exchange, for example Bitcoin into Ether, is TWO events: 1. A sale of the Bitcoin, which realises a gain or loss under §23 if not more than one year was held (Rz. 54). 2. A purchase of the Ether. Its cost is the market price of the Bitcoin given up plus incidental purchase costs (Rz. 59), and its one-year period starts new: "Die Veräußerungsfristen des § 23 Absatz 1 Satz 1 Nummer 2 EStG beginnen nach jedem Tausch neu" (Rz. 55). The price source used must be documented (Rz. 103). The ruling names trading platforms and the web lists CoinMarketCap and CoinGecko as possible sources (Rz. 43).

### 5.2 Gifts and Inheritance

**Gifts and inheritance table**

| Scenario | Rule |
| --- | --- |
| Gift (Schenkung) | The recipient takes over the giver's purchase date AND cost (§23(1) sentence 3 EStG, Rz. 75) |
| Inheritance (Erbschaft) | The heir takes over the purchase date AND cost of the deceased. The ELSTER instructions for 2025 name both cases: "Bei unentgeltlichem Erwerb (zum Beispiel Erbschaft, Schenkung) rechnet Ihr Finanzamt dem Rechtsnachfolger die Anschaffung durch den Rechtsvorgänger zu" |
| Implication | If the giver or the deceased bought more than one year before the recipient sells, the sale is outside §23 |
| Schenkungsteuer | A separate tax under another law (ErbStG). See the table below. Outside the income tax scope of this Guide: refer |

Sources for the table: https://www.gesetze-im-internet.de/estg/__23.html and https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025

**Gift and inheritance tax: two personal allowances**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/erbstg_1974/__16.html |
| Spouse or registered civil partner: this much of the acquisition stays tax-free. An allowance, not a cliff. Applies in cases of unlimited gift and inheritance tax liability | EUR 500,000 | §16(1) no. 1 ErbStG: "des Ehegatten und des Lebenspartners in Höhe von 500 000 Euro" |
| Child (tax class I no. 2): same rule | EUR 400,000 | §16(1) no. 2 ErbStG: "in Höhe von 400 000 Euro" |

The allowance is not yearly. Everything received from the same person within ten years is added together (§14(1) ErbStG): https://www.gesetze-im-internet.de/erbstg_1974/__14.html Other relatives have lower allowances on the same page. How crypto is valued for gift tax is not covered here.

### 5.3 Stablecoins

- **Stablecoin treatment.** The 2025 ruling does not mention stablecoins. It sorts every crypto asset by its function, whatever it is called, and treats a token used as a means of exchange like a currency token (Rz. 2 to 4). The legacy Guide said: stablecoins (USDT, USDC, DAI) are "andere Wirtschaftsgüter", the same rules apply, a round trip from euro into a stablecoin and back within one year is taxable, and a movement in the dollar rate of a dollar stablecoin is a §23 event. That is the legacy Guide's own reading. It is unverified.

### 5.4 Lost/Stolen Crypto

- **Lost/stolen crypto treatment.** The legacy Guide said provably lost or stolen crypto, and scam losses, "may" be claimed as a §23 loss. The 2025 ruling says NOTHING of the kind: the words for theft and loss of assets do not appear in it. What it does say points the other way: a sale is a transfer of the asset to a third party for something in return (Rz. 54), and a §23 loss comes from a sale (Rz. 57). The legacy claim is removed. Do not tell a client that a lost key, a hack or a scam gives a deductible loss. Refer.
- The only thing the ruling says about hacks is about RECORDS: data lost through a platform's insolvency or a hacker attack counts against the client (Rz. 89).

### 5.5 ICO / Token Sales

- **ICO/token sale treatment.** Tokens bought in an ICO for euro or for other crypto are acquired (Rz. 25, 54). Cost = what was paid: euro, or the market price of the crypto given up (Rz. 59). A sale when not more than one year was held: §23 gain or loss. The issuer's side is a business matter (Rz. 76) and outside this Guide.
- The legacy Guide said a loss on worthless tokens can be realised "by provable abandonment". That is not in the ruling and is removed. A sale to a third party for a price, however small, is a sale under Rz. 54. Whether a sale for a token amount is accepted is a question for a Steuerberater.

### 5.6 Fork Coins

- **Fork coin treatment.** A hard fork does NOT create §22 Nr. 3 income (Rz. 68). If the coins held before the fork were purchased, the new coins count as purchased too, at the SAME time as the old coins. The cost of the old coins is split between old and new coins in the ratio of their market prices at the time of the fork. If no value can be given to the new coins, the whole cost stays with the old coins (Rz. 67, 68). A sale of the new coins is a §23 private sale when not more than one year lies between the purchase of the ORIGINAL coins and the sale.
- The legacy Guide said: cost zero, purchase date equals fork date, tax-free one year after the fork. All three were wrong. Under the ruling the period runs from the purchase of the original coins, so new coins from long-held originals can be sold outside §23 straight away.

### 5.7 Margin/Futures Trading

- **Margin/futures trading treatment.** The 2025 ruling does not address futures, contracts for difference, margin or leverage: none of those words appear in it. The law taxes gains on forward transactions (Termingeschäfte) as investment income under §20(2) sentence 1 no. 3 EStG: https://www.gesetze-im-internet.de/estg/__20.html Whether a given crypto derivative is such a transaction, and how leveraged spot trading is treated, is not settled on the pages read for this Guide. The legacy Guide's split ("futures and CFDs: §20; leveraged spot: §23") is unverified. See `de-capital-gains` for the flat tax rules and refer.

## Section 6: Worked Examples

The legacy examples used made-up euro amounts. Every amount in this Guide must be one an official page prints, so the examples are now in words. All amounts meant are the limits in the Section 1 tables.

### Example 1: Simple Sale Within Haltefrist

The client bought two units of a payment token on 15 March 2026 and sold one unit for euro on 1 August 2026, paying an exchange fee.

Gain = sale price less the purchase cost of that unit less the exchange fee (§23(3) sentence 1 EStG; Rz. 57, 59).
Not more than one year held, so the sale is inside §23.
If the client's total gain from ALL private sales in 2026 is at or above the private sales limit, the entire total is taxable income. If it is below the limit, it is tax-free.

### Example 2: Sale After Haltefrist

The client bought one Ether on 1 January 2025 and sold it on 15 January 2026.

More than one year held, so the sale is outside §23 and the gain is not taxed (Rz. 57). The Anlage SO instructions for 2025 ask only for crypto sales where not more than one year lies between purchase and sale. Keep the purchase evidence all the same: the tax office can ask for it (Rz. 100 to 104).

### Example 3: Staking Rewards

The client received passive staking rewards through 2026 and has no other §22 Nr. 3 income.

Each reward is recorded at its market price in euro at receipt, or at a consistent daily price (Rz. 48, 91). Add them up and deduct the directly related costs.
If the result is at or above the other income limit, the entire result is taxable as sonstige Einkünfte and is added to the client's other income.
Each reward also starts its own one-year period for a later sale (Rz. 54).

### Example 4: Under Freigrenze

The client's total §23 gain for 2026 is below the private sales limit. The client's total §22 Nr. 3 income for 2026 is below the other income limit.

§23: below the limit, tax-free.
§22 Nr. 3: below the limit, not taxable.
The two limits are tested separately and are never added together. Under the ELSTER instructions for 2025, amounts below the limits need not be entered in Anlage SO. Whether a return is due at all depends on the client's other income (Section 4.3). Losses should still be declared.

## Section 7: Common Mistakes

**Common mistakes table**

| Mistake | Correction |
| --- | --- |
| Applying the flat tax (Abgeltungsteuer) to payment token gains | WRONG. Payment tokens held privately are §23, not §20. The personal rate applies. Only tokens that work like securities can be §20 income (Rz. 81 to 86) |
| Believing only FIFO is allowed, or running one queue across all wallets | Individual identification comes first. The fallback works per wallet and per token (Rz. 61, 62) |
| Ignoring crypto-to-crypto trades | Each swap is a taxable sale and a new purchase, and the one-year period starts again (Rz. 54, 55) |
| Not tracking staking rewards separately | Each reward has its own acquisition date and cost (Rz. 48, 54) |
| Assuming the Haltefrist becomes ten years with staking or lending | WRONG for currency or payment tokens (Rz. 63) |
| Treating Freigrenze as Freibetrag | WRONG. At or above the limit, ALL of it is taxable |
| Adding the two limits together | WRONG. The private sales limit and the other income limit are separate tests |
| Testing the other income limit on gross rewards | WRONG. It tests income after costs (§22 Nr. 3, §2(2) EStG) |
| Treating hard fork coins as new coins with no cost | WRONG. Cost is split and the old purchase date carries over (Rz. 67, 68) |
| Treating every airdrop as income | Only where the client gave a service for it (Rz. 70 to 72) |
| Claiming lost or stolen crypto as a loss | Not supported by the ruling. Refer (5.4) |
| Not reporting because "exchange didn't report" | Does not matter. The duty to declare is the client's (§150(2) AO, Rz. 88). From reporting period 2026 providers report to the BZSt anyway (4.4) |
| Relying on the platform to keep the records | Missing records and lost data count against the client (Rz. 89) |
| Citing the 2022 ruling | It was replaced on 6 March 2025. Cite the 2025 version only. The legacy Guide's paragraph numbers do not match it |

## Section 8: Reference Material

**Reference material table**

| Topic | Reference |
| --- | --- |
| Private sales | §23(1) sentence 1 no. 2 EStG; Rz. 53 to 60 |
| Freigrenze, private sales | §23(3) sentence 5 EStG; older value in Rz. 53. The legacy Guide named the act that raised the limit: not checked, removed |
| Miscellaneous income | §22 Nr. 3 EStG; Rz. 45 to 48a, 65 |
| Commercial income | §15(2) EStG; Rz. 35 to 40 |
| Ministry crypto guidance | Ruling of 6 March 2025, GZ: IV C 1 - S 2256/00042/064/043. Replaced the ruling of 10 May 2022 |
| Order of use | Rz. 61, 62 (legacy cited Rz. 59 to 63 of the old ruling as a "FIFO requirement") |
| No ten-year period | Rz. 63 (legacy cited Rz. 87 of the old ruling) |
| Staking classification | Rz. 13, 48, 48a (legacy cited Rz. 78 to 92 of the old ruling) |
| Hard forks, airdrops | Rz. 67, 68; Rz. 70 to 75 |
| Utility and security tokens | Rz. 77 to 86 |
| Records and cooperation | Rz. 87 to 105; §90, §150, §162 AO |
| Loss offsetting | §23(3) sentences 7 and 8 EStG; §22 Nr. 3 sentences 3 and 4 EStG; §10d EStG |
| Filing obligation | §25(3) EStG; §46 EStG; §56 EStDV; §149 AO |
| Correcting a return | §153 AO |
| Record retention | §147a AO (six years, high-income private persons only). NOT §147 AO |
| Grundfreibetrag 2026 | See the basic allowance table in Section 1 |
| Solidaritätszuschlag | §3, §4 SolzG |
| Platform reporting | KStTG; BZSt procedure page |
| Court ruling | Federal Fiscal Court, judgment of 14 February 2023, IX R 3/22: crypto assets are assets (cited in Rz. 31, 53) |

## The method, step by step

1. Sort each asset by its function: payment token, utility token, security token or NFT (ruling of 6 March 2025, Rz. 3 to 5). NFTs and security tokens leave this Guide. https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2
2. Sort each activity: sale or swap (§23 EStG), passive staking or lending (§22 Nr. 3 EStG), block creation (test the business conditions of §15(2) EStG first). https://www.gesetze-im-internet.de/estg/__15.html
3. For every sale and swap, fix the purchase time and the sale time and test the one-year period of §23(1) sentence 1 no. 2 EStG. https://www.gesetze-im-internet.de/estg/__23.html
4. Decide which units were sold: individual identification, otherwise per wallet and per token the fallback of Rz. 61 and 62 of the ruling. Write the method down. https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2
5. Work out each gain or loss under §23(3) sentence 1 EStG, add up the year per person, and test the total against the private sales limit (§23(3) sentence 5 EStG). https://www.gesetze-im-internet.de/estg/__23.html
6. Work out §22 Nr. 3 income: receipts at market price less costs, all services together, per person, and test the result against the other income limit. https://www.gesetze-im-internet.de/estg/__22.html
7. Handle losses inside their own box: §23 losses against §23 gains, §22 Nr. 3 losses against §22 Nr. 3 income, one year back and forward under §10d EStG. https://www.gesetze-im-internet.de/estg/__10d.html
8. Enter the results in Anlage SO of the income tax return through ELSTER, using the labels of the current year's form. https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025
9. File within the deadline of §149 AO. If an older return turns out to be wrong, §153 AO requires a correction without delay. https://www.gesetze-im-internet.de/ao_1977/__149.html
10. Keep the evidence listed in Rz. 87 to 105 of the ruling, and check whether the retention duty of §147a AO applies. https://www.gesetze-im-internet.de/ao_1977/__147a.html

## Ask the client first

- Is the crypto held privately or in a business? Were you paid wages in crypto?
- For each sale or swap: when was it bought, when was it sold, and in which wallet or on which platform? Were there swaps between tokens?
- What kind of token is it: a payment token such as Bitcoin or Ether, a utility token, a token that works like a security, or an NFT?
- Did you receive rewards (staking, lending, mining, airdrops)? For an airdrop, did you have to do or hand over anything to get it?
- Which platforms and wallets did you use, are any of them foreign or decentralised, and do you have complete transaction exports for every year?
- What other income do you have, do you have wages, and are you assessed jointly with a spouse?

## When to refuse or refer

- NFTs. The ruling does not cover them (Rz. 5).
- Tokens that work like securities, and crypto derivatives, futures, contracts for difference and leveraged trading (Rz. 81 to 86; §20 EStG). See `de-capital-gains`.
- Crypto held in a business, commercial block creation, frequent trading that may be a business (Rz. 35 to 44, 51, 52), and token issuers (Rz. 76).
- Wages or bonuses paid in crypto. The ruling leaves them out.
- Lost, stolen or scammed crypto, and worthless tokens.
- Liquidity pools, yield farming, wrapped tokens, governance rewards, liquidated collateral, stablecoin questions: the ruling gives no rule. The ministry's notice says NFTs and liquidity mining are not yet part of the ruling: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte.html
- Clients who are not tax resident in Germany, moves into or out of Germany, and any case that turns on a tax treaty.
- Gift and inheritance tax beyond the two allowances shown, including how crypto is valued.
- Past years with undeclared crypto income. §153 AO requires a correction, and voluntary disclosure is a matter for a Steuerberater or lawyer.
- Clients with no usable records. The tax office may estimate (§162 AO).
- The exact church tax rate for a client. It is set by state church tax rules, which are not on the federal pages.

## Sources

- EStG §23 (private sales): https://www.gesetze-im-internet.de/estg/__23.html
- EStG §22 (other income): https://www.gesetze-im-internet.de/estg/__22.html
- EStG §2 (what "Einkünfte" means): https://www.gesetze-im-internet.de/estg/__2.html
- EStG §15 (business income): https://www.gesetze-im-internet.de/estg/__15.html
- EStG §20 (investment income) and §32d (flat tax): https://www.gesetze-im-internet.de/estg/__20.html and https://www.gesetze-im-internet.de/estg/__32d.html
- EStG §10d (loss deduction): https://www.gesetze-im-internet.de/estg/__10d.html
- EStG §32a (tariff, basic allowance): https://www.gesetze-im-internet.de/estg/__32a.html
- EStG §25 and §46, EStDV §56 (duty to file): https://www.gesetze-im-internet.de/estg/__25.html and https://www.gesetze-im-internet.de/estg/__46.html and https://www.gesetze-im-internet.de/estdv_1955/__56.html
- SolzG §3 and §4 (solidarity surcharge): https://www.gesetze-im-internet.de/solzg_1995/__3.html and https://www.gesetze-im-internet.de/solzg_1995/__4.html
- AO §90, §147a, §149, §153, §162, §169: https://www.gesetze-im-internet.de/ao_1977/__90.html and https://www.gesetze-im-internet.de/ao_1977/__147a.html and https://www.gesetze-im-internet.de/ao_1977/__149.html and https://www.gesetze-im-internet.de/ao_1977/__153.html and https://www.gesetze-im-internet.de/ao_1977/__162.html and https://www.gesetze-im-internet.de/ao_1977/__169.html
- ErbStG §14 and §16 (gift and inheritance tax): https://www.gesetze-im-internet.de/erbstg_1974/__14.html and https://www.gesetze-im-internet.de/erbstg_1974/__16.html
- Finance ministry ruling on crypto assets, 6 March 2025: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte-bmf-schreiben.pdf?__blob=publicationFile&v=2
- Finance ministry, notice that this ruling replaces the ruling of 10 May 2022: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2025-03-06-einzelfragen-kryptowerte.html
- ELSTER, instructions for the 2025 income tax return (Anlage SO): https://www.elster.de/eportal/helpGlobal?themaGlobal=help_est_ufa_10_2025
- BZSt, crypto reporting procedure under the KStTG: https://www.bzst.de/DE/Unternehmen/Intern_Informationsaustausch/DAC8/Verfahren/verfahren_node.html
- Finance ministry, tax booklet (Steuern von A bis Z), 2025 edition: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9

## Disclaimer

This Guide and its outputs are provided for informational and computational purposes only and do not constitute tax, legal, or financial advice. Open Accountants and its contributors accept no liability for any errors, omissions, or outcomes arising from the use of this Guide. All outputs must be reviewed and signed off by a qualified professional (such as a Steuerberater, Wirtschaftsprüfer, or equivalent licensed practitioner in your jurisdiction) before filing or acting upon.

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
