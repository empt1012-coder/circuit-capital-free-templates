Source: this is a Markdown copy of the free page at https://circuits.fit/guides/how-to-read-a-saas-renewal.html.

# How to read a SaaS renewal

The invoice is not the brief. Pull usage, overlap, and the exit clause before you answer the 8% increase.

## Who this is for

The operator who owns the tool, the CFO who signs the increase, and anyone who has to explain why two products still do the same job.

Most renewals fail in month eleven because nobody owns month nine. The vendor sends a quote. Finance asks if you still need it. You say yes because last quarter’s outage is still in memory. That is how overlapping CRMs survive.

Use this as a 90-day pass. Print it. Put a name next to each line.

## 90 days out

- Export active seats and last-login dates. A seat that has not signed in for 90 days is not a user. It is a tax.
- List every other tool that does 30% of the same job. If two products share a workflow, one of them is on trial at renewal, whether the vendor knows it or not.
- Find the termination and data-export clauses. If export needs a services ticket, price that ticket now.

## 60 days out

Write one paragraph: what work dies if this tool is down for a day, who can add a seat, and what you would switch to. If you cannot write it, you do not have an owner.

Ask the vendor for the renewal in writing with unit price, volume, and any auto-increase. Verbal “we will take care of you” is not a term.

> A renewal without a kill list is a subscription you already lost.

## 30 days out

| Check | Pass | Fail |
| --- | --- | --- |
| Unused seats | True-down before the quote locks | Paying for last-login ghosts |
| “Standard” increase | The clause is in the paper | The increase is a habit |
| Stay / shrink / leave | Finance and the operator in one meeting | A Slack poll after the invoice |

## The only metric

Did this tool retire hours, tickets, or another license? If the answer is a vibe, you are buying a logo. Keep the tool that has a before-and-after number. Cut the one that only has a champion.

## Sources

- [CISA and FBI, Secure by Demand Guide, August 2024](https://www.cisa.gov/resources-tools/resources/secure-demand-guide)
- [Regulation (EU) 2023/2854, the Data Act, on EUR-Lex](https://eur-lex.europa.eu/eli/reg/2023/2854/oj)
- [FinOps Foundation, FinOps Framework](https://www.finops.org/framework/)

## The contract terms that matter most

Most renewal leverage comes from a short list of clauses. Find each one in the order form or master agreement before the first vendor call.

- **Renewal date and notice period.** Many SaaS contracts renew automatically unless you give notice 30, 60, or 90 days ahead. Miss the window and you negotiate from a weaker position.
- **Price increase terms.** Look for a cap on renewal increases. If there is none, ask for one. A cap is a common, reasonable request.
- **Seat true-down.** Can you reduce seats at renewal, or only add them? Some contracts allow only increases. Fix that at renewal.
- **Data export and return.** Can you export all of your data in a usable format, and how long does the vendor keep it after termination?
- **AI and data-use terms.** Many products have added AI features. Check whether new terms allow the vendor to use your data for training, and whether that is opt-in or opt-out.
- **Security artifacts.** CISA’s Secure by Demand guide suggests asking whether SSO and security logging are in the base product, and whether the vendor can provide an SBOM. Renewal is when you can ask.

## A worked example

Example numbers, not survey data. A team pays $48,000 a year for 120 seats. Usage shows 66 active users in the last 30 days, or 55%. The vendor proposes an 8% increase, to $51,840 for the same 120 seats. At 90 days out, the owner checks a 90-day usage view and finds 72 regular users, so proposes 80 seats to allow for growth. At the current per-seat price of $400, 80 seats cost $32,000. Even if the 8% increase is accepted on the smaller count, the new cost is $34,560, about $17,000 below the vendor’s proposal. The owner also asks for a 5% cap on future increases and a 30-day data-return window. The [software renewal scorecard](https://circuits.fit/tools/software-renewal-scorecard.html) produces this agenda from the same inputs.

## Common mistakes

- **Negotiating only price.** Terms like caps, true-downs, and exit rights often matter more over three years than a one-time discount.
- **Letting the vendor set the timeline.** End-of-quarter pressure is the vendor’s deadline, not yours.
- **Skipping the exit test.** If you have never exported your data, you do not know whether you can leave.
- **Ignoring overlap.** Check whether another tool you own does the same job. Overlap is the easiest saving.

## A note for EU workloads

The EU Data Act has applied since September 12, 2025. For data processing services, which can include SaaS, it sets rules on switching providers and ends switching charges from January 12, 2027. If your vendor serves you in the EU, ask how its exit terms reflect that. This is a question for counsel, not a conclusion.

## Before you sign off

- The renewal date and notice deadline are on the owner’s calendar.
- Usage is pulled for 30 and 90 days.
- The price cap, true-down, export, data-return, and AI terms are found and noted.
- The stay, shrink, or leave meeting has the signer, the user, and the person who would run the export.

A written review of up to 25 renewals is described on the Renewal Audit page: https://circuits.fit/services/renewal-audit.html
