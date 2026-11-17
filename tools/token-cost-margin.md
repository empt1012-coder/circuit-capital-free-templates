Source: this is a Markdown copy of the free page at https://circuits.fit/tools/token-cost-margin.html.

# Token cost to gross margin

See if an AI-native task still contributes after tokens and human review.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

Token cost = (input tokens / 1,000,000) × price per 1M input tokens + (output tokens / 1,000,000) × price per 1M output tokens. Review cost = (minutes / 60) × loaded cost per hour. Contribution = price charged − token cost − review cost. Margin = contribution / price charged. You type the prices. This page does not call a model.

## Why tokens are rarely the whole cost

AI-native products are often priced as if the model call were the main cost. In practice, many tasks also need a person to check, correct or approve the output before a customer sees it. That review time is usually priced in dollars per hour, not fractions of a cent per thousand tokens, and it can dominate the unit economics. This tool puts both costs on one line so you can see which one drives the margin.

## How to use this

1. Enter the price you charge per task and the average input and output tokens one task uses. Your model provider’s usage logs give the token counts.
2. Enter the provider’s price per million input tokens and per million output tokens from its current price list.
3. Enter the average human-review minutes per task and the loaded hourly cost of the reviewer, including benefits and overhead.
4. Optionally, add tasks per month to see the monthly contribution. The formulas are in the calculator template below.

## Worked example

These prices are illustrative, not any vendor’s list price. A company charges $2.00 per task. One task uses 6,000 input tokens and 1,500 output tokens. The model costs $3 per million input tokens and $15 per million output tokens. A reviewer spends three minutes per task at a loaded cost of $60 an hour, and the company runs 20,000 tasks a month.

Token cost is (6,000 ÷ 1,000,000) × $3 plus (1,500 ÷ 1,000,000) × $15, which is about $0.04. Review cost is (3 ÷ 60) × $60, or $3.00. Contribution is $2.00 − $0.04 − $3.00, a loss of about $1.04 per task, a margin of −52%, and about −$20,810 a month. Cut review to one minute and the same task contributes about $0.96, a 48% margin, or about $19,190 a month. The model price barely moved the answer. The review minutes decided it, which is why the tool prints “Human review costs more than the tokens” when that is true.

## Assumptions and limits

- Contribution here is price minus token cost minus review cost. It leaves out hosting, payment fees, support, retries, failed tasks and sales cost. Use the [AI cost per finished task](https://circuits.fit/tools/ai-cost-per-task.html) tool to account for retries and failures.
- The page does not call a model or look up prices. You type every number, in one currency.
- Averages hide spread. If a tenth of tasks need twenty minutes of review, run that case separately.

## Questions readers ask

### What if my provider raises prices?

Rerun with the new price. Gartner warned on October 14, 2026 that most neocloud providers may not stay independent through 2030; [our briefing](https://circuits.fit/articles/gartner-ai-infrastructure-impairment-neoclouds.html) explains why that is a pricing risk for buyers. Test a higher token price before you sign a long commitment.

### Should review time ever be zero?

Only where a wrong answer is cheap and reversible. For anything a customer relies on, budget some review and measure it.

## Calculator template

A spreadsheet with these formulas is also available as a free download on the source page. Not legal, tax, insurance, or procurement advice.

Token cost = (input tokens / 1,000,000 × input price) + (output tokens / 1,000,000 × output price).

Review cost = (human-review minutes / 60) × loaded hourly cost.

Contribution per task = price charged per task − token cost − review cost.

Margin % = contribution per task / price charged per task.

Monthly contribution = contribution per task × tasks per month (if you enter it).

| Task | Price charged per task | Input tokens | Output tokens | Price per 1M input tokens | Price per 1M output tokens | Human-review minutes | Loaded cost per hour | Tasks per month | Token cost | Review cost | Contribution per task | Margin % | Monthly contribution |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Support reply draft (example) | 1.50 | 6000 | 800 | 3 | 15 | 2 | 60 | 10000 |  |  |  |  |  |
| Contract summary (example) | 12 | 40000 | 3000 | 3 | 15 | 10 | 90 | 500 |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |
