Source: this is a Markdown copy of the free page at https://circuits.fit/guides/software-renewal-tracker-template.html.

# How to build a software renewal tracker

Sort by the last day you can say no, not the renewal date. Columns, formulas, a scoring method and a worked example.

## Who this is for

The finance lead, IT manager or operations person who has been asked to "get the software renewals under control" and is about to open a blank spreadsheet.

A software renewal tracker is a list of contracts sorted by the last day you can still say no. Everything else in the sheet exists to help you decide what to say before that day arrives.

Most templates you will find are a vendor list with an expiry date column. That is a start, but it sorts by the wrong date and it does not tell you what to do. This guide walks through a tracker that does both: it calculates the notice deadline for each contract, and it scores each one so the quarterly review starts with a recommendation instead of a blank stare. You can build everything here in Excel, LibreOffice Calc or Google Sheets with ordinary formulas.

## What a renewal tracker is for

The tracker has three jobs. First, it stops a contract from renewing without a decision. Many software agreements renew automatically unless you give written notice a set number of days before the term ends. Once that notice window closes, the vendor has no reason to negotiate, because you are already committed to another term. Second, it puts evidence next to each decision: how many people use the tool, what it costs per active user, and what the vendor wants to charge next year. Third, it records who decided what, so the next review does not reopen the same question from scratch.

If your sheet only does the first job, it is a calendar. That is still worth having. But the second and third jobs are where the money is, because they turn "renew" from a default into a choice.

Keep one row per contract, not one row per vendor. A company with two separate order forms from the same vendor, signed a year apart, has two renewal dates and two notice deadlines. Merge them into one row and you will miss one of them.

## The input columns

These are the columns a person types into. Keep them on the left of the sheet and visually distinct from the formulas, for example white cells for inputs and grey for calculations, so nobody types over a formula.

| Column | What to enter | Where it comes from |
| --- | --- | --- |
| Vendor and product | The vendor name and the specific product or order form | The signed order form |
| Category | CRM, security, collaboration, finance and so on | Your own list; keep it short |
| Contract owner | One named person, not a team | Whoever uses the tool and will defend or drop it |
| Annual cost | Total cost per year; multiply monthly plans by 12 | The last invoice or the order form |
| Renewal date | The day the current term ends | The order form, not the billing portal |
| Notice period (days) | Days of notice the contract requires to cancel or change; 0 if none | The terms, usually in a renewal or termination clause |
| Auto-renews? | Yes or No | The same clause |
| Licensed seats and active users | Seats you pay for, and people who actually signed in recently | The tool's admin console |
| Usage % (if not seat-based) | Share of a usage commitment actually consumed | Usage reports, for metered or platform contracts |
| Business criticality | Low, Medium, High or Critical | The owner's honest answer to "what stops if this is down for a day" |
| Security items | SSO, MFA, SOC 2 report, SBOM availability, breach history | Security review, the vendor's trust page, questionnaire answers |
| Exit difficulty | Low, Medium or High | How hard it would be to export data and move |
| Price increase at renewal (%) | The increase in the renewal quote, or the contractual cap if there is no quote yet | The quote in writing |

Use drop-down lists (data validation) for every column with a fixed set of answers. A criticality column that contains "High", "high" and "HIGH - ask Sam" cannot be scored.

Decide in advance what "active" means. A common rule is a sign-in within the last 90 days. Whatever rule you pick, write it on an instructions tab and apply it the same way to every tool, or the usage numbers will not be comparable.

## The calculated columns

The notice deadline is the most important formula in the sheet, and it should always be a formula, never a typed date. With the renewal date in column F and the notice period in column G:

```
Notice deadline:            =IF(AND(ISNUMBER(F5),ISNUMBER(G5)),F5-G5,"")
Days until notice deadline: =IF(U5="","",U5-TODAY())
```

The `ISNUMBER` check matters. If the notice period is blank, a plain `=F5-G5` treats it as zero and shows the renewal date as the deadline, which looks safe and is not. A blank should produce a blank deadline and a visible prompt to go and read the contract.

If a contract states its notice period in months, use `=EDATE(F5,-G5)` with months in column G. Calendar months and 30-day blocks do not line up, so match what the contract says.

Then group the days remaining into windows that a meeting can work through: notice passed, next 30 days, 31 to 60 days, 61 to 90 days, later. A nested `IF` does this, and conditional formatting can colour each band.

Three money columns make the conversation concrete:

- **Effective usage %** is active users divided by licensed seats, capped at 100%, or the usage percentage for contracts that are not seat-based.
- **Cost per active user** is annual cost divided by active users. This is the number that surprises people, because a tool with a reasonable list price per seat can be expensive per person who uses it.
- **Estimated waste** is annual cost multiplied by (1 minus effective usage). It is an estimate, not a refund you are owed, but it is the right starting point for a seat true-down.

Add a next-year cost column, annual cost multiplied by (1 plus the price increase), so the meeting sees the real number being approved.

## Scoring a contract

A score does not make the decision. It sorts the list so the meeting spends its time on the contracts that need a conversation. A simple, explainable approach scores four things from 0 to 100 and takes a weighted average.

