Source: this is a Markdown copy of the free page at https://circuits.fit/tools/ai-cost-per-task.html.

# AI model cost per finished task

Compare list price with the cost of a task that actually finishes, and the daily volume where self-hosting beats the API.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

Attempts per task = 1 + average retries. Token cost uses each attempt. Review cost applies to the share of tasks that fail. Cost per successful task divides that total by the success rate. Listed cost is one attempt, before retries, failures, and review. A month in the break-even chart is 30 days. You type the prices. This page does not call a model.

## How to use this

1. Replace the two example models with the prices and token counts you were quoted. Add a third or fourth if you have them.
2. Use the success rate and retries you actually see. A low list price can lose once failed tasks and review time are in the cost.
3. Fill the self-host lines to see the daily token volume where the server costs less than the API, and whether your throughput reaches it.

## What this calculator does

AI model prices are quoted per million tokens. That number is easy to compare and often misleading. A cheaper model that fails more often needs retries, and failed tasks need a person to fix them. This page converts list prices into the cost of a task that actually finishes, including retries and human review. It also shows the daily token volume at which running your own server would cost less than paying per token through an API.

## The math, in plain English

- **Cost of one attempt** = input tokens ÷ 1,000,000 × input price + output tokens ÷ 1,000,000 × output price.
- **Attempts per task** = 1 + average retries.
- **Review cost** = share of tasks that fail × review minutes ÷ 60 × hourly rate.
- **Cost per finished task** = (attempt cost × attempts + review cost) ÷ success rate.
- **Self-host monthly cost** = server cost + ops hours × ops hourly rate. Break-even daily tokens = monthly self-host cost ÷ 30 ÷ API price per token.

## Worked example

The page loads with two example models. The prices are example numbers for illustration, not quotes from any provider.

**Example: low list price.** $0.50 per million input tokens, $2 per million output tokens, 2,000 input and 800 output tokens per attempt. One attempt costs about $0.0026. But it succeeds 60% of the time, averages two retries, and each failure takes 15 minutes of review at $80 an hour. Cost per finished task: about **$13.35**.

**Example: higher list price.** $3 input and $15 output per million tokens, 1,500 input and 400 output tokens. One attempt costs about $0.01. It succeeds 95% of the time with no retries, and failures take 10 minutes of review. Cost per finished task: about **$0.71**.

The model that is roughly four times cheaper per attempt is almost nineteen times more expensive per finished task. Almost all of the difference is human review on failed work, not tokens.

For self-hosting, the example uses a $4,000 monthly server, 10 ops hours at $90, and a blended API price of $8 per million tokens. Monthly self-host cost is $4,900. Break-even is about 20.4 million tokens a day. The example server can carry 50 million a day, so above about 20.4 million daily tokens, self-hosting would cost less in this example.

## Where to get your inputs

1. **Prices.** From your provider’s current pricing page or your contract. Providers such as Anthropic publish per-token prices, and they change. Check the date.
2. **Token counts.** From your API usage logs, averaged over a real sample of the task, not a demo prompt.
3. **Success rate and retries.** From a test set of at least a few dozen real tasks, judged by the person who owns the output.
4. **Review minutes.** Time a reviewer fixing failed outputs. Do not guess.

## How to read the result

If review cost dominates, improving quality is worth more than finding a cheaper model. If token cost dominates and quality is equal, list price matters. If your daily volume is far below break-even, self-hosting adds risk without saving money. If it is above break-even but beyond the server’s throughput, you need more hardware and the math changes.

## Limitations

- The page does not call any model or fetch prices. You type them.
- It treats every failure as needing review. Some failures are caught and discarded automatically.
- The self-host line ignores hardware depreciation schedules, power, and the cost of staff turnover. Treat it as a first screen. The [cloud repatriation note](https://circuits.fit/articles/cloud-repatriation.html) lists the fuller comparison.
- Batch discounts, cached-input pricing, and committed-use contracts can change the per-token price. Use the price you actually pay.

## FAQ

### Are my numbers saved or sent?

They stay in your browser. Nothing is uploaded.

### What success rate should I use?

The rate at which a reviewer would accept the output without edits. Partial credit belongs in review minutes.

### How does this connect to gross margin?

Feed the cost per finished task into the [token cost to gross margin](https://circuits.fit/tools/token-cost-margin.html) calculator to see what it does to a product’s margin.

## Calculator template

A spreadsheet with these formulas is also available as a free download on the source page. Not legal, tax, insurance, or procurement advice.

### Cost per finished task

Cost of one attempt = (input tokens / 1,000,000 × input price) + (output tokens / 1,000,000 × output price).

Attempts = 1 + average retries.

Cost per started task = (attempts × cost of one attempt) + ((1 − success rate) × review minutes / 60 × hourly rate).

Cost per finished task = cost per started task / success rate.

| Model | Price per 1M input | Price per 1M output | Input tokens per attempt | Output tokens per attempt | Success rate % | Average retries | Review minutes on a failure | Review hourly rate | Cost of one attempt | Cost per started task | Cost per finished task | Cost per 1,000 started tasks |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Model A (example, cheaper list price) | 0.50 | 1.50 | 4000 | 600 | 70 | 1 | 6 | 60 |  |  |  |  |
| Model B (example) | 3 | 15 | 4000 | 600 | 95 | 0 | 6 | 60 |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |

### Self-host versus API break-even

A month is treated as 30 days.

Monthly self-host cost = monthly GPU or server cost + (ops hours per month × ops hourly rate).

Break-even tokens per day = monthly self-host cost × 1,000,000 / (API blended price per 1M tokens × 30).

If self-host throughput (tokens per day) is at least the break-even volume, the server can carry that volume; otherwise the API costs less at any volume the server can carry.

| Input | Your figure |
|---|---|
| Monthly GPU or server cost |  |
| Ops hours per month |  |
| Ops hourly rate |  |
| Self-host throughput, tokens per day |  |
| API blended price per 1M tokens |  |
| Monthly self-host cost |  |
| Break-even tokens per day |  |
| Server can carry break-even volume? |  |
