Source: this is a Markdown copy of the free page at https://circuits.fit/guides/it-risk-register-excel.html.

# How to build an IT risk register in Excel

Write the scales first, then look scores up from a 5 by 5 grid. Columns, formulas, severity bands and a worked example.

## Who this is for

The IT or security manager who needs a working risk register in a spreadsheet, and the finance or audit lead who has to read it.

An IT risk register is only as good as the agreement behind its numbers. The spreadsheet part takes an afternoon. Getting two people to give the same risk the same score takes longer, and it is the part that matters.

This guide builds a register in Excel (it works the same way in LibreOffice Calc and Google Sheets) around a 5 by 5 likelihood by impact matrix: the columns, the lookup formulas, severity bands that set how often each risk is reviewed, and a worked example with the arithmetic shown.

## What the register is for

A risk register lists the things that could go wrong with your technology, how likely and how damaging each one is, what you are doing about it, and who is accountable. It is a decision tool: it tells leadership where to spend money and attention, and it shows an auditor, insurer or board that risks are known and owned.

Keep it separate from two neighbouring lists. A vulnerability or findings tracker holds individual technical issues with fix dates. A [risk exception register](https://circuits.fit/guides/risk-exception-register-template.html) holds approved, time-limited departures from a control. A risk register sits above both: "a critical system is compromised through an unpatched internet-facing service" is a risk; a specific missing patch is a finding; an approved decision not to patch one server until March is an exception. The three can reference each other by ID, but merging them makes each harder to read.

## The columns

| Column | What to enter |
| --- | --- |
| Risk ID | A unique reference such as R-007 |
| Risk statement | Cause, event and consequence in one sentence |
| Category | Security, availability, vendor, data, compliance, people |
| Asset or service | What is affected, using your inventory names |
| Risk owner | A named person who can approve spending to treat it |
| Existing controls | What is in place today, specifically |
| Inherent likelihood and impact (1 to 5) | The risk before those controls |
| Residual likelihood and impact (1 to 5) | The risk with those controls working |
| Treatment | Reduce, accept, transfer or avoid |
| Planned actions and due date | What will change the residual score, and when |
| Last reviewed | Date of the most recent review |

Calculated columns follow: inherent score and severity, residual score and severity, next review due, and an overdue flag.

Write risk statements in the form "because of [cause], [event] could happen, leading to [consequence]". "Phishing" is a topic. "Because staff can approve payment changes by email, an attacker impersonating a supplier could redirect a payment, leading to a direct financial loss" is a risk someone can score and treat.

## Write the scales first

Before anyone scores anything, write a one-line definition for each level, and put them on a settings tab next to the matrix. For example:

| Level | Likelihood | Impact |
| --- | --- | --- |
| 1 | Rare: not expected in the next year | Minimal: little or no effect on operations, data or customers |
| 2 | Unlikely: could happen, no sign it is being attempted | Minor: short disruption or limited internal data exposure |
| 3 | Possible: plausible; similar issues seen elsewhere | Moderate: noticeable disruption, some customer or financial effect |
| 4 | Likely: expected to be attempted or to occur | Major: significant outage, sensitive data exposure or financial loss |
| 5 | Almost certain: already happening or easy to exploit | Severe: prolonged outage, large breach or regulatory action |

Where you can, attach numbers to impact levels that fit your company: a dollar range, hours of downtime, number of customer records. "Major" means something very different to a 30-person firm and a 3,000-person one. If you use a published method such as NIST SP 800-30, follow its structure, but the definitions still have to be written for your organization.

The middle levels are the hardest. If Possible and Likely cannot be told apart in writing, most risks will end up scored 3 by 3, and the register will look tidy while saying very little.

## Building the 5 by 5 matrix in Excel

Put the matrix on the settings tab as a grid: likelihood 1 to 5 down the rows, impact 1 to 5 across the columns, and the score in each cell. The default is likelihood multiplied by impact, so the grid runs from 1 in the top left to 25 in the bottom right. Say the grid occupies `Settings!C12:G16`.

In the register, look the score up from the grid instead of multiplying in each row:

```
Inherent score: =IF(OR(H5="",I5=""),"",INDEX(Settings!$C$12:$G$16,H5,I5))
Residual score: =IF(OR(J5="",K5=""),"",INDEX(Settings!$C$12:$G$16,J5,K5))
```

Why bother, when `=H5*I5` gives the same answer? Because many organizations eventually want to weight impact more heavily than likelihood, for example so that a rare but severe event scores higher than a frequent trivial one. With a lookup grid, that is a change to a few cells on one tab. With multiplication, it is a rewrite of every row.

Use data validation to limit likelihood and impact cells to whole numbers from 1 to 5. A typed 3.5 or "med" breaks the lookup. If you want the heat map look, apply conditional formatting to the grid itself and to the severity columns so the colour follows the band.

## Severity bands and review frequency

Turn the score into a severity with a small table of minimum scores and an approximate-match lookup:

```
Severity: =IF(Q5="","",VLOOKUP(Q5,Settings!$B$20:$C$23,2,TRUE))
```

| Minimum score | Severity | Review every |
| --- | --- | --- |
| 1 | Low | 180 days |
| 5 | Medium | 90 days |
| 10 | High | 60 days |
| 20 | Critical | 30 days |

`VLOOKUP` with `TRUE` returns the band for the largest minimum score that does not exceed the score, so the minimums must stay in ascending order. These bands are an example, not a standard. Set them to match your risk appetite, and write down who approved them.

Add a third column to the band table for review frequency, then calculate next review due from residual severity:

```
Next review due: =IF(W5="","",W5+VLOOKUP(T5,Settings!$C$20:$D$23,2,FALSE))
Overdue?:        =IF(X5="","",IF(X5<TODAY(),"Overdue","OK"))
```

This is what keeps the register alive. High and Critical risks come back to the table often; Low ones do not consume meeting time.

## A worked example

Two invented risks, scored with the scales and bands above.

**R-007: payment redirection.** "Because supplier bank details can be changed on the strength of an email, an attacker impersonating a supplier could redirect a payment, leading to a direct financial loss."

- Inherent: likelihood 4 (these attempts are common), impact 4 (a single payment could be large). Score 16, High.
- Existing controls: any bank detail change requires a call-back to a number already on file, and a second approver in finance.
- Residual: likelihood 2, impact 4. Score 8, Medium, reviewed every 90 days.
- Treatment: reduce. Action: add the call-back step to the payments system workflow so it cannot be skipped, due end of quarter.

**R-012: ransomware on file servers.** "Because staff can open email attachments on machines with access to shared drives, ransomware could encrypt the file servers, leading to a multi-day outage."

- Inherent: likelihood 3, impact 5. Score 15, High.
- Existing controls: EDR on all endpoints, nightly backups with an offline copy, restore tested last quarter.
- Residual: likelihood 2, impact 5. Score 10, still High, reviewed every 60 days.

R-012 shows something useful. Good controls cut the likelihood, but the impact of a successful attack stays severe, so the residual score lands exactly on the High boundary. That is not a scoring error. It tells the owner that further work should aim at impact, for example faster restore or segmenting the shares, and it tells the board this risk deserves attention even with strong controls in place.

## Common mistakes

- **No written scales.** Scores then reflect who filled in the row.
- **Everything is a 3 by 3.** Usually a sign the middle definitions are too close together.
- **Residual scored on planned controls.** Score the controls that are running today. Planned work goes in the actions column.
- **Topics instead of risks.** "Cloud" cannot be scored or owned.
- **Typed severities.** A severity typed by hand and a severity calculated from the score will disagree eventually. Always calculate.
- **No review date.** A register without review dates is a snapshot from the day it was written.
- **Owner is a department.** A department cannot approve a budget line. A person can.

## FAQ

### Should we use a 3 by 3 or a 5 by 5 matrix?

A 3 by 3 is easier to score consistently. A 5 by 5 gives more resolution, but only if the five levels are clearly defined. Start with whichever your team will actually apply the same way.

### How many risks should be on the register?

Enough that every significant system and process is covered, few enough that each one gets reviewed. Many small and mid-sized companies keep a few dozen. Combine near-duplicates.

### Where do accepted risks go?

An accepted risk stays on the risk register with treatment "accept" and a review date. If acceptance means departing from a specific control, record that departure in the exception register too, with an expiry.

### Does Excel 2016 work?

The formulas on this page do. Functions such as `MAXIFS`, useful for pulling the latest review date from a review log, need Excel 2019 or later.

Spreadsheet workbooks for renewal and risk tracking are described at https://circuits.fit/start/
