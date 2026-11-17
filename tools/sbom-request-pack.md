Source: this is a Markdown copy of the free page at https://circuits.fit/tools/sbom-request-pack.html.

# SBOM request pack

Ask a vendor for an ingredients list, then mark what came back.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

The email asks for the 2026 CISA minimum elements, including for SaaS and AI software, not only code the buyer compiles. The field list below is the ask. Tick Received when a field comes back. Missing rows stay on the page.

## Why ask for an SBOM

A software bill of materials is an ingredients list for software: which components a product contains, who supplies them, which versions are inside, and how they depend on each other. When a component turns up on CISA’s Known Exploited Vulnerabilities catalog, the buyer with an SBOM can answer “are we affected?” in minutes. The buyer without one sends a questionnaire and waits.

On July 29, 2026, CISA, the NSA, the FBI and international partners published the *2026 Minimum Elements for a Software Bill of Materials*. It replaces the minimum elements the National Telecommunications and Information Administration published in 2021. CISA says the minimum elements apply to all software, and that some types, including AI and software as a service, may need additional elements. That matters for buyers: “we are SaaS, so an SBOM does not apply” is no longer the answer the guidance supports.

## How to use this

1. Enter the vendor, the product and your name, and say whether you are buying SaaS, installed software or an AI feature.
2. Use the email template below. It asks for each field on the list. Copy it into your own email or procurement portal.
3. When the vendor replies, tick **Received** for each field that actually came back. Anything left unticked stays marked Missing. Put the missing rows on the renewal agenda.

## Worked example

A finance team is renewing an expense-management SaaS product. The buyer enters the vendor and product, chooses SaaS, and sends the request. Two weeks later the vendor returns a spreadsheet with component names, versions and licenses, plus a note that it “monitors vulnerabilities continuously.” The buyer ticks Component name, Version and License. Supplier name, Unique identifier, Dependency relationship, Author of SBOM data, Timestamp and Known vulnerabilities stay Missing.

That result is useful on its own. Without unique identifiers, the list cannot be matched reliably against vulnerability databases. Without a timestamp, nobody knows whether it describes the product running today. Without dependency relationships, an exploited library buried two levels down will not show up. The six missing fields become six lines in the renewal call, and the [software renewal scorecard](https://circuits.fit/tools/software-renewal-scorecard.html) scores the SBOM answer alongside price caps and data export.

## Assumptions and limits

- The field list is our working list drawn from the minimum-elements guidance. Check the CISA document for the exact element names and definitions before you put them in a contract.
- The page does not read or validate an SBOM file. It tracks whether each field came back.
- A received field is only as good as the data in it. A stale SBOM can be worse than none if it gives false comfort, so ask how often it is regenerated.
- On the source page, nothing you type leaves the browser.

## Questions readers ask

### Will a small vendor be able to answer?

Many build tools can generate an SBOM automatically. A vendor that cannot produce one at all is telling you something about how it tracks its own components.

### What about AI features?

Ask the AI-specific questions in the guide [Extra questions for an AI bill of materials](https://circuits.fit/guides/ai-sbom-extra-questions.html), which covers the May 12, 2026 G7 and CISA note.

## Template

Fields follow the 2026 Minimum Elements for a Software Bill of Materials, published July 29, 2026 by CISA, the NSA, the FBI and international partners. CISA says the minimum elements apply to all software, including SaaS and AI, which may need additional elements. Check the CISA document for exact definitions.

## Before you send
- [ ] Vendor and product named exactly as on the contract
- [ ] Delivery model noted: SaaS, installed software, or AI feature
- [ ] Contract owner and security contact identified
- [ ] Renewal date and notice deadline checked (an SBOM ask carries more weight before the notice deadline)

## Email template

To: [Vendor]
Subject: SBOM request for [Product]

We are buying [Product] ([SaaS / installed software / AI feature]).
Please send an ingredients list that meets the 2026 CISA minimum elements, including for SaaS and AI software, not only code we compile.

For each component, include:
- Supplier name
- Component name
- Version
- Unique identifier
- Component hash, with the name of the hash algorithm used
- Dependency relationship
- License
- Known vulnerabilities

For the SBOM itself, include:
- Author of the SBOM data
- Timestamp
- SBOM tool name: the tool that generated it
- SBOM generation context: when and how in the software lifecycle the SBOM was generated

A logo slide is not an ingredients list.

[Your name]

## What came back (mark Received or Missing)

| Field | Received / Missing | Notes |
|---|---|---|
| Supplier name | | |
| Component name | | |
| Version | | |
| Unique identifier | | |
| Component hash and hash algorithm | | |
| Dependency relationship | | |
| Author of SBOM data | | |
| Timestamp | | |
| SBOM tool name | | |
| SBOM generation context | | |
| License | | |
| Known vulnerabilities | | |

## Tracking across vendors

| Vendor | Product | Model | Date asked | Date received | Fields missing | Follow-up owner | Follow-up date |
|---|---|---|---|---|---|---|---|
| | | | | | | | |
