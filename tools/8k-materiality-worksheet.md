Source: this is a Markdown copy of the free page at https://circuits.fit/tools/8k-materiality-worksheet.html.

# SEC 8-K materiality worksheet

Record who decided an incident was material, and count four business days to the Item 1.05 date.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

Not legal advice. The Item 1.05 clock starts when the company determines the incident is material, not when it is discovered. This page counts four business days after that determination. It skips weekends and US federal holidays in the year of the determination and the following year. A holiday on Saturday is taken on Friday. A holiday on Sunday is taken on Monday. The page does not decide whether the incident is material.

## How to use this

1. Enter the discovery time and the escalation. Those dates are a record. They do not start the four-day count.
2. Name the person who owns the materiality decision, check the thresholds you actually use, and write the evidence you considered.
3. Enter the determination date. The output is the fourth business day after that date, and a one-page record you can copy or print.

## Why this worksheet exists

Since the SEC adopted its cybersecurity disclosure rules on July 26, 2023, a public company that determines a cybersecurity incident is material must file a Form 8-K under Item 1.05. The SEC’s release says the filing is generally due four business days after the company determines the incident is material, not four days after it is discovered. The release also allows a delay if the US Attorney General determines that immediate disclosure would pose a substantial risk to national security or public safety and notifies the Commission in writing.

That design puts weight on one moment: the materiality determination. Auditors, regulators and plaintiffs will later ask who made it, when, on what evidence, and against which thresholds. Most companies keep that record in email threads and meeting notes. This page turns it into one dated record you can print, save as PDF and attach to the incident file.

## Worked example

The page loads with an example. An incident is discovered on Thursday, October 1, 2026, at 9:30 AM and escalated at 11:00 AM. The CFO owns the decision. The company checks its financial and customer thresholds, notes that a customer list was exposed for two hours, and relies on a counsel memo dated October 6. The materiality determination is recorded at 4:00 PM on Tuesday, October 6.

The count starts the next day. Wednesday, October 7, is day one. Thursday, October 8, is day two. Friday, October 9, is day three. Monday, October 12, is Columbus Day, a US federal holiday, so it is skipped. Tuesday, October 13, 2026, is day four, and that is the date the page prints. The discovery date, five days earlier, does not move it.

Two more dates worth testing: a determination on Wednesday, November 25, 2026, counts past Thanksgiving to Wednesday, December 2. A determination on Wednesday, December 23 counts past Christmas Day to Wednesday, December 30.

## Assumptions and limits

- Business days exclude Saturdays, Sundays and US federal holidays for the determination year and the next year. A holiday that falls on a Saturday is treated as observed on Friday, and one that falls on a Sunday is observed on Monday.
- The page does not decide materiality. It records that someone did, and when.
- It does not model the Attorney General delay, amendments to an earlier 8-K, or foreign private issuer reporting on Form 6-K.
- Times are recorded as typed. Use the time zone your disclosure committee uses, and say which one in the evidence note.
- On the source page, inputs are saved only in that browser’s local storage.

## Questions readers ask

### Does a vulnerability on CISA’s known-exploited list start the clock?

No. A catalog listing is a patching signal. The clock starts only when the company determines an incident is material. If triage finds a compromise, the materiality analysis begins then.

### Who should own the decision?

That is a governance choice. Many companies assign it to a disclosure committee that includes the CFO, general counsel and CISO. The worksheet asks for one name so the record is never “the team.”

### Can we wait to be sure?

The SEC expects the materiality determination to be made without unreasonable delay after discovery. Record the evidence you were waiting for and why.

## Worksheet

Not legal, tax, insurance, or procurement advice. Item 1.05 of Form 8-K is due within four business days after the company determines a cybersecurity incident is material. The clock starts at the determination, not at discovery. Determine materiality without unreasonable delay. Count business days, skipping weekends and federal holidays.

### 1. Incident and escalation

- Incident discovered (date, time, zone):
- Who escalated it:
- When it was escalated:
- Who owns the materiality decision:

### 2. Evidence considered

- Systems and data affected:
- Operational impact:
- Financial impact (range):
- Customer, legal or regulatory exposure:
- Reputational factors:
- Threshold note (qualitative and quantitative):

### 3. Determination

- Material? (Yes / No / Not yet):
- Determined by (names, roles):
- Date and time of determination:
- Filing due (4th business day):
- Holidays skipped in the count:
- Counsel consulted:
- Board or committee informed (date):

### Checklist

- [ ] Decision owner named before an incident, with a deputy
- [ ] Record kept of who decided, when, and on what evidence
- [ ] Business-day count checked against the federal holiday calendar
- [ ] Disclosure committee and counsel contact list current
- [ ] Re-review date set if the answer is Not yet
