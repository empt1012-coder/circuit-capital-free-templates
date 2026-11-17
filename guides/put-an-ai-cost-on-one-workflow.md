Source: this is a Markdown copy of the free page at https://circuits.fit/guides/put-an-ai-cost-on-one-workflow.html.

# Put an AI cost on one workflow

One process, one owner, 90 days. Measure token spend, review time and rework against a baseline, and finish with a unit cost you can defend.

## Who this is for

The founder or operator who owns one process. This page prices that workflow. Seat cost versus return, and questions a board can ask, are in [How to tell AI spend from AI return](https://circuits.fit/guides/ai-spend-vs-return.html).

## Which guide do you need?

- **Reviewing the whole AI budget**, every license, usage bill and pilot, before a board or budget meeting: [AI budget review: how to tell AI spend from AI return](https://circuits.fit/guides/ai-spend-vs-return.html).
- **Costing one process** you own, with a baseline, token spend, review time and rework over 90 days: [Put an AI cost on one workflow](https://circuits.fit/guides/put-an-ai-cost-on-one-workflow.html).

This guide is about one process, not the AI budget. Pick a workflow with a finish line, measure it before and after, and end with a cost per finished unit. The reason to start that small: McKinsey’s 2026 survey, as reported in September, still had only 37% of respondents attributing any EBIT to AI, and about 6% as high performers. Individual productivity is not the same as a cheaper close. This guide is how to stop mixing those two.

## Pick a workflow with a finish line

Good: monthly close commentary, support macros, bid/no-bid memos, invoice exceptions. Bad: “make the company more AI-native.” If you cannot name the artifact that is done, you cannot measure time or cost.

Write the current path: who starts it, how long it takes, where it fails, what “done” looks like. That is your baseline. No baseline, no after.

## Instrument three costs

- **License or token spend** for that workflow only — not the company-wide copilot bill.
- **Human review time** after the model drafts. Review is the cost that hides in “we saved time.”
- **Rework** when the draft invents a date, a customer, or a covenant.

> If the only metric is seats, the organization will buy seats.

## 90 days, one owner

| Cost | Count this | Do not count this |
| --- | --- | --- |
| Tokens or license | Spend on this workflow | The company-wide copilot bill |
| Review | Minutes after the draft | “We feel faster” |
| Rework | Invented dates, names, covenants | A demo that went well |

Name a manager whose bonus includes cycle time or error rate for that workflow. Put the date on the calendar now. Gartner said in September that only 22% of organizations had scaled AI across multiple business units. You do not need to be in the 22%. You need one number that moved.

If nothing moved, cut the overlapping copilots and keep the model on the one path that has an owner. That is not anti-AI. It is how you keep the next Gartner-sized invoice from becoming the strategy.

## A worked example

Example numbers for illustration, not survey data. A finance team writes monthly variance commentary. Today it takes an analyst 6 hours a month at a loaded cost of $80 an hour: $480. The team pilots a model that drafts the commentary.

- **Token cost.** About 40 drafts a month across business units. At the prices and token counts the team measured, about $0.70 per draft including retries: $28.
- **Review.** The analyst spends 2.5 hours reviewing and editing: $200.
- **Rework.** Twice a month, a draft cites the wrong period or invents a driver. Fixing and checking those takes 1 hour: $80.

New monthly cost: $308, against a $480 baseline. A saving of $172 a month, or about 36%. That is real, and much smaller than the “six hours saved” the demo implied. The [cost per finished task calculator](https://circuits.fit/tools/ai-cost-per-task.html) does the token and review math. The [token cost to gross margin](https://circuits.fit/tools/token-cost-margin.html) tool shows the effect on a product.

## How to measure, step by step

1. **Record a baseline for two cycles.** Time and errors before the model. Without it, you cannot show a change.
2. **Tag spend to the workflow.** Use a separate API key, project, or cost tag so the tokens for this workflow are not mixed into the company total. The FinOps Foundation’s material on AI costs covers allocation methods.
3. **Time review honestly.** Ask the reviewer to log minutes for a few weeks.
4. **Count rework.** Keep a simple tally of drafts that needed substantial correction, and why.
5. **Compare after 90 days.** Report cost, cycle time, and error rate against the baseline. Decide: expand, adjust, or stop.

## Reading a price list

Model providers publish per-token prices, usually separate prices for input and output tokens, and sometimes discounts for batch processing or cached input. Anthropic’s pricing page is one example. Prices change, so record the date and the price you actually pay. Output tokens often cost several times more than input tokens, so a workflow that writes long drafts costs more than one that classifies short items.

## Common mistakes

- Counting the company-wide license as the workflow’s cost, which makes small pilots look expensive and large rollouts look free.
- Leaving out review time.
- Measuring for one week. Month-end and quarter-end workflows need at least two cycles.

## Before you sign off

- One workflow, one owner, and a finished artifact you can count.
- A baseline from at least two cycles before the model.
- Spend tagged to this workflow only.
- Review minutes and rework tracked, not estimated.
- A 90-day decision date on the calendar.

## Sources

- [Gartner AI spending forecast, May 19, 2026](https://www.gartner.com/en/newsroom/press-releases/2026-05-19-gartner-forecasts-worldwide-ai-spending-to-grow-47-percent-in-2026)
- [Gartner scaling survey, Sept. 1, 2026](https://www.gartner.com/en/newsroom/press-releases/gartner-survey-finds-only-22-percent-of-organizations-have-successfully-scaled-ai-across-multiple-business-units)
- [McKinsey State of AI 2026](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)
- [FinOps Foundation, FinOps for AI overview](https://www.finops.org/wg/finops-for-ai-overview/)
- [Anthropic, pricing](https://www.anthropic.com/pricing): an example of a published per-token price list
