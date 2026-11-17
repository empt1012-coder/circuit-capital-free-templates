Source: this is a Markdown copy of the free page at https://circuits.fit/tools/vendor-claim-checker.html.

# Vendor claim checker

Separate a speed or savings claim from the bill.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

The pasted claim stays a claim. A vendor comparison is not the fact. If you enter volume and unit price, your cost is your arithmetic. It is printed next to the claim. It does not confirm the claim. If the figure belongs to NVIDIA, Gartner, CISA, or the vendor, the “whose number” line says so.

## Why check a vendor claim

“Up to 8x faster.” “Cuts costs by 40%.” A vendor benchmark is a useful signal, but it is the vendor’s measurement, on the vendor’s workload, against a baseline the vendor chose. It is not a measurement of your bill. This tool turns a claim into a short note for the buying file: whose number it is, what it did not measure, what the bill is at your volume, and three questions for the next call.

## How to use this

1. Paste the claim exactly as the vendor wrote it, and name the vendor and product.
2. Say who measured it (vendor, analyst, another customer or unknown) and what the metric is.
3. Say whether the claim names a baseline (faster than what?) and a price source (which meter, at what price?).
4. Optionally enter your own volume and unit price. The page multiplies them so your bill sits next to the claim.
5. Fill in the checklist below and paste it into the evaluation or renewal record.

## Worked example

A vendor announces a fast mode with “up to 8x faster token generation than our standard mode.” This is the kind of claim covered in [Astra Ultrafast is a speed claim](https://circuits.fit/articles/astra-ultrafast-is-a-speed-claim.html). You enter: measured by the vendor; metric, tokens per second; baseline named, yes (the standard mode); price source named, no. You expect 30 million tokens a month at a unit price of 12 dollars per million.

The note says the number is the vendor’s comparison, not the fact. Under “what was not measured” it lists two gaps: no price source is named, and the comparison was not run on your volume. It prints your arithmetic, 30 × 12 = 360, in the units you typed, and says that does not confirm the claim. The three questions are: walk the baseline (what was held constant?), show where the price is and which meter it covers, and say what the claim does at your volume of 30. That is a better agenda than “is it really 8x?”

## Assumptions and limits

- The page does not test the product or look anything up. It structures what you entered.
- The bill line is volume times unit price in whatever units you type. Keep them consistent.
- A named baseline and price source do not make a claim true. They make it checkable.
- On the source page, nothing you type leaves the browser.

## Questions readers ask

### What if an analyst published the number?

Choose Analyst. The note says it is the analyst’s number, not a measurement on your workload. Read the analyst’s release for the sample and the date before you rely on it.

### Can I use this for security claims?

It is built for performance and cost claims. For a supplier’s security assurances, ask for dated evidence instead: the patch date, the version, and who confirmed it. The [SBOM request pack](https://circuits.fit/tools/sbom-request-pack.html) covers component lists.

## Template

Use one copy per claim, for example "up to 8x faster" or "cuts costs 40%".

## The claim
- Vendor:
- Product:
- Exact wording of the claim (quote it):
- Where it appeared (link, deck page, date):

## Whose number is it
- [ ] Who measured it: the vendor, a named third party, or a customer?
- [ ] What metric: speed, cost, accuracy, time saved?
- [ ] Baseline named: faster or cheaper than what, exactly?
- [ ] Price source named: list price, discounted price, or "contact sales"?
- [ ] Test conditions given: workload, volume, hardware, date?

## Your bill
- Your monthly volume:
- Your unit price:
- Monthly cost at your volume (volume x unit price):
- Gap between the claim's conditions and yours:

## Three questions to send the vendor
1. Who ran the measurement behind this claim, and can we see the method and date?
2. What is the baseline, and does it match what we run today?
3. What would this cost at our volume, at the price in our contract, in writing?

## Decision
- [ ] Claim verified with evidence
- [ ] Claim unverified: do not use it in the business case
- Owner: ____  Date: ____
