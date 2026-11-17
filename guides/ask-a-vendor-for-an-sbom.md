Source: this is a Markdown copy of the free page at https://circuits.fit/guides/ask-a-vendor-for-an-sbom.html.

# Ask a vendor for an SBOM

CISA’s 2026 minimum elements apply to SaaS and AI software. Ask for the fields, the format, and the date. A slide is not a bill of materials.

## Who this is for

The person who signs a software renewal and the person who has to answer a customer security review.

CISA’s July 29, 2026 minimum elements apply to all software, including open source, AI software, and SaaS. They update the 2021 NTIA baseline. Use them as a procurement list, not as a claim that every vendor is legally required to send you one tomorrow.

## The fields

CISA’s release names four additions on top of the older baseline: component hash algorithm, component license, the name of the tool that generated the SBOM, and the context in which it was generated. Ask for those by name. Also ask for the component names and versions the document is built to carry. If a field is missing, the reply is incomplete against the 2026 list, even if the PDF looks thick.

## The ask

- Machine-readable, not only a PDF. Say CycloneDX or SPDX if you already consume one of those. If you do not, still refuse a screenshot.
- The generation date, and how often a new file is produced. A file from the year the product launched is a souvenir.
- Whether hosted software is in scope. CISA says SaaS is in scope for the minimum elements. “We are a cloud app” is not an answer.
- Who will send an updated file after a critical component changes, and on what clock.

## What fails

| Reply | Treat it as |
| --- | --- |
| “We are SOC 2” | A different document |
| A logo slide of “trusted components” | Not an SBOM |
| A list with no license and no hash algorithm | Short of the 2026 elements |
| “Legal will not share our ingredients” | A commercial position you can price |

## Why it is worth asking

An SBOM is a list of the components inside a piece of software. When a serious vulnerability is announced in a common library, the companies that can answer “do we use this, and where?” in an hour are the ones with SBOMs from their vendors. The rest send emails and wait. The NTIA’s 2021 minimum elements set the original baseline: supplier name, component name, version, other unique identifiers, dependency relationships, the author of the SBOM data, and a timestamp. CISA’s 2026 update builds on that list with the four additions above.

The SBOM is also a signal. CISA’s Secure by Demand guide, published with the FBI in August 2024, lists the SBOM among the artifacts a customer can collect to judge whether a vendor builds security into its products. A vendor that can produce one quickly usually has its build process under control.

## How to make the request, step by step

1. **Pick the products.** Start with software that is internet-facing, handles sensitive data, or runs with high privilege. You do not need SBOMs for everything on day one.
2. **Write the ask in the contract or renewal.** Name the 2026 minimum elements, the format (CycloneDX or SPDX), the update frequency, and the time to deliver a new file after a critical component change.
3. **Decide who receives it.** A named security contact, not a shared inbox nobody reads.
4. **Check the first file.** Open it with a tool or at least a text editor. Confirm it has versions, licenses, a hash algorithm, the generating tool, and a date.
5. **Use it once.** The next time a major library vulnerability is announced, search your SBOMs for it. That test tells you whether the files are worth keeping current.

## A worked example

Illustrative case. Your company renews a document management product. The order form now says: “Supplier will provide a machine-readable SBOM in CycloneDX or SPDX format meeting CISA’s 2026 minimum elements within 30 days of signature, an updated SBOM with each major release, and an updated SBOM within 10 business days of remediating a critical vulnerability in a third-party component.” The vendor agrees to the first two and pushes back on the third. You settle on 15 business days. That is a real improvement over no clause at all, and it is in the contract rather than in a sales email.

The [SBOM request pack](https://circuits.fit/tools/sbom-request-pack.html) builds this request, and the [software renewal scorecard](https://circuits.fit/tools/software-renewal-scorecard.html) counts a missing SBOM against the renewal.

## Limits to keep in mind

An SBOM shows what is inside, not whether each component is exploitable in that product. Pair it with the vendor’s vulnerability disclosure policy and, where available, statements on whether a given vulnerability affects the product. It also does not replace patching. It tells you where to look faster.

## Before you sign off

- The products in scope are listed, starting with internet-facing and high-privilege software.
- The contract names the 2026 minimum elements, a format, an update frequency, and a delivery clock after a critical fix.
- A named person receives the files and checks the first one.
- You have searched the files at least once for a real vulnerability.
- Refusals are recorded and priced into the renewal.

If the product includes a model or agent, add the questions in [Extra SBOM questions for AI products](https://circuits.fit/guides/ai-sbom-extra-questions.html).

## Sources

- [CISA, 2026 Minimum Elements for an SBOM](https://www.cisa.gov/resources-tools/resources/2026-minimum-elements-software-bill-materials-sbom)
- [CISA news release, July 29, 2026](https://www.cisa.gov/news-events/news/cisa-and-partners-unveil-updated-software-bill-materials-resource-improves-transparency-security-and)
- [CISA SBOM overview](https://www.cisa.gov/sbom)
- [NTIA, The Minimum Elements for a Software Bill of Materials, July 2021](https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom)
- [CISA and FBI, Secure by Demand Guide, August 2024](https://www.cisa.gov/resources-tools/resources/secure-demand-guide)
- [CycloneDX project](https://cyclonedx.org/capabilities/mlbom/)
- [SPDX specifications](https://spdx.dev/use/specifications/)
