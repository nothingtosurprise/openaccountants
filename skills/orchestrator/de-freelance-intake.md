---
name: de-freelance-intake
description: ALWAYS USE THIS SKILL when a user asks for help preparing their German tax returns AND mentions freelancing (Freiberufler), self-employment (Selbstständigkeit), trade business (Gewerbetreibender), contracting, or sole proprietorship (Einzelunternehmer). Trigger on phrases like "help me do my German taxes", "prepare my EStE", "I'm self-employed in Germany", "I'm a Freiberufler", "do my Steuererklärung", "prepare my USt and ESt", or any similar phrasing where the user is a Germany-resident self-employed individual needing tax return preparation. This is the REQUIRED entry point for the Germany self-employed tax workflow -- every other skill in the stack (germany-vat-return, de-income-tax, de-social-contributions, de-trade-tax, de-estimated-tax, de-return-assembly) depends on this skill running first to produce a structured intake package. Uses upload-first workflow -- the user dumps all their documents and the skill infers as much as possible before asking questions. Uses ask_user_input_v0 for structured questions instead of one-at-a-time prose. Built for speed. Germany full-year residents only; self-employed individuals and sole proprietors.
version: 0.1
jurisdiction: DE
tax_year: 2026
last_updated: 2026-09-19
review_status: pending_review
drafted_by: OpenAccountants
approved_by: pending
tier: 2
license: AGPL-3.0-or-later (code) / OpenAccountants Guide License v1.0 (content)
---

# German freelancer and sole trader tax intake (Freiberufler and Gewerbetreibende)

The intake an assistant runs before any German tax return work for a self-employed person: the scope questions, the document checklist, what to read out of each document, the gap questions, and the hand-off to the other German Guides. It is for sole proprietors who live in Germany, both Freiberufler (§ 18 EStG) and Gewerbetreibende (§ 15 EStG). This Guide does not compute tax. The few figures it carries are limits that decide a route: which VAT regime, which return rhythm, which expense bucket. Figures are for tax year 2026. They are read from the consolidated federal law pages and from the finance ministry's instructions for the 2026 EÜR form (ministry letter of 1 September 2026). Three figures come from a source dated another year: the reduced VAT rate and the two church tax rates are printed as digits only in the ministry's tax booklet, 2025 edition. If the client is preparing an earlier year, the workflow is the same but some figures differ: see "Tax year first" in Section 1.

## What this file is

The intake orchestrator for self-employed individuals resident in Germany (Freiberufler and Gewerbetreibende). Every downstream German Guide (`germany-vat-return`, `de-einkommensteuer-freelancer`, `de-social-contributions`, `de-trade-tax`, `de-estimated-tax`) and the assembly orchestrator (`de-return-assembly`) depend on this Guide running first to produce a structured intake package. Older versions of this Guide call the income tax step `de-income-tax`.

This Guide does not compute any tax figures. Its job is to collect all the facts, parse all the documents, confirm everything with the user, and hand off a clean intake package to `de-return-assembly`.

## Design principles

v0.1 follows the same upload-first, inference-then-confirm pattern as `mt-freelance-intake` v0.1:

1. **Compact refusal sweep** using `ask_user_input_v0`: 3 to 5 interactive questions, about 30 seconds.
2. **Upload-first workflow**: after the refusal check, the user dumps everything they have.
3. **Inference pass**: the assistant parses every document and extracts as much as possible.
4. **Gap-filling only**: the assistant asks the user ONLY about what is missing, ambiguous, or needs confirmation.
5. **Single confirmation pass** at the end: show the full picture, let the user correct anything wrong, hand off to the downstream Guides.

Target: intake completes in 5 minutes for a prepared user, 15 minutes for a user who has to go fetch documents.

## Critical operating principles

**Do not narrate the workflow.** Do not say "Phase 1," "Phase 2," "Now I'll ask you about deductions." Just do the work.

**Do not ask questions that have already been answered.** If the refusal check established the user is Regelbesteuert, do not later ask about VAT status. Track what is known.

**Do not ask about things visible in uploaded documents.** If the bank statement shows quarterly Vorauszahlungen to the Finanzamt, do not ask "did you pay estimated tax." Confirm what you see, do not re-ask.

**Use `ask_user_input_v0` for any multiple-choice question.** Text input is only for genuinely open-ended data (names, addresses, specific amounts when they cannot be inferred). If the assistant has no such tool, ask the same questions as one short numbered list in a single message.

**Prefer batching.** Ask 3 related questions in a single message when they do not depend on each other's answers.

**Be terse but complete.** No hedging, no "let me know if you have questions," no "I hope this helps."

**Exception for blocking decisions.** If a single question determines whether the user is in-scope or out-of-scope, ask it standalone.

**Do not decide what only the tax office can decide.** Whether an activity is freelance or commercial, and whether a room at home is the centre of all the work, are recorded as the client states them and flagged for the reviewer. See Section 2 and Section 6.

## Section 1: The opening

When triggered, respond with ONE message that:

1. One-line greeting (no paragraph of expectation-setting)
2. One-line summary of the flow (scope check -> upload -> gaps -> handoff to return assembly)
3. One-line reviewer reminder (must be reviewed by Steuerberater before filing)
4. Launch the refusal sweep immediately using `ask_user_input_v0`

**Example first message:**

> Let's get your [tax year] German returns ready. Quick scope check, then you upload your documents, then I fill in the gaps. Target time: 10 minutes.
>
> Reminder: everything I produce needs to be reviewed and signed off by a Steuerberater before you file anything with the Finanzamt. I'm not a substitute for professional review.
>
> Scope check:

Then immediately call `ask_user_input_v0` with the refusal questions.

**Do NOT:**
- Write a welcome paragraph
- Explain the phases
- Ask "are you ready to start"
- List what documents you will eventually need
- Give a disclaimer beyond the one reviewer line

**Tax year first.** If the user has not named the year, ask for it inside the scope check. The figures in this Guide are for 2026. For an earlier year, check each figure against the law as it stood in that year before relying on it. One difference is on a ministry page: the single commuting rate from the first kilometre started on 1 January 2026, and before that date this rate applied only from the 21st kilometre. https://www.bundesfinanzministerium.de/Content/DE/Standardartikel/Themen/Steuern/das-aendert-sich-2026.html

## Section 2: Refusal sweep (compact)

Present the refusal sweep as a single `ask_user_input_v0` call with 3 questions, all single-select.

**The 3 questions to ask first:**

~~~
Q1: "Germany residency in [tax year]?"
    Options: ["Full year (home or habitual abode in Germany all year: unbeschränkt steuerpflichtig)", "Part year", "Did not live in Germany"]

Q2: "Business structure?"
    Options: ["Freiberufler (§ 18 EStG, liberal profession)", "Gewerbetreibender (§ 15 EStG, trade or business)", "GbR / Partnership", "GmbH / UG / Kapitalgesellschaft", "Not sure"]

Q3: "VAT status?"
    Options: ["Regelbesteuerung (standard VAT: charge and reclaim USt)", "Kleinunternehmer § 19 UStG (sales are VAT-exempt, turnover within both limits)", "Not sure"]
~~~

- **Q1 evaluation.** Q1 = Full year -> continue. Q1 = Part year or did not live in Germany -> stop. "I'm set up for full-year German residents (unbeschränkt steuerpflichtig) only. Part-year or non-residents have different rules around beschränkte Steuerpflicht. You need a Steuerberater who handles non-resident returns." The legal test for full liability is a home (Wohnsitz) or habitual abode (gewöhnlicher Aufenthalt) in Germany: § 1(1) EStG at https://www.gesetze-im-internet.de/estg/__1.html
- **Q2 evaluation.** Q2 = Freiberufler -> continue. No Gewerbesteuer applies if the tax office accepts that classification. Record the profession the client names and test it against the list in "Freiberufler or Gewerbetreibender" below. Q2 = Gewerbetreibender -> continue with a flag: Gewerbesteuer applies, will need the Hebesatz of the municipality. Q2 = GbR / Partnership -> stop. "Partnerships file a separate Feststellungserklärung with different rules for profit allocation. You need a Steuerberater familiar with partnership returns." Q2 = GmbH / UG / Kapitalgesellschaft -> stop. "I don't cover corporate returns. Kapitalgesellschaften file KStE and GewStE with separate rules. You need a Steuerberater." Q2 = Not sure -> ask one follow-up: "What exactly do you do, what training is it based on, and are you registered with the trade office (Gewerbeamt)?" Then apply the test below. If it still does not settle the point, record the business type as unsettled in `open_flags` and continue: the tax office decides, not the assistant.
- **Q3 evaluation.** Q3 = Regelbesteuerung -> continue. UStVA monthly or quarterly: see the VAT return rhythm table below. Q3 = Kleinunternehmer -> continue. No UStVA and no yearly VAT return as a rule, with the two exceptions listed under the small-business tables below. Both turnover limits in the table must be kept. Q3 = Not sure -> ask one follow-up: "Do you charge 19% (or 7%) USt on your invoices? If yes, you're Regelbesteuert. If your invoices carry a note that the Kleinunternehmer exemption of § 19 UStG applies, you're Kleinunternehmer." An invoice with no VAT on it does not prove Kleinunternehmer status by itself: a service to a business customer abroad, or an exempt activity such as medical treatment, also shows no German VAT. If the follow-up does not settle it, record `vat_status` as `unsettled`, ask for both turnover figures (Section 6, question 11) and flag it.