- **Usage score:** effective usage multiplied by 100. A tool used by 65% of its seats scores 65.
- **Criticality score:** Low 25, Medium 50, High 75, Critical 100.
- **Security score:** the average of points for each security item. For example SSO Yes 100, Partial 50, No 0; MFA Enforced 100, Available 60, No 0; SOC 2 Type II 100, Type I 60, None 0. Treat a blank as Unknown and give it low points (25 is reasonable), so missing answers pull the score down instead of being ignored.
- **Price score:** 100 at no increase, falling in a straight line to 0 at an increase you consider unacceptable, such as 20%. The formula is `=MAX(0,MIN(100,100*(1-increase/0.2)))`.

Weights are a policy choice. One reasonable starting set is usage 35, criticality 25, security 25 and price 15. Divide by the total of the weights rather than assuming they add up to 100, so anyone can change them without breaking the formula.

Then turn the score into a recommendation with rules checked in a fixed order:

1. **Cancel** if usage is below 25% and criticality is Low or Medium.
2. **Renew** if the score is at least 70 and the price increase is 5% or less.
3. **Replace** if the score is below 45 and exit difficulty is not High.
4. **Renegotiate** for everything else.

The order matters. A barely used, low-importance tool should be flagged for cancellation even if its security posture is excellent. And a poor score on a tool that is very hard to leave becomes Renegotiate, not Replace, because replacement is not a realistic plan this quarter.

Next to the recommendation, add a short "why" column that says which rule fired. People trust a recommendation they can read.

## A worked example

Two invented contracts, scored with the weights and rules above, as of November 2, 2026.

**Contract 1: a CRM.** Annual cost $48,000. Renewal date March 31, 2027. Notice period 60 days, auto-renews. 120 seats licensed, 78 active. Criticality High. SSO Yes, MFA Enforced, SOC 2 Type II, SBOM Unknown, no known breaches. Exit difficulty High. Renewal quote: 8% increase.

- Notice deadline: March 31, 2027 minus 60 days is January 30, 2027, which is 89 days away. It sits in the 61 to 90 day window, so it belongs on this quarter's agenda.
- Effective usage: 78 / 120 = 65%. Cost per active user: $48,000 / 78 = about $615. Estimated waste: $48,000 × 35% = $16,800. Next-year cost: $51,840.
- Scores: usage 65, criticality 75, security (100 + 100 + 100 + 25 + 100) / 5 = 85, price 100 × (1 − 0.08 / 0.20) = 60.
- Weighted score: (65 × 35 + 75 × 25 + 85 × 25 + 60 × 15) / 100 = 71.75.
- Recommendation: the score clears 70, but the 8% increase is above the 5% limit, so Renew does not apply. Renegotiate.

The evidence for that negotiation is already in the row: 42 unused seats, about $16,800 of estimated waste, and a quote that adds $3,840. A reasonable ask is a true-down toward the active count and a price cap, agreed before January 30.

**Contract 2: a survey tool.** Annual cost $6,000. 40 seats, 6 active, so usage is 15%. Criticality Low. The Cancel rule fires first, whatever the other scores say. The meeting's only question is whether the six people who use it have somewhere else to go, and who sends the notice.

## Running it every quarter

A tracker that is updated once a year is a historical document. A quarterly rhythm is enough for most companies:

- A week before, the owner of the sheet refreshes active users from each admin console and asks contract owners for any new quotes.
- Set a fixed as-of date for the meeting so everyone sees the same day counts, instead of `TODAY()` shifting while people read.
- In the meeting, work by deadline first, then by recommendation: anything in the notice-passed or next-30-days window, then Cancel and Replace, then Renegotiate, then a quick confirmation of the Renews.
- Record the outcome in two input columns, *Our decision* and *Decision owner*. Where the decision differs from the recommendation, write one line saying why. That line is what the next review needs.
- Put a calendar reminder 30 days before every notice deadline in the next 90 days, in the decision owner's calendar, not the spreadsheet owner's.

For the conversation with the vendor itself, the [90-day SaaS renewal checklist](https://circuits.fit/guides/how-to-read-a-saas-renewal.html) covers what to pull at each stage, and the free [software renewal scorecard](https://circuits.fit/tools/software-renewal-scorecard.html) scores a single contract in the browser.

## Common mistakes

- **Sorting by renewal date.** The renewal date is when the money moves. The notice deadline is when the decision is locked. Sort and filter by the deadline.
- **Typing the deadline by hand.** It goes stale the first time someone corrects a renewal date or notice period.
- **Treating a blank notice period as zero.** It hides exactly the contracts nobody has read yet.
- **Using the billing portal's date.** Portals often show the next invoice date, which is not always the term end in the order form.
- **Counting provisioned accounts as users.** An account that has not signed in for a quarter is a cost, not a user.
- **Letting the score decide.** The score sorts the agenda. A person still makes the call and writes it down.
- **A team as owner.** "IT" never sends the cancellation notice. A named person does.
- **One row per vendor.** Separate order forms have separate deadlines.

## FAQ

### How many contracts does a spreadsheet handle before we need software for this?

A spreadsheet works well into the hundreds of rows if the inputs are disciplined. The limit is usually not size but upkeep: if nobody refreshes usage each quarter, a dedicated tool will not fix that either.

### What if a contract has no notice period?

Enter 0, deliberately, so the sheet can tell it apart from a blank. The deadline then equals the renewal date.

### Should monthly subscriptions go in the tracker?

Yes, with annualized cost, so they sort by real exposure. They rarely carry notice risk, but they often carry waste.

### Who should own the sheet?

Usually finance, because finance sees every invoice. Each row still needs a contract owner outside finance who knows whether the tool is used.

A written review of up to 25 renewals is described on the Renewal Audit page: https://circuits.fit/services/renewal-audit.html
