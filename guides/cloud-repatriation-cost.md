Source: this is a Markdown copy of the free page at https://circuits.fit/guides/cloud-repatriation-cost.html.

# When cloud repatriation is a finance decision, not an engineering slogan

Steady-state workloads need a unit cost, not a burst story. Run the comparison with egress, people, and the feature you will not get — or keep arguing about the invoice.

## Who this is for

The U.S. mid-market CFO who wants the bill to mean something, and the operator who will have to staff “home” if finance says the word repatriation.

The cloud argument of the 2010s was elasticity. The cloud argument of the mid-2020s is the invoice. Workloads that run every hour of the quarter do not need a burst story. They need a unit cost. When that unit cost is higher than a colo row plus a small platform team, finance starts using the word “repatriation.” That is a matching problem, not a morality play.

Some products still belong on the public cloud: spiky demand, a global edge, a managed store you do not want to staff. Others were lifted and shifted in a hurry and never earned their keep. This page is how a mid-market shop decides which is which without inventing a calculator that pretends to know your discount.

## Cost drivers that actually move the bill

Compute and storage are the lines everyone can see. The damage usually sits next to them.

- **Egress and data gravity.** Getting data in is cheap. Getting it out is a toll. AWS’s published on-demand transfer table still prices the first 10 TB per month of internet egress from EC2 at $0.09 per GB after a small free tier, then steps down. That is list, not your EDP.
- **Cross-AZ and cross-region chatter.** A chatty database that copies itself for “high availability” can look cheap until you price the copies as a product.
- **Managed-service multipliers.** RDS, warehouse, and similar services buy you staffing you do not have. They also hide a premium you only see when you compare to a box you would have to run.
- **Commitments you cannot unwind.** Reserved instances and savings plans that outrun actual use are a tax you already signed. Moving a workload does not erase the commit.
- **People.** A company that outsourced operations cannot “bring it home” without hiring. Hiring is slower than a board slide.

If you cannot attach the top twenty lines to a service, a team, and a product, you are not ready to move anything. You are ready to argue.

## FinOps questions before anyone buys a rack

FinOps that only produces dashboards is theater. FinOps that can attach a cost to a SKU can choose.

1. Which workloads run above a high, steady utilization most hours of the quarter — and which only look expensive because they are on-demand by habit?
2. What share of the bill is untagged, and who is allowed to launch an untagged resource?
3. What is the fully loaded twelve-month cloud number: list minus real discounts, plus support, plus the commit you will still pay if you leave?
4. What is the fully loaded “home” number: colo or owned row, hardware, power, software, and the platform people you do not have yet?
5. What feature disappears if you leave — global backbone, managed failover, a region you cannot staff — and is that a product risk or a rounding error?
6. If two people resign in the first year, does the savings still exist?

> Repatriation without an ownership model is just a more expensive outage.

## When staying versus leaving makes sense

| Signal | Lean stay | Lean leave (or hybrid) |
| --- | --- | --- |
| Demand | Spiky, global, unknown | Steady, local, known for four quarters |
| Data | Small, or already at the edge | Heavy gravity, clumsy egress, batch that never bursts |
| Staff | No platform team, and no plan to hire one | Named owners who have run a row before |
| Commit | Leaving would strand a savings plan you still owe | The commit is already a bad fit and the workload is separable |
| Product risk | You need a region or failover you will not build | The missing managed feature is a nice-to-have |

The usual candidates to come home are batch analytics, predictable inference, and stateful systems that were never elastic. Customer-facing apps with a global edge usually stay. Hybrid is the real destination for most mid-market shops: reserved cloud for the bursty surface, owned or colo capacity for the furnace.

Staff the platform team first. Migrate a boring workload second. Only then hold a quote. If the savings only appear if nobody leaves the company, the savings are fictional.

## Labeled list-price example

**This is not your bill.** It is a published list-price illustration so egress is not a vibe.

AWS’s public on-demand table (U.S. regions, internet egress from EC2, after the small monthly free tier) still lists $0.09 per GB for the first 10 TB in a month. Ten terabytes is 10,240 GB. 10,240 × $0.09 is $921.60 at list, before NAT gateways, cross-AZ traffic, CloudFront, or any discount you actually have.

Use that only as a scale check: if your architecture ships terabytes out every month, the toll is a product decision. Pull your own invoice lines. Do not run a spreadsheet that pretends a blog’s $900 is your number.

## Sources

- [AWS EC2 on-demand pricing, data transfer](https://aws.amazon.com/ec2/pricing/on-demand/) (list prices; not a quote)