### Freiberufler or Gewerbetreibender: the legal test

This is the first fork of every German intake. It decides trade tax, the bookkeeping duty and the form (Anlage S or Anlage G).

- **What § 18 EStG names.** Freelance work is, first, self-employed scientific, artistic, literary, teaching or educational work ("wissenschaftliche, künstlerische, schriftstellerische, unterrichtende oder erzieherische Tätigkeit"). Second, the self-employed work of: Ärzte, Zahnärzte, Tierärzte, Rechtsanwälte, Notare, Patentanwälte, Vermessungsingenieure, Ingenieure, Architekten, Handelschemiker, Wirtschaftsprüfer, Steuerberater, beratende Volks- und Betriebswirte, vereidigte Buchprüfer, Steuerbevollmächtigte, Heilpraktiker, Dentisten, Krankengymnasten, Journalisten, Bildberichterstatter, Dolmetscher, Übersetzer, Lotsen "und ähnlicher Berufe" (and similar professions). In English: doctors, dentists, vets, lawyers, notaries, patent attorneys, surveying engineers, engineers, architects, commercial chemists, auditors, tax advisers, consulting economists and business economists, sworn auditors, tax agents, non-medical practitioners (Heilpraktiker), dental practitioners (Dentisten), physiotherapists, journalists, photo reporters, interpreters, translators, maritime pilots (Lotsen). See § 18(1) no. 1 EStG at https://www.gesetze-im-internet.de/estg/__18.html
- **What § 18 EStG does not name.** Software developers, IT consultants, web designers and marketing agencies are not in the list. "Consultant" alone is not in it either: the list names only consulting economists and business economists (beratende Volks- und Betriebswirte). Such a client is a Freiberufler only if the work is one of the five activity types, or a profession similar to a named one. The economics ministry's start-up portal (not a tax administration text) says that for a similar profession the training and the actual work must be comparable to a named profession, and that the five activity types can be classified only case by case ("nur nach Einzelfallprüfung"). Do not tell such a client that they are a Freiberufler, and do not tell them that they are a Gewerbetreibender either. Not being named does not make the work commercial: the portal says a number of professions similar to the named ones also count as liberal professions ("Zu den Freien Berufen zählt auch eine Reihe von Berufen, die den Katalogberufen ähnlich sind"), and an expert article on the same portal gives a computer scientist and a graphic designer as examples of freelancers who add a commercial side activity ("Eine Informatikerin testet Programme von anderen Entwicklern", "Ein Grafiker vergibt neben seiner freiberuflichen Tätigkeit auch Druckaufträge"). Record what they do, the training it rests on, how they are registered and how they have filed and been assessed so far (line 8 of the prior EÜR, Anlage S or Anlage G in the prior return), and flag it. https://www.existenzgruendungsportal.de/gruenden-kurz-und-knapp/freie-berufe and https://www.existenzgruendungsportal.de/SharedDocs/Expertenforum_Unterseiten/Freie-Berufe/Gemischte-Taetigkeiten/Gemischte-Taetigkeiten
- **What the law calls a Gewerbebetrieb.** A self-employed, lasting activity, carried on to make a profit and offered on the general market, is a Gewerbebetrieb unless it is farming, a liberal profession or other self-employed work: § 15(2) EStG at https://www.gesetze-im-internet.de/estg/__15.html The ministry's 2026 EÜR instructions say the same for line 8 of the form: income from self-employed work exists only if § 18(1) EStG is met ("liegen nur vor, wenn die Voraussetzungen des § 18"), and in all other cases of profit income "handelt es sich um Einkünfte aus Gewerbebetrieb". https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2
- **Who decides.** The tax office, not the client and not the assistant. The start-up portal: "Die Entscheidung, ob Ihre Tätigkeit freiberuflich oder gewerblich ist, trifft bei Ihrer Anmeldung im Zweifelsfall das Finanzamt, in einigen Fällen auch das Gewerbeamt." A first treatment as Freiberufler is not final. The portal says the final decision often comes later, in a tax audit (Betriebsprüfung), and that trade tax may then have to be paid for past years. It names a binding ruling from the tax office (verbindliche Auskunft, for a fee) as a way to settle doubt. https://www.existenzgruendungsportal.de/gruenden-kurz-und-knapp/freie-berufe
- **The trade registration.** The opening of a commercial business is reported to the municipality, which informs the tax office. The start of freelance work is reported to the tax office itself (§ 138(1) AO at https://www.gesetze-im-internet.de/ao_1977/__138.html). ELSTER names the municipal office: "Sie haben Ihr Gewerbe beim Gewerbeamt angemeldet" (https://www.elster.de/elsterweb/infoseite/unternehmensgruendung). The start-up portal says freelancers need no Gewerbeschein. Older versions of this Guide said the Finanzamt issues the Gewerbeschein: it does not. A trade registration is a strong sign of a Gewerbebetrieb, but it is not the tax decision: see "Who decides".
- **Staff.** A Freiberufler may use trained staff only while he or she still leads the work and is personally responsible for it on the strength of his or her own expertise (§ 18(1) no. 1 sentence 3 EStG). If the client has employees (Q4), flag this.
- **Mixed activities, sole proprietor.** The start-up portal: if a freelance and a commercial activity can be separated (an architect who also brokers property, an eye doctor who also sells contact lenses), the tax office treats them separately and often asks for separate records and separate profit figures, in Anlage S and Anlage G. If they cannot be separated, the tax office decides by which part shapes the whole, and the result can be that it treats all of the work as a Gewerbebetrieb. Ask about every side activity: sales of goods, commissions, brokerage, print or other bought-in work resold in the client's own name. Sources: https://www.existenzgruendungsportal.de/gruenden-kurz-und-knapp/freie-berufe and https://www.existenzgruendungsportal.de/SharedDocs/Expertenforum_Unterseiten/Freie-Berufe/Gemischte-Taetigkeiten/Gemischte-Taetigkeiten
- **Mixed activities, partnership.** The statute's own taint rule is written for partnerships: a partnership that also carries on a commercial activity counts as a Gewerbebetrieb in full (§ 15(3) no. 1 EStG). This Guide refuses partnerships, so the rule matters here only for Q5.
- **What follows from the answer.** Freiberufler: no trade tax, profit in Anlage S, no size-based bookkeeping duty (Section 6). Gewerbetreibender: trade tax applies to every Gewerbebetrieb run in Germany (§ 2(1) GewStG at https://www.gesetze-im-internet.de/gewstg/__2.html), profit in Anlage G, and the bookkeeping duty of § 141 AO can arise.

**Trade tax: allowance for natural persons and partnerships**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/gewstg/__11.html |
| Allowance taken off the trade income of a natural person or a partnership, per business per year | EUR 24,500 | § 11(1) GewStG: "um einen Freibetrag in Höhe von 24 500 Euro" |

- **An allowance, not a cliff.** Only trade income above it is taxed. Corporations do not get it. The computation belongs to `de-trade-tax`.

### Kleinunternehmer or Regelbesteuerung: the legal test

**Small-business VAT limits: the statute**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ustg_1980/__19.html |
| Total turnover (Gesamtumsatz) of the previous calendar year: must not have exceeded | EUR 25,000 | § 19(1) UStG: "im vorangegangenen Kalenderjahr 25 000 Euro nicht überschritten hat" |
| Total turnover of the current calendar year: must not exceed | EUR 100,000 | § 19(1) UStG: "im laufenden Kalenderjahr 100 000 Euro nicht überschreitet" |

**Small-business VAT limits: the ministry's 2026 EÜR instructions**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2 |
| Business that starts during the year: total turnover of the current calendar year must not exceed | EUR 25,000 | EÜR instructions 2026, line 12: "darf der Gesamtumsatz im laufenden Kj. 25.000 € nicht überschreiten" |

- **Both tests must be met.** The law joins the previous year and the current year with "und". A turnover exactly at a limit is still inside it: the law says "nicht überschritten" and "nicht überschreitet".
- **The current-year limit is a hard stop, not a forecast.** The EÜR instructions say that the very receipt "mit dem Sie die jeweilige Grenze im laufenden Kj. überschreiten, unterliegt der Regelbesteuerung". Receipts before that point stay exempt: "Die bis zum Zeitpunkt der Überschreitung vereinnahmten Umsätze sind steuerfrei". If the bank statement shows the client near or over a limit, flag it and route to `germany-vat-return`.
- **What counts.** Gesamtumsatz is the sum, worked out on payments received, of the sales that are taxable in Germany under § 1(1) no. 1 UStG ("Summe der vom Unternehmer ausgeführten steuerbaren Umsätze im Sinne des § 1 Absatz 1 Nummer 1"). That provision covers supplies made "im Inland". Certain exempt sales are left out, and sales of fixed assets are left out (§ 19(2) UStG). Read together, a service whose place of supply is abroad under § 3a(2) UStG does not count. That last step is a reading of two statute texts, not one printed sentence: ask for the German and the foreign turnover separately and flag a client who is over a limit only because of foreign sales. https://www.gesetze-im-internet.de/ustg_1980/__1.html
- **Waiver.** The client may waive the rule by a declaration to the tax office. The declaration is irrevocable and can be made until the last day of February of the second calendar year after the tax period. It binds for at least five calendar years. After that it can be withdrawn only from the start of a later calendar year (§ 19(3) UStG). Ask whether the client ever waived.
- **Invoices.** A Kleinunternehmer may not charge VAT separately on an invoice (2026 EÜR instructions, line 12: "keine Umsatzsteuer gesondert in Rechnung stellen"). Whoever shows VAT on an invoice without being entitled to owes that amount (§ 14c UStG at https://www.gesetze-im-internet.de/ustg_1980/__14c.html). The invoice states the price in one sum and must carry a note that the Kleinunternehmer exemption applies: § 34a UStDV at https://www.gesetze-im-internet.de/ustdv_1980/__34a.html
- **Returns.** For a Kleinunternehmer the duties of § 18(1) to (4) UStG do not apply, so there are no advance returns and no yearly VAT return. Two exceptions stay in force (§ 19(1) sentence 2 UStG): the tax office may still ask for a return, and § 18(4a) UStG still applies. § 18(4a) UStG makes a business that owes only VAT on goods bought from other EU states (§ 1(1) no. 5), VAT as the recipient of a supply (§ 13b(5)) or VAT under § 25b(2) file advance returns and a yearly VAT return. The advance returns are due only for the periods in which that VAT arises ("Voranmeldungen sind nur für die Voranmeldungszeiträume abzugeben, in denen die Steuer für diese Umsätze zu erklären ist"). The common case is a Kleinunternehmer who buys a service from a business abroad and owes the German VAT on it as the recipient (§ 13b(5) UStG at https://www.gesetze-im-internet.de/ustg_1980/__13b.html). Look for foreign software, advertising and platform charges on the bank statement.
- **Input VAT.** Input VAT on purchases used for tax-free sales cannot be deducted (§ 15(2) no. 1 UStG at https://www.gesetze-im-internet.de/ustg_1980/__15.html), and § 19(1) UStG makes the Kleinunternehmer's sales tax-free. Record a Kleinunternehmer's purchase invoices at the gross amount.

**VAT rates on invoices: the statute**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ustg_1980/__12.html |
| Standard rate | 19% | § 12(1) UStG: "Die Steuer beträgt für jeden steuerpflichtigen Umsatz 19 Prozent der Bemessungsgrundlage" |

**VAT rates on invoices: the ministry's tax booklet, 2025 edition**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Reduced rate, only for the supplies listed in § 12(2) UStG and its annex | 7% | Tax booklet, 2025 edition: "den ermäßigten von 7 Prozent". The statute prints this rate in words ("sieben Prozent") |

**VAT return rhythm for a Regelbesteuert client**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ustg_1980/__18.html |
| VAT for the previous calendar year above which the return period is the month, not the quarter | EUR 9,000 | § 18(2) UStG: "für das vorangegangene Kalenderjahr mehr als 9 000 Euro" |
| VAT for the previous calendar year up to which the tax office may release the business from advance returns | EUR 2,000 | § 18(2) UStG: "für das vorangegangene Kalenderjahr nicht mehr als 2 000 Euro" |

- **The test is last year's VAT, not turnover.** The default period is the calendar quarter. The return and the payment are due by the tenth day after the period ends (§ 18(1) UStG).
- **The release is the tax office's choice.** It is not automatic, and the yearly VAT return is still due.
- **New businesses, tax periods 2021 to 2026.** A business that starts in the current year uses the expected VAT of that year. A business that ran for only part of the previous year scales that year's VAT up to a full year. Outside those tax periods the basic rule applies: monthly returns in the year of start and in the year after (§ 18(2) UStG).
- **Dauerfristverlängerung.** On application the tax office extends the deadlines for advance returns and payments by one month (§ 46 UStDV). A monthly filer gets it only against a special prepayment of one eleventh of the previous year's prepayments (§ 47 UStDV at https://www.gesetze-im-internet.de/ustdv_1980/__47.html). A quarterly filer pays no special prepayment.

**After Q1 to Q3 pass, ask the second batch of scope questions (also batched):**

~~~
Q4: "Employees?"
    Options: ["No employees", "1 to 5 employees", "More than 5 employees"]

Q5: "Partnerships or joint ventures?"
    Options: ["None: I operate alone", "I'm a partner in a GbR or other partnership alongside this business", "Not sure"]
~~~

- **Q4 evaluation.** No employees -> continue. 1 to 5 employees -> continue with a flag: Lohnsteuer obligations exist but are out of scope for this workflow. Flag for Steuerberater review. Payroll itself is covered by `de-payroll` and `germany-payroll`. For a Freiberufler also flag the staff rule in the test above. More than 5 -> stop. "I'm set up for sole operators and very small businesses. With more than 5 employees, the payroll and Lohnsteuer complexity requires a dedicated Steuerberater." The limit of 5 is this Guide's own scope line, not a legal threshold.
- **Q5 evaluation.** None -> continue. Partner in a GbR -> continue with a flag: income in which several persons share is determined separately (§ 180(1) no. 2 a AO at https://www.gesetze-im-internet.de/ao_1977/__180.html), so the client's share will appear in a Feststellungsbescheid and needs to be entered in Anlage S or Anlage G. Will address during gap-filling. Not sure -> ask one follow-up: "Do you share business income with another person or file a joint business return (Feststellungserklärung)? If not, you operate alone."

**Total time:** about 45 seconds if the user taps through.

## Section 3: The dump

Once the refusal sweep passes, immediately ask for the document dump. Single message. No preamble.

**Example:**

> Scope is good. Now upload everything you have for [tax year]. Drop it all in at once:
>
> - Business Kontoauszüge (bank statements) for all of [tax year] (CSV or PDF)
> - Ausgangsrechnungen (sales invoices) issued in [tax year]
> - Eingangsrechnungen (purchase invoices / receipts) for business expenses
> - Prior year Steuerbescheid (tax assessment notice from the Finanzamt)
> - Vorauszahlungsbescheide (estimated tax payment notices)
> - Prior UStVA filings for [tax year] (if Regelbesteuert), and any letter about your return period or a Dauerfristverlängerung
> - EÜR from prior year (Anlage EÜR)
> - Krankenversicherung (health insurance) annual statement (Beitragsbescheinigung)
> - Any Finanzamt correspondence, including any notice to start keeping books
> - Fragebogen zur steuerlichen Erfassung and Gewerbeanmeldung, if the business is new or you have them to hand
> - Rentenversicherung or Künstlersozialkasse notices, if any
> - Capital asset purchase receipts (computers, equipment, vehicles)
> - Anything else tax-related you have
>
> Don't worry about labeling or organizing. I'll figure out what each file is. Drag and drop when ready.

Then wait. Do not ask any other questions while waiting.

**If the user uploads a partial dump and says "that's what I have":** move to inference. Do not demand more. Request specific missing items during gap-filling.

**If the user says "I don't know what I have":** Switch to guided mode:
> Check these places:
> - Business bank: download [tax year] statements as PDF or CSV
> - Email: search for "Rechnung", "Steuerbescheid", "Vorauszahlung", "Finanzamt", "Krankenkasse"
> - ELSTER portal (elster.de): download prior returns and Steuerbescheide
> - Your Steuerberater from last year, if you had one
> - Dropbox / Google Drive for saved invoices
> - Krankenkasse portal: download Beitragsbescheinigung
>
> Come back when you have something to upload. I'll work with whatever you bring.

## Section 4: The inference pass

When documents arrive, parse each one. For each document, extract:

- **Bank statement (Kontoauszüge) extraction items.** Total deposits (candidate Betriebseinnahmen); Recurring inflows (customer payments with names); Outflows to Finanzamt (Vorauszahlungen ESt/SolZ/KiSt with dates); Outflows to Finanzamt (USt-Vorauszahlungen with dates); Outflows to Krankenkasse GKV or PKV (health insurance premiums); Outflows to Rentenversicherung (if voluntary or Pflichtversichert, also via Künstlersozialkasse); Equipment purchases (potential Anlagevermögen); Transfers to personal account (Privatentnahmen); Office rent payments (Büromiete); SaaS / software subscriptions, and whether the supplier is abroad; Professional memberships (IHK Beiträge, Berufsverband); Insurance payments (Berufshaftpflicht, Kfz); Telefon / Internet payments; Kfz expenses (fuel, maintenance, leasing); One customer that makes up nearly all the inflows (see the pension question in Section 6)
- **Sales invoices (Ausgangsrechnungen) extraction items.** Customer names and amounts (netto + USt); Whether USt was charged (Regelbesteuerung indicator); Whether invoices carry the Kleinunternehmer note of § 19 UStG (Kleinunternehmer indicator); Total Umsatz reconciliation against bank deposits; Any business customers in another EU state (as a rule a service to a business is supplied where that business is run, § 3a(2) UStG, with exceptions in § 3a(3) to (8); where the customer owes the VAT there, the sale goes into the quarterly Zusammenfassende Meldung, § 18a(2) UStG; a Kleinunternehmer files none, § 18a(4) UStG); Any non-EU customers (Drittlandsleistung, § 3a UStG); Proper invoice format check (§ 14 UStG requirements). Sources: https://www.gesetze-im-internet.de/ustg_1980/__3a.html and https://www.gesetze-im-internet.de/ustg_1980/__18a.html
- **E-invoices.** For a supply to another business, where supplier and customer are both established in Germany, the invoice must be an e-invoice, issued within six months. Sales exempt under § 4 nos. 8 to 29 UStG are outside that duty (§ 14(1) and (2) UStG at https://www.gesetze-im-internet.de/ustg_1980/__14.html). A Kleinunternehmer's invoice may always be an ordinary invoice (§ 34a UStDV). Where the e-invoice duty applies, the issuer needs no consent from the recipient (§ 14(1) UStG: consent is needed only "soweit keine Verpflichtung nach Absatz 2 Satz 2 Nummer 1 besteht"), so ask every client, a Kleinunternehmer included, whether they can receive e-invoices. Transition rules let issuers keep sending paper, or with the recipient's consent another electronic format, until 31 December 2026 for sales made in 2025 and 2026, and for sales made in 2027 only if the issuer's total turnover of the previous calendar year was not above a limit (§ 27(38) UStG at https://www.gesetze-im-internet.de/ustg_1980/__27.html). Note which format the client sends and route to `germany-einvoice`.
- **Purchase invoices (Eingangsrechnungen) extraction items.** Expense category (Betriebsausgaben, Anlagevermögen, durchlaufende Posten); Vorsteuer amount on each (reclaimable for Regelbesteuert, cost for Kleinunternehmer); Supplier location (inland, EU, Drittland); Any single asset above the GWG limit or inside the pool range (asset table below); Any restricted categories (Bewirtungskosten, Geschenke: limits table below)
- **Prior year Steuerbescheid extraction items.** Prior year festgesetzte Einkommensteuer (drives Vorauszahlungen); Prior year Solidaritätszuschlag; Prior year Kirchensteuer (if applicable; it also shows the client's church tax rate); Any Nachzahlung or Erstattung; Vorauszahlungen festgesetzt for current year
- **Vorauszahlungsbescheide quarterly dates.** Quarterly ESt Vorauszahlungen (10 March, 10 June, 10 September, 10 December: § 37(1) EStG); SolZ amounts; KiSt amounts (if applicable). See the prepayment table below
- **Prior EÜR (Anlage EÜR) extraction items.** Prior year Betriebseinnahmen and Betriebsausgaben; Prior year Gewinn; Capital allowances schedule (Anlage AVEÜR: continuing depreciation); Any Sonderabschreibung or Investitionsabzugsbetrag under § 7g EStG used; Whether the prior EÜR was filed as selbständige Arbeit or as Gewerbebetrieb (line 8 of the form)
- **Krankenversicherung Beitragsbescheinigung extraction items.** Annual GKV or PKV premiums paid; For GKV: the contributions set under SGB V, and whether they can carry a sick pay claim (Krankengeld); For PKV: only the share of the premium that pays for benefits comparable to statutory cover, without the sick pay part (Basisabsicherung). Take it from the insurer's statement and do not estimate it; Pflegeversicherung amount. Legal basis: § 10(1) no. 3 EStG at https://www.gesetze-im-internet.de/estg/__10.html
- **Health insurance: what counts as basic cover in a statutory fund.** § 10(1) no. 3 EStG treats as basic cover the contributions set under the third title of the first section of chapter eight of SGB V. The table of contents of SGB V places the fund's additional contribution (§ 242, Zusatzbeitrag) in that title: https://www.gesetze-im-internet.de/sgb_5/ So do not split a statutory fund's additional contribution off as something outside basic cover, as older versions of this Guide did. Where the contributions can carry a sick pay claim, the law cuts them by a fixed share: record the claim, yes or no.

**Fixed assets: limits used when sorting purchase invoices**

| Cost of the single asset, less the input VAT it contains | Treatment | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__6.html |
| Not more than EUR 800 | May be expensed in full in the year of purchase (a choice, per asset). This is the GWG limit | § 6(2) EStG: "für das einzelne Wirtschaftsgut 800 Euro nicht übersteigen" |
| More than EUR 250, if expensed at once | Must be entered in a special running register, unless the records already show the data | § 6(2) EStG: "deren Wert 250 Euro übersteigt" |
| More than EUR 250 and not more than EUR 1,000 | Alternative for the whole year: one pool (Sammelposten), released over five years | § 6(2a) EStG: "für das einzelne Wirtschaftsgut 250 Euro, aber nicht 1 000 Euro übersteigen" |

- **Which assets.** Movable, depreciable fixed assets that can be used on their own. The limits are measured net of the input VAT contained in the cost. The official pages read for this Guide do not say how a Kleinunternehmer measures them, so flag such a case.
- **The pool is a choice for the whole year.** If it is chosen, it covers every asset of that year in the pool range, and only assets up to the lower pool bound may still be expensed at once.
- **EÜR filers follow the same rules** (§ 4(3) EStG).
- **Computers and software.** The ministry accepts a useful life of one year for computer hardware, with its peripherals, and for operating and application software, so the cost can be deducted in full in the year of purchase. The asset must still be listed in Anlage AVEÜR. The 2026 EÜR instructions: "kann eine betriebsgewöhnliche Nutzungsdauer von einem Jahr" be assumed. Older versions of this Guide spread a laptop over three years without naming this option. https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2

**Restricted expenses: limits used when sorting purchase invoices**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__4.html |
| Gifts to people who are not the client's employees: deductible only if the cost of everything given to one recipient in the business year is not more than | EUR 50 | § 4(5) no. 1 EStG: "insgesamt 50 Euro nicht übersteigen" |
| Business entertainment: share of the reasonable and documented cost that may be deducted | 70% | § 4(5) no. 2 EStG: "soweit sie 70 Prozent der Aufwendungen übersteigen" |

- **Gifts: a cliff, per recipient, per year.** Above the limit the whole cost for that recipient is lost, not just the excess.
- **Entertainment needs proof.** Written details of place, date, participants, occasion and amount. For a restaurant, the bill must be attached.
- **Separate records.** Gifts, entertainment and the home office room must be recorded one by one and apart from other expenses, or the deduction is lost (§ 4(7) EStG). Collect them in `limited_deduction`.

**Income tax prepayments: when the tax office sets them**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__37.html |
| Prepayments are set only if they come to at least, per calendar year | EUR 400 | § 37(5) EStG: "mindestens 400 Euro im Kalenderjahr" |
| and at least, per due date | EUR 100 | § 37(5) EStG: "mindestens 100 Euro für einen Vorauszahlungszeitpunkt betragen" |

- **Both minimums must be met.** The law joins them with "und".
- **Set by notice.** The tax office sets prepayments by Vorauszahlungsbescheid, as a rule from the tax of the last assessment, and may adjust them until the end of the fifteenth month after the tax year (§ 37(3) EStG). Prepayments are due only once the tax office has set them, so a client with no notice has not missed one. The schedule belongs to `de-estimated-tax`.

After parsing everything, build an internal inference object. Do not show the raw inference yet. Transform it into a compact summary for the user in Section 5.

## Section 5: The confirmation

After inference, present a single compact summary message. Use a structured format that is fast to scan. Invite the user to correct anything wrong. The example shows the shape only: every [amount] is a value read from the client's own documents.

**Example summary message:**

> Here's what I pulled from your documents. Skim and tell me what's wrong.
>
> **Identity**
> - Max Mustermann, single
> - Full-year Germany resident (Berlin)
> - Freiberufler (Übersetzer, a profession named in § 18 EStG), sole proprietor
> - VAT: Regelbesteuerung (USt-IdNr. DE123456789)
>
> **Umsatz (from bank statement + invoices)**
> - Betriebseinnahmen (netto): about [amount]
>   - TechCorp GmbH: [amount] (monthly retainer)
>   - StartupAG: [amount] (project work)
>   - Various smaller clients: [amount]
> - USt collected (19%): about [amount]
> - Business clients in other EU states: [amount] (client owes the VAT there, goes into the Zusammenfassende Meldung)
>
> **Betriebsausgaben (from bank statement + purchase invoices)**
> - Büromiete: [amount]
> - Software / SaaS: [amount] (of which from suppliers abroad: [amount])
> - Berufshaftpflicht: [amount]
> - Steuerberater Vorjahr: [amount]
> - Telefon / Internet: [amount] (open: business use share)
> - Kfz: [amount] fuel + [amount] maintenance (open: business use share or Fahrtenbuch)
> - MacBook Pro [amount] netto (April): above the GWG limit. Computer hardware, so a one-year useful life is accepted
> - Vorsteuer auf Eingangsrechnungen: about [amount] (reclaimable)
>
> **Sozialversicherung (from Beitragsbescheinigung / bank statement)**
> - GKV (TK): [amount] per year, with sick pay claim: open
> - Pflegeversicherung: [amount] per year
> - Rentenversicherung: not detected (freiwillig, or a duty not yet registered?)
>
> **Vorauszahlungen (from Vorauszahlungsbescheid / bank statement)**
> - ESt Vorauszahlungen: [amount] on each of the four due dates
> - SolZ: none set
> - KiSt: not detected
>
> **Prior year (from the prior year Steuerbescheid)**
> - Festgesetzte ESt: [amount]
> - Gewinn aus selbständiger Arbeit: [amount]
> - Anlage AVEÜR: [amount] continuing depreciation
>
> **USt (from prior UStVA filings)**
> - January to November UStVA filed (monthly filer)
> - December UStVA outstanding
> - Dauerfristverlängerung: yes (special prepayment of one eleventh paid)
>
> **Flags I already see:**
> 1. Telefon / Internet: need business use share
> 2. Kfz: need the method (1%-Regelung or Fahrtenbuch) and the business use share
> 3. MacBook Pro: above the GWG limit, one-year useful life for computer hardware, list in Anlage AVEÜR
> 4. December UStVA not yet filed: will prepare as part of this workflow
> 5. No Rentenversicherung detected, and one client makes up most of the income: pension duty to be checked
> 6. Kirchensteuer status unclear
>
> **Is any of this wrong? Reply "looks good" or tell me what to fix.**

## Section 6: Gap filling

After the user confirms the summary (or corrects it), ask about things that cannot be inferred from documents. Use `ask_user_input_v0` where possible.

**Things that usually cannot be inferred:**

1. **Arbeitszimmer (home office).** Cannot tell from documents whether a room at home is used and whether it is the centre of all the work. See the home office table below.
2. **Private use percentage.** Telefon, Internet, Kfz business-use split.
3. **Kfz method.** 1%-Regelung vs Fahrtenbuch, and whether the car is used mostly for the business.
4. **Capital allowances from prior years.** Continuing AfA on assets acquired before the tax year (unless the prior EÜR has the schedule).
5. **GKV or PKV.** Whether gesetzlich or privat krankenversichert (affects the Sonderausgaben computation).
6. **Kirchensteuer.** Whether the user pays KiSt. See the church tax table below.
7. **Bundesland.** Needed for the Kirchensteuersatz and, with the municipality, for the Gewerbesteuer Hebesatz (if Gewerbetreibender).
8. **Other income.** Employment income (Anlage N), rental (Anlage V, `de-rental-income`), Kapitalerträge (Anlage KAP, `de-capital-gains`), crypto (`de-crypto-tax`).
9. **Pension insurance duty.** Some self-employed people are compulsorily insured in the statutory pension scheme. See "Pension duty" below.
10. **Profit method.** EÜR or balance sheet, and whether the tax office has sent a notice to start keeping books. See "EÜR or balance sheet" below.
11. **Turnover for the Kleinunternehmer test.** Gesamtumsatz of the previous calendar year and of the current year so far, if the documents do not show both.

**Home office: the statute**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__4.html |
| Room at home that is the centre of all business and professional work: yearly flat amount that may be taken in place of the actual costs | EUR 1,260 | § 4(5) no. 6b EStG: "pauschal ein Betrag von 1 260 Euro (Jahrespauschale)" |
| Daily flat amount for each calendar day on which the work is done mainly at home and no first place of work outside the home is visited | EUR 6 | § 4(5) no. 6c EStG: "ein Betrag von 6 Euro (Tagespauschale)" |
| Yearly cap on the daily flat amounts | EUR 1,260 | § 4(5) no. 6c EStG: "höchstens 1 260 Euro im Wirtschafts- oder Kalenderjahr" |

- **The room test.** The costs of a room at home and its furnishing are not deductible at all unless the room is the centre of the whole business and professional activity ("Mittelpunkt der gesamten betrieblichen und beruflichen Betätigung"). A separate room is not enough. The statute does not define the centre, so do not decide it for the client.
- **If the room is the centre.** The client takes the actual costs or the yearly flat amount. The flat amount falls by one twelfth for each full month in which the room is not the centre.
- **The daily flat amount needs no separate room.** It covers the whole business and professional activity (one amount per day, not one per job). If no other workplace is permanently available, it is also allowed on days with work away from home. It cannot be taken so far as the room deduction is taken, or for a home whose costs are deducted as a second household.
- **Same number, two rules.** The yearly flat amount for the room and the cap on the daily amounts are the same figure. They are different rules.

Call `ask_user_input_v0` with:

~~~
Q: "Arbeitszimmer (home office)?"
   Options: [
     "Room at home that is the centre of all my business and professional work (Mittelpunkt)",
     "Room at home, and I also do a large part of my work elsewhere (client sites, another office)",
     "No separate room: I work at home on some days (Tagespauschale)",
     "Separate business premises (Büromiete already captured)",
     "No home office claim"
   ]
~~~

If option 1 -> actual costs or the yearly flat amount. Ask for room size as a share of total Wohnfläche, plus Miete/Nebenkosten amounts, and for the months in which the room was the centre.
If option 2 -> do not decide whether the room is still the centre. Flag as T2. If it is not the centre, no room costs are deductible and only the daily flat amount is left. Ask for the home working days as in option 3.
If option 3 -> ask for the number of days in the tax year on which the work was done mainly at home and no first place of work was visited. Record the days. The day rate and the cap are in the table. The amount is worked out in `de-einkommensteuer-freelancer`.
If option 4 -> rent already in Betriebsausgaben. Skip.
If option 5 -> skip entirely.

**Private use of a business car: the statute**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__6.html |
| Business use above which the list-price method (1%-Regelung) applies | 50% | § 6(1) no. 4 EStG: "das zu mehr als 50 Prozent betrieblich genutzt wird" |
| Private use per calendar month, as a share of the German list price at first registration plus extras, VAT included | 1% | § 6(1) no. 4 EStG: "für jeden Kalendermonat mit 1 Prozent des inländischen Listenpreises" |

**Trips between home and the first business premises: the commuting allowance**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/estg/__9.html |
| Per full kilometre of the one-way distance, per day on which the premises are visited, from the first kilometre | EUR 0.38 | § 9(1) sentence 3 no. 4 EStG: "von 0,38 Euro anzusetzen, höchstens jedoch 4 500 Euro im Kalenderjahr" |
| Yearly cap. It does not apply so far as the client uses an own car or a car put at his or her disposal | EUR 4,500 | § 9(1) sentence 3 no. 4 EStG: "höchstens jedoch 4 500 Euro im Kalenderjahr" |

**Business trips in a private car: flat rate per kilometre driven**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/brkg_2005/__5.html |
| Car, per kilometre driven, in place of the actual costs | 30 cents | § 5(2) BRKG: "beträgt die Wegstreckenentschädigung 30 Cent je Kilometer zurückgelegter Strecke". § 9(1) sentence 3 no. 4a EStG points to this rate |

- **Three different trips.** A business trip, for example to a customer, counts every kilometre driven. A trip between the taxpayer's home and his or her own first business premises (erste Betriebsstätte) is not a business trip: § 4(5) no. 6 EStG applies the employee commuting rule to business owners, and the EÜR instructions say "Grundsätzlich darf nur die Entfernungspauschale als Betriebsausgabe berücksichtigt werden". It counts the one-way distance. Private trips are not deductible at all. https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2
- **One commuting rate in 2026.** The rate applies from the first kilometre. Older versions of this Guide give it only from the 21st kilometre. The ministry says that was the rule before 1 January 2026 (link in Section 1).
- **The list-price method is not open to every car.** It applies only to a car used for the business above the share in the table. For a car at or below that share, the private use is valued at the part of the total car costs that falls on the non-business trips (2026 EÜR instructions, line 20: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2). For a car above the share, the logbook (Fahrtenbuch) is the alternative to the list price (§ 6(1) no. 4 sentence 3 EStG).
- **List price, never the price paid.** The base is the German list price at first registration plus extras, including VAT.
- **Electric and plug-in hybrid cars** have a reduced list price under the same paragraph. Flag them. Not covered here.

Call `ask_user_input_v0` with:

~~~
Q: "Kfz: business use method?"
   Options: [
     "Fahrtenbuch (logbook kept all year)",
     "1%-Regelung (Bruttolistenpreis method)",
     "Private car, flat rate per kilometre driven on business trips (no car in Betriebsvermögen)",
     "No vehicle used for business"
   ]
~~~

If Fahrtenbuch -> ask for total km, business km, and vehicle costs. Work out the business share.
If 1%-Regelung -> first ask whether the car is used for the business above the share in the table. If yes, ask for the Bruttolistenpreis and the months of use and record them. If no, the list-price method is not open: record `kfz_method` as `cost_share`, ask for the total car costs and the business share, and flag T2. The private use addition is worked out in `de-einkommensteuer-freelancer`.
If flat rate per kilometre -> ask for the business km driven. The rate is in the business trip table.
For every car -> ask whether the client drives between home and a fixed business premises, on how many days, and the one-way distance.
If no vehicle -> skip.

Call `ask_user_input_v0` with:

~~~
Q: "Kirchensteuer?"
   Options: [
     "Yes: I belong to a religious community that levies church tax (for example evangelisch or katholisch)",
     "No: no membership (ausgetreten or never joined)"
   ]
~~~

If yes -> ask for the Bundesland and read the rate from the client's last Steuerbescheid.

**Church tax rates: the ministry's tax booklet, 2025 edition**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9 |
| Lower of the two rates, charged on the income tax | 8% | Tax booklet, 2025 edition: "je nach Bundesland 8 oder 9 Prozent" |
| Higher of the two rates, charged on the income tax | 9% | Same sentence |

- **Who pays.** Members of a religious community that levies church tax. The booklet: "Steuerpflichtig sind die Mitglieder oder Angehörigen einer Kirchensteuer erhebenden Gemeinschaft."
- **Which state has which rate.** The booklet says the rate is fixed by the church tax decisions of the religious communities and differs by federal state. It does not list the states, and no page on the official hosts read for this Guide prints a list. Older versions of this Guide give the lower rate to Bayern and Baden-Württemberg. Treat that as unconfirmed and read the rate from the client's last Steuerbescheid.

Call `ask_user_input_v0` with:

~~~
Q: "Bundesland?"
   Options: [
     "Baden-Württemberg", "Bayern", "Berlin", "Brandenburg", "Bremen",
     "Hamburg", "Hessen", "Mecklenburg-Vorpommern", "Niedersachsen",
     "Nordrhein-Westfalen", "Rheinland-Pfalz", "Saarland", "Sachsen",
     "Sachsen-Anhalt", "Schleswig-Holstein", "Thüringen"
   ]
~~~

Needed for: Kirchensteuersatz and Gewerbesteuer Hebesatz (if Gewerbetreibender: the Hebesatz of the municipality is looked up during assembly).

**Pension duty.** Ask every client three things: "Is your work teaching, training or coaching, nursing or child care, midwifery, art or publishing, or a craft entered in the Handwerksrolle?", "Do you work, on a lasting basis, essentially for one client only?" and "Do you employ anyone who is subject to social insurance?" § 2 SGB VI makes these self-employed people, among others, compulsorily insured: teachers and educators, and carers in sick, maternity, infant or child care, in each case if they regularly employ no insured employee; midwives; artists and publicists (under the Künstlersozialversicherungsgesetz); craftspeople entered in the Handwerksrolle; and anyone who regularly employs no insured employee and works on a lasting basis and essentially for one customer only ("auf Dauer und im Wesentlichen nur für einen Auftraggeber"). A marginally employed person (Minijob) does not count as an employee for these tests. If a duty may exist and no pension payments show on the bank statement, flag it and route to `de-social-contributions`. https://www.gesetze-im-internet.de/sgb_6/__2.html

**EÜR or balance sheet.** This workflow assumes the cash-basis EÜR. Anyone who is not obliged by law to keep books, and does not keep them by choice, may use it (§ 4(3) EStG). Ask whether the client files an EÜR or a balance sheet, and whether the tax office has ever sent a notice to start keeping books.

**Tax-law bookkeeping duty: commercial businesses only**

| What | Value | Note |
| --- | --- | --- |
| Source | all figures below | https://www.gesetze-im-internet.de/ao_1977/__141.html |
| Total turnover of the single business in the calendar year: the duty can start above | EUR 800,000 | § 141(1) no. 1 AO: "von mehr als 800 000 Euro im Kalenderjahr" |
| Profit from the commercial business in the business year: the duty can start above | EUR 80,000 | § 141(1) no. 4 AO: "einen Gewinn aus Gewerbebetrieb von mehr als 80 000 Euro im Wirtschaftsjahr" |

- **Either limit is enough.** The law joins the tests with "oder".
- **The duty does not start by itself.** It starts with the business year that follows the tax office's notice pointing out the duty (§ 141(2) AO). Until that notice arrives, § 141 AO creates no duty. A duty under commercial law (last bullet) is a separate matter.
- **Freiberufler are not named.** § 141 AO covers commercial businesses and farmers only.
- **Merchants.** A merchant (Kaufmann) must keep books under commercial law (§ 238 HGB at https://www.gesetze-im-internet.de/hgb/__238.html), and that duty counts for tax too (§ 140 AO at https://www.gesetze-im-internet.de/ao_1977/__140.html). Small sole merchants can be released under § 241a HGB: see `germany-bookkeeping` for that test. A client entered in the Handelsregister, or one who files a balance sheet for any reason, is outside this workflow: refer. This is the Guide's own scope line, not law: a sole merchant released under § 241a HGB need not keep books.

**Business in another tax office's district.** If the tax office responsible for the business is not also the one responsible for the client's income tax, for example because the business is run from another town, the business income is determined separately (§ 180(1) no. 2 b AO at https://www.gesetze-im-internet.de/ao_1977/__180.html). Ask where the business is run from and flag a mismatch.

Flag all private-use percentages as T2: the Steuerberater must confirm the percentage is reasonable and documented.

## Section 7: The final handoff

Once gap-filling is done, produce a final handoff message and hand off to `de-return-assembly`.

**Example handoff message:**

> Intake complete. Here's what's going to the return assembly:
>
> Freiberufler, single, Regelbesteuerung, full-year Germany resident (Berlin). Betriebseinnahmen [amount], estimated Gewinn about [amount] before Sonderausgaben and außergewöhnliche Belastungen.
>
> I'm now going to run the full German return preparation. This covers:
> 1. UStVA (open periods of [tax year] and the Umsatzsteuererklärung)
> 2. ESt + EÜR (Einkommensteuererklärung with Anlage EÜR, Anlage S/G, Anlage Vorsorgeaufwand)
> 3. Sozialversicherungsbeiträge reconciliation (KV/PV/RV)
> 4. Gewerbesteuer (if Gewerbetreibender)
> 5. Vorauszahlungen schedule for the following year
>
> You'll get back:
> 1. An Excel working paper with all forms and live formulas
> 2. A reviewer brief with positions, citations, and flags for your Steuerberater
> 3. A filing calendar with all upcoming deadlines
>
> Starting now.

Then internally invoke `de-return-assembly` with the structured intake package.

## Section 8: Structured intake package (internal format)

The downstream Guide (`de-return-assembly`) consumes a JSON structure. It is internal and not shown to the user unless they ask. `tax_year` is the year being prepared. `kirchensteuer_rate` stays `null` until it is read from the client's Steuerbescheid. Never fill it with a default: the church tax table gives two rates and cannot say which state has which. In this package a zero means a real zero and `null` means not yet known. Use `null` for `gesamtumsatz_prior_year`, `gesamtumsatz_current_year` and `gewerbesteuer.applies` while they are unknown. Key fields:

~~~json
{
  "jurisdiction": "DE",
  "tax_year": 2026,
  "taxpayer": {
    "name": "",
    "birth_year": 0,
    "marital_status": "single | married | single_parent",
    "residency": "full_year",
    "bundesland": "",
    "municipality": "",
    "steuernummer": "",
    "ust_id_nr": "",
    "vat_status": "regelbesteuerung | kleinunternehmer | unsettled",
    "business_type": "freiberufler | gewerbetreibender | unsettled",
    "profession_as_stated": "",
    "trade_registration": false,
    "profit_method": "euer | bilanz",
    "industry": "",
    "entity_type": "sole_proprietor",
    "kirchensteuer": true,
    "kirchensteuer_rate": null
  },
  "income": {
    "betriebseinnahmen_netto": 0,
    "ust_collected": 0,
    "eu_reverse_charge_income": 0,
    "drittland_income": 0,
    "other_income": 0,
    "client_breakdown": []
  },
  "expenses": {
    "fully_deductible": [],
    "mixed_use": [],
    "limited_deduction": [],
    "capital_items": [],
    "gkv_pkv": {
      "type": "GKV | PKV",
      "annual_premium": 0,
      "basisabsicherung": 0,
      "sick_pay_claim": false,
      "pflegeversicherung": 0
    }
  },
  "vat": {
    "gesamtumsatz_prior_year": null,
    "gesamtumsatz_current_year": null,
    "kleinunternehmer_waived": false,
    "ustva_period": "monthly | quarterly | released | none",
    "ustva_filed": [],
    "dauerfristverlaengerung": false,
    "sondervorauszahlung": 0,
    "vorsteuer_reclaimable": 0,
    "reverse_charge_purchases": 0,
    "exempt_supplies": false
  },
  "sozialversicherung": {
    "gkv_or_pkv": "GKV | PKV",
    "annual_kv_premium": 0,
    "annual_pv_premium": 0,
    "rentenversicherung": {
      "type": "none | freiwillig | pflicht_ksk | pflicht_other | unsettled",
      "annual_amount": 0
    }
  },
  "vorauszahlungen": {
    "est_quarterly": [],
    "solz_quarterly": [],
    "kist_quarterly": [],
    "total_est_paid": 0,
    "total_solz_paid": 0,
    "total_kist_paid": 0
  },
  "prior_year": {
    "festgesetzte_est": 0,
    "festgesetzter_solz": 0,
    "festgesetzte_kist": 0,
    "gewinn": 0,
    "afa_schedule": []
  },
  "home_office": {
    "type": "mittelpunkt | tagespauschale | unsettled | none",
    "days_worked_at_home": 0,
    "months_room_was_centre": 0,
    "room_percentage": 0,
    "annual_amount": 0
  },
  "private_use": {
    "kfz_method": "fahrtenbuch | 1pct_regelung | cost_share | km_pauschale | none",
    "kfz_business_pct": 0,
    "kfz_bruttolistenpreis": 0,
    "commute_days": 0,
    "commute_one_way_km": 0,
    "telefon_business_pct": 0,
    "internet_business_pct": 0
  },
  "gewerbesteuer": {
    "applies": null,
    "hebesatz": 0,
    "municipality": ""
  },
  "open_flags": [],
  "refusals_triggered": [],
  "documents_received": []
}
~~~

## Section 9: Refusal handling

Refusals fire from either the refusal sweep (Section 2) or during inference (e.g., GmbH structure discovered in documents, or a balance sheet instead of an EÜR).

When a refusal fires:
1. Stop the workflow
2. State the specific reason in one sentence
3. Recommend the path forward (specific practitioner type)
4. Offer to continue with partial help ONLY if the out-of-scope item is cleanly separable (rare)

**Do not:**
- Apologize profusely
- Try to work around the refusal
- Suggest the user "might be able to" fit into scope if they answer differently
- Continue silently

**Sample refusal:**

> Stop. You have a registered GmbH. I'm set up for Freiberufler and Gewerbetreibende (Einzelunternehmer) only. GmbHs file Körperschaftsteuererklärung and Gewerbesteuererklärung with separate rules for Geschäftsführergehalt and Gewinnausschüttungen. You need a Steuerberater familiar with Kapitalgesellschaften.
>
> I can't help with this one.

## Section 10: Self-checks

- **Check IN1.** No one-question-at-a-time prose in the refusal sweep. If the assistant asked "Question 1 of 10" or walked through questions as separate messages, check fails.
- **Check IN2.** Refusal sweep used `ask_user_input_v0`, or one batched list where no such tool exists. The first substantive interaction was a batch, not a chain of prose questions.
- **Check IN3.** Upload-first flow honoured. After the refusal sweep, the assistant asked for a document dump before asking any content questions.
- **Check IN4.** Documents were parsed and inferred before asking questions. The inference summary (Section 5) was shown before gap-filling questions (Section 6).
- **Check IN5.** Gap-filling only asked about things NOT visible in documents. If the assistant asked "did you pay Krankenversicherung" after the bank statement showed TK payments, check fails.
- **Check IN6.** Open flags captured. Anything ambiguous, risky, or attention-worthy during inference is in the `open_flags` list in the handoff package.
- **Check IN7.** Handoff to `de-return-assembly` is explicit. The user was told "I'm now going to run the return preparation," and the downstream orchestrator was explicitly invoked with the intake package.
- **Check IN8.** Reviewer step was stated upfront and reiterated before handoff. The opening message mentioned Steuerberater signoff.
- **Check IN9.** Refusals were clean. No hedging. Stop means stop.
- **Check IN10.** No meta-commentary about workflow phases. The assistant did not say "Phase 1," "Phase 2," etc.
- **Check IN11.** Total user-facing turn count is low. Target: 8 turns or fewer from start to handoff for a prepared user (1 refusal batch + 1 upload + 1 confirmation + 1 to 3 gap fills + 1 handoff). More than 12 turns for a normal intake is a check failure.
- **Check IN12.** VAT status was established. Regelbesteuerung vs Kleinunternehmer was confirmed before inference, as it changes how every transaction is classified. For a Kleinunternehmer both turnover limits were tested, not one.
- **Check IN13.** Business type was established. Freiberufler vs Gewerbetreibender was recorded as the client states it, tested against the § 18 EStG list, and flagged where the list does not name the work. The assistant did not tell a client whose work is not named that they are a Freiberufler, and did not tell them that they are a Gewerbetreibender.

## Section 11: Performance targets

For a prepared user (documents in a folder, ready to upload):
- **Refusal sweep**: 45 seconds (1 to 2 interactive turns)
- **Document upload**: 2 minutes (1 upload turn)
- **Inference and confirmation display**: 1 minute of assistant processing + 1 turn for user confirmation
- **Gap filling**: 2 minutes (2 to 3 interactive turns)
- **Handoff**: immediate
- **Total**: about 6 minutes

For an unprepared user (has to go fetch documents):
- Refusal sweep: same
- Document discovery: 10 to 20 minutes offline
- Rest: same
- **Total**: 15 to 25 minutes

## Section 12: Cross-Guide references

**Inputs:** User-provided documents and answers.

**Outputs:** Structured intake package consumed by `de-return-assembly`.

**Downstream Guides triggered (via `de-return-assembly`):**
- `germany-vat-return`: UStVA / Umsatzsteuererklärung
- `de-einkommensteuer-freelancer`: ESt + EÜR (Einkommensteuererklärung with Anlage EÜR)
- `de-social-contributions`: Krankenversicherung / Pflegeversicherung / Rentenversicherung
- `de-trade-tax`: Gewerbesteuer (only if Gewerbetreibender)
- `de-estimated-tax`: Vorauszahlungen schedule

**Other Guides this intake routes to:**
- `germany-bookkeeping`: EÜR or double-entry books, record keeping
- `germany-einvoice`: e-invoice duty and formats
- `de-rental-income`, `de-capital-gains`, `de-crypto-tax`: other income found during gap filling

### Change log

- **v0.1 (April 2026):** Initial draft. Upload-first, inference-then-confirm pattern modelled on `mt-freelance-intake` v0.1.
- **Refresh (September 2026):** Figures read again on the official pages for tax year 2026 and moved into sourced tables. Freiberufler test rewritten from the text of § 18 EStG. Commuting rule, home office test, Kleinunternehmer return duties and the health insurance split corrected. Example amounts replaced by placeholders.

## The method, step by step

1. Fix the tax year and test residency. A person with a home or habitual abode in Germany is fully liable to income tax (§ 1(1) EStG). This Guide covers full-year residents only. https://www.gesetze-im-internet.de/estg/__1.html
2. Classify the activity against § 18(1) no. 1 EStG (liberal professions) and § 15(2) EStG (Gewerbebetrieb). Record the client's own statement, test it against the list in Section 2, and flag anything the list does not name. The tax office decides. https://www.gesetze-im-internet.de/estg/__18.html
3. For a new business, check the registration. The start must be reported within one month: a commercial business to the municipality, freelance work to the tax office. The Fragebogen zur steuerlichen Erfassung goes to the tax office through ELSTER within the same month (§ 138(1), (1b) and (4) AO). https://www.gesetze-im-internet.de/ao_1977/__138.html and https://www.elster.de/elsterweb/infoseite/unternehmensgruendung
4. Settle the VAT status under § 19 UStG: both turnover limits, the start-up year limit, any waiver. Doing this before reading the invoices matters, because it changes how every transaction is recorded (net or gross). https://www.gesetze-im-internet.de/ustg_1980/__19.html
5. For a Regelbesteuert client, set the advance return period under § 18(2) UStG from last year's VAT, and note any Dauerfristverlängerung (§§ 46 and 47 UStDV). https://www.gesetze-im-internet.de/ustg_1980/__18.html
6. Confirm the profit method. The EÜR is open to anyone not obliged to keep books who does not keep them by choice (§ 4(3) EStG). A Gewerbetreibender can be pulled into bookkeeping by a notice under § 141 AO. A client who files a balance sheet is referred. https://www.gesetze-im-internet.de/ao_1977/__141.html
7. Collect the documents (Section 3) and parse them (Section 4). Sort purchases with the limits of § 6(2) and (2a) EStG for assets and § 4(5) EStG for gifts, entertainment and the home office. https://www.gesetze-im-internet.de/estg/__6.html and https://www.gesetze-im-internet.de/estg/__4.html
8. Read the prepayments from the Vorauszahlungsbescheid and the bank statement against the four due dates of § 37(1) EStG. https://www.gesetze-im-internet.de/estg/__37.html
9. Record the social insurance position: health insurance contributions as § 10(1) no. 3 EStG sorts them, and the pension duty test of § 2 SGB VI. https://www.gesetze-im-internet.de/sgb_6/__2.html
10. Show the summary (Section 5), fill the gaps (Section 6), and write every unsettled point into `open_flags`.
11. Tell the client how the returns are sent and when. The Anlage EÜR goes to the tax office electronically (§ 60(4) EStDV at https://www.gesetze-im-internet.de/estdv_1955/__60.html). A yearly return is due seven months after the end of the calendar year, or by the last day of February of the second following year if a tax adviser prepares it (§ 149(2) and (3) AO at https://www.gesetze-im-internet.de/ao_1977/__149.html). The longer deadlines of Art. 97 § 36 EGAO covered tax periods 2020 to 2024 only: https://www.gesetze-im-internet.de/aoeg_1977/art_97__36.html
12. Hand the package to `de-return-assembly` (Section 7). If the order is changed and documents are parsed before the VAT status and the business type are known, every amount has to be read twice.

## Ask the client first

- Which tax year are you preparing, and did you live in Germany for all of it?
- What exactly do you do, what training is it based on, and are you registered only with the tax office or also with the trade office? Do you sell goods, earn commissions or resell anything alongside your main work?
- What was your total turnover last calendar year, and what is it so far this year? Do your invoices show VAT, and have you ever waived the Kleinunternehmer rule?
- Do you file an EÜR or a balance sheet, and has the tax office ever sent you a notice to start keeping books?
- Is your work teaching, training or coaching, nursing or child care, midwifery, art or publishing, or a craft entered in the Handwerksrolle? Do you work essentially for one client, and do you employ anyone who is subject to social insurance?
- Do you have other income: a job, rent, investments, crypto, a share in a partnership?

## When to refuse or refer

- Part-year residents and non-residents (beschränkte Steuerpflicht). Refer to a Steuerberater who handles non-resident returns.
- Partnerships (GbR, PartG, OHG, KG) as the business itself. They file a Feststellungserklärung. A client who is a partner alongside an own sole business stays in scope, with a flag.
- GmbH, UG and other corporations.
- More than 5 employees. Payroll itself is out of scope at any number.
- A client who keeps double-entry books or files a balance sheet for the year being prepared, including a merchant entered in the Handelsregister and a Gewerbetreibender whose bookkeeping duty under § 141 AO has already started. The duty starts only with the business year that follows the notice (§ 141(2) AO), so a client who received the notice during the year being prepared is still in scope for that year: flag it.
- An unsettled classification that matters: work that § 18 EStG does not name, a freelance and a commercial activity that cannot be separated, or staff doing work the client does not lead. Record it, flag it, and tell the client that the tax office decides and that a Steuerberater or a binding ruling can settle it. Do not settle it yourself.
- Whether a room at home is the centre of all the work, where the client also works elsewhere.
- A Kleinunternehmer who has crossed, or is about to cross, a turnover limit during the year, or who owes VAT as the recipient of services from abroad. Route to `germany-vat-return`.
- Goods sold across borders, distance sales to consumers in other EU states, and the one-stop shop. Route to `germany-vat-return`.
- Electric and plug-in hybrid business cars, and any car whose business share is disputed.
- Farming and forestry.
- The church tax rate for a given state. Read it from the client's Steuerbescheid.
- Business premises in the district of another tax office (separate determination of the business income under § 180(1) no. 2 b AO).

## Sources

- EStG § 1, § 15, § 18 (tax liability, Gewerbebetrieb, liberal professions): https://www.gesetze-im-internet.de/estg/__1.html and https://www.gesetze-im-internet.de/estg/__15.html and https://www.gesetze-im-internet.de/estg/__18.html
- EStG § 4, § 6, § 9, § 10, § 37 (EÜR and restricted expenses, assets and car, commuting, insurance contributions, prepayments): https://www.gesetze-im-internet.de/estg/__4.html and https://www.gesetze-im-internet.de/estg/__6.html and https://www.gesetze-im-internet.de/estg/__9.html and https://www.gesetze-im-internet.de/estg/__10.html and https://www.gesetze-im-internet.de/estg/__37.html
- EStDV § 60 (EÜR sent electronically): https://www.gesetze-im-internet.de/estdv_1955/__60.html
- BRKG § 5 (mileage rate that § 9 EStG points to): https://www.gesetze-im-internet.de/brkg_2005/__5.html
- GewStG § 2, § 11 (what trade tax covers, allowance): https://www.gesetze-im-internet.de/gewstg/__2.html and https://www.gesetze-im-internet.de/gewstg/__11.html
- UStG § 1, § 3a, § 12, § 13b, § 14, § 14c, § 15, § 18, § 18a, § 19, § 27: https://www.gesetze-im-internet.de/ustg_1980/__1.html and https://www.gesetze-im-internet.de/ustg_1980/__3a.html and https://www.gesetze-im-internet.de/ustg_1980/__12.html and https://www.gesetze-im-internet.de/ustg_1980/__13b.html and https://www.gesetze-im-internet.de/ustg_1980/__14.html and https://www.gesetze-im-internet.de/ustg_1980/__14c.html and https://www.gesetze-im-internet.de/ustg_1980/__15.html and https://www.gesetze-im-internet.de/ustg_1980/__18.html and https://www.gesetze-im-internet.de/ustg_1980/__18a.html and https://www.gesetze-im-internet.de/ustg_1980/__19.html and https://www.gesetze-im-internet.de/ustg_1980/__27.html
- UStDV § 34a, § 46, § 47 (Kleinunternehmer invoices, Dauerfristverlängerung): https://www.gesetze-im-internet.de/ustdv_1980/__34a.html and https://www.gesetze-im-internet.de/ustdv_1980/__46.html and https://www.gesetze-im-internet.de/ustdv_1980/__47.html
- HGB § 238 (merchants keep books): https://www.gesetze-im-internet.de/hgb/__238.html
- AO § 138, § 140, § 141, § 149, § 180 (registration, bookkeeping duty, filing deadlines, separate determination): https://www.gesetze-im-internet.de/ao_1977/__138.html and https://www.gesetze-im-internet.de/ao_1977/__140.html and https://www.gesetze-im-internet.de/ao_1977/__141.html and https://www.gesetze-im-internet.de/ao_1977/__149.html and https://www.gesetze-im-internet.de/ao_1977/__180.html
- EGAO Art. 97 § 36 (longer filing deadlines, tax periods 2020 to 2024 only): https://www.gesetze-im-internet.de/aoeg_1977/art_97__36.html
- SGB VI § 2 (self-employed people with pension duty): https://www.gesetze-im-internet.de/sgb_6/__2.html
- SGB V, table of contents (where the additional health contribution sits): https://www.gesetze-im-internet.de/sgb_5/
- Finance ministry, EÜR form and instructions for 2026, letter of 1 September 2026: https://www.bundesfinanzministerium.de/Content/DE/Downloads/BMF_Schreiben/Steuerarten/Einkommensteuer/2026-09-01-anlage-EUER-2026.pdf?__blob=publicationFile&v=2
- Finance ministry, tax booklet (Steuern von A bis Z), 2025 edition: https://www.bundesfinanzministerium.de/Content/DE/Downloads/Broschueren_Bestellservice/steuern-von-a-z.pdf?__blob=publicationFile&v=9
- Finance ministry, what changes in 2026: https://www.bundesfinanzministerium.de/Content/DE/Standardartikel/Themen/Steuern/das-aendert-sich-2026.html
- Economics ministry (BMWE) start-up portal, liberal professions, and an expert article on mixed activities hosted there: https://www.existenzgruendungsportal.de/gruenden-kurz-und-knapp/freie-berufe and https://www.existenzgruendungsportal.de/SharedDocs/Expertenforum_Unterseiten/Freie-Berufe/Gemischte-Taetigkeiten/Gemischte-Taetigkeiten
- ELSTER, tax number for a new business: https://www.elster.de/elsterweb/infoseite/unternehmensgruendung

## End of Intake Guide v0.1

End of the intake Guide, version 0.1, refreshed for tax year 2026.

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
