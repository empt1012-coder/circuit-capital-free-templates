Source: this is a Markdown copy of the free page at https://circuits.fit/tools/software-renewal-scorecard.html.

# Software renewal scorecard

Decide keep, renegotiate, or replace before a renewal call.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

Each gap has a fixed score. Seat use under 60% of paid seats, no price-up cap or an unknown cap, notice under 30 days, no full export, no SBOM, unknown AI training use, and no exit clause score 2. A named cap, including 0%, scores 0. Unknown export, SBOM, subprocessors or exit clause, and opt-out training, score 1. A data-return window under 30 days scores 1. Unlisted subprocessors score 2. Seats paid, seats active, notice period, data-return window and the cap question are required: if any is blank or invalid, the result is Incomplete, not Keep. 0 points is Keep. 1 to 7 is Renegotiate. 8 or more is Replace. No full export and no exit clause is Replace even when the total is lower.

## What this scorecard does

A software renewal is the one moment each year when the buyer has leverage. Before you sign, the vendor wants the deal. After you sign, the terms are fixed for another term. This scorecard turns the contract and usage facts you already have into a single decision, Keep, Renegotiate, or Replace, and a list of specific requests to send the vendor.

It does not judge whether the product is good. It checks whether the commercial and data terms protect you. A well-loved tool can still score Renegotiate if half the seats sit unused or there is no cap on the next price increase.

## How to use it, step by step

1. **Pull usage.** From the vendor’s admin console, export the number of seats you pay for and the number of users active in the last 30 days.
2. **Read the order form and master agreement.** Find the renewal price cap, the notice period to cancel or change, the data-return window after termination, and whether there is an exit or termination-for-convenience clause.
3. **Check the data terms.** Confirm whether you can export all of your data in a usable format, whether subprocessors are listed, and how the vendor uses your data for AI training.
4. **Ask for an SBOM.** If you do not know whether the vendor provides one, select Unknown and send the request. The [SBOM request pack](https://circuits.fit/tools/sbom-request-pack.html) drafts that email.
5. **Score it.** Use the scoring rules in the template below. Copy the result into your vendor email or the renewal ticket.

Start at least 90 days before the renewal date. Many contracts require 30 to 90 days’ notice to change terms, and the scorecard flags notice periods under 30 days because they leave no room to negotiate.

## Worked example

These are example numbers, not data from a real vendor. A team pays $48,000 a year for an example CRM with 120 paid seats. Only 66 users were active in the last 30 days. There is no price-up cap in the contract. The notice period is 60 days and the data-return window is 14 days. Full export is available, subprocessors are listed, and there is an exit clause. The vendor has not said whether it provides an SBOM, and AI training on customer data is opt-out.

The scorecard returns **Renegotiate with 7 points**:

- Seat use is 55%, under the 60% line: 2 points.
- No price-up cap: 2 points.
- Data-return window of 14 days, under 30: 1 point.
- SBOM unknown: 1 point.
- AI training is opt-out rather than opt-in: 1 point.

The agenda it writes asks the vendor to cut the renewal to active seats, add a price cap, extend the data-return window to at least 30 days, confirm SBOM availability, and move training to opt-in. Cutting to 75 seats at the same per-seat price would bring the example cost from $48,000 to $30,000.

## How to read the result

**Keep (0 points)** means none of the checks found a gap. Renew, and record the date you checked.

**Renegotiate (1 to 7 points)** is the most common result. Send the agenda. Most items are standard requests that vendors grant regularly, especially seat true-ups and price caps.

**Replace (8 or more, or no export and no exit clause)** means the terms leave you with little protection. That does not mean cancel tomorrow. It means start evaluating alternatives now, so you have a real option at the next renewal. A product you cannot export from and cannot exit is the one where the vendor sets the price.

## Limitations

- The points are fixed weights chosen by this desk. They are a starting rule, not an industry standard. Adjust your judgment for a tool that is critical to operations.
- Seat activity in the last 30 days can miss seasonal users, such as staff who only log in at quarter-end. Check a 90-day view before cutting.
- The scorecard does not read contracts. It relies on what you type. If a required field is blank, it returns Incomplete and names the missing field instead of a decision. If you do not know an answer, choose Unknown rather than guessing.
- It is not legal or procurement advice. Have counsel review contract changes.

## FAQ

### Is my data sent anywhere?

No. The scoring runs in your browser. Nothing is uploaded.

### Why does opt-out AI training score a point?

Opt-out means your data may be used unless someone remembers to switch it off. Opt-in means it is not used unless you agree. The guide [What belongs in a processor clause](https://circuits.fit/guides/what-belongs-in-a-processor-clause.html) covers the contract side.

### Why ask for an SBOM on a SaaS product?

CISA’s 2026 minimum elements for SBOMs say hosted software is in scope. See [Ask a vendor for an SBOM](https://circuits.fit/guides/ask-a-vendor-for-an-sbom.html).

### What if the vendor refuses every request?

Then you know the price of staying. Record it, and use the next term to build an alternative.

## Scorecard template

Use one row per product. A spreadsheet with these formulas is also available as a free download on the source page.

Scoring: 0 points = Keep, 1–7 = Renegotiate, 8+ = Replace. If there is no full export and no exit clause, the decision is Replace regardless of the total.

### Columns

| Column | What to enter |
|---|---|
| Product | Product name |
| Annual cost | Amount you pay per year |
| Seats paid | Seats on the contract |
| Seats active (30 days) | Seats used in the last 30 days |
| Price-up cap | Yes / No / Unknown |
| Cap % | The cap, if any. 0 means no increase is allowed. |
| Notice period (days) | Days of notice required |
| Data-return window (days) | Days you have to get data back |
| Can export all data | Yes / No / Unknown |
| SBOM on request | Yes / No / Unknown |
| AI training | Opt-in / Opt-out / Unknown / N/A |
| Subprocessors listed | Yes / No / Unknown |
| Exit clause | Yes / No / Unknown |

### How points are counted

- Seat use below 60%: 2 points
- No price-up cap (anything other than Yes): 2 points
- Notice period under 30 days: 2 points
- Data-return window under 30 days: 1 point
- Cannot export all data: 2 points; Unknown: 1 point
- No SBOM on request: 2 points; Unknown: 1 point
- AI training Unknown: 2 points; Opt-out: 1 point
- Subprocessors not listed: 2 points; Unknown: 1 point
- No exit clause: 2 points; Unknown: 1 point

Seat use % = seats active / seats paid.

Decision: Replace if export is No and exit clause is No. Otherwise Replace if points are 8 or more, Renegotiate if points are 1 to 7, Keep if points are 0.

### Blank rows

| Product | Annual cost | Seats paid | Seats active (30 days) | Price-up cap | Cap % | Notice period (days) | Data-return window (days) | Can export all data | SBOM on request | AI training | Subprocessors listed | Exit clause | Seat use % | Points | Decision |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| CRM A (example) | 48000 | 120 | 64 | No |  | 30 | 14 | Unknown | Unknown | Opt-out | Yes | No |  |  |  |
| Design tool B (example) | 9600 | 40 | 37 | Yes | 5 | 60 | 30 | Yes | Yes | Opt-in | Yes | Yes |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

A written review of up to 25 renewals is described on the Renewal Audit page: https://circuits.fit/services/renewal-audit.html
