Source: this is a Markdown copy of the free page at https://circuits.fit/guides/ai-sbom-extra-questions.html.

# Extra questions for an AI bill of materials

The May 12, 2026 G7 and CISA note is an add-on, not a replacement. A model name with no components is not an ingredients list.

## Who this is for

The operator buying an AI feature inside a product, and the security reviewer who has to describe what that feature contains.

On May 12, 2026, CISA and G7 partners published minimum elements for a software bill of materials for AI. CISA says AI systems are software systems, so the AI list sits on top of the general SBOM elements. The guide is not exhaustive and not, by itself, a mandate. It is still the public list to point at.

## What the AI note adds

Use it when the product is a model, a copilot, or an agent, not only when the vendor’s engineers compiled a binary. Ask which pieces are the model, which are data or adapters, and which are ordinary application code. If the vendor cannot separate those, you cannot tell whether a later incident is in the model, the data, or the wrapper.

## Questions

- Will you provide the general 2026 SBOM and the AI supplement, as two labeled files or one file that clearly includes both?
- What is the model’s name and version, and who provides it if it is not yours?
- Which components can change without a new SBOM, and which cannot?
- Does the file include enough license information to show a component you are not allowed to ship to a customer?
- If you only embed a third-party model, whose SBOM covers the model, and whose covers your application?

## Why an AI product needs more than a normal SBOM

A traditional SBOM answers a narrow question: which software components, at which versions, are inside this product. That is enough to answer “are we exposed to this new vulnerability in a library?” An AI product adds parts that a component list does not describe well. The model may come from a third party. It may be fine-tuned with adapters. It may depend on datasets, prompt templates, and retrieval indexes that change without a new software release. If a problem shows up, you need to know which of those parts changed and who supplied it.

Two open formats already carry this kind of information. CycloneDX has a machine-learning bill of materials (ML-BOM) capability for describing models and datasets. SPDX 3.0 includes AI and dataset profiles. Asking for one of these formats gives the vendor a concrete target and gives you something your tools can read.

## How to run the request, step by step

1. **Identify the AI features in scope.** List every product feature that uses a model: assistants, summarizers, classifiers, agents. Include features switched on inside software you already pay for.
2. **Send the questions above in writing.** Ask for the general SBOM and the AI supplement together, so you can see how they line up.
3. **Ask for the format.** CycloneDX or SPDX, machine-readable. A PDF can be read by a person but not checked by a tool.
4. **Check the change rules.** Ask how you will be told when the model version, provider, or training data changes. A model swap can change behavior more than a code release.
5. **File the answers with the contract.** Note what the vendor declined to share and why. That record matters at the next renewal and after an incident.

## A worked example

This is an illustrative case, not a real vendor. A support platform adds an AI reply feature. The vendor sends its standard SBOM, which lists the web application’s open-source libraries. It does not mention the model. On follow-up, the vendor says the feature calls a third-party hosted model and uses a retrieval index built from your help-center articles.

What you now know: the vendor’s SBOM covers its application, the model provider’s documentation covers the model, and the retrieval index contains your own content. What you still need: the model name and version, the provider, how you will be notified of a model change, and whether your articles or tickets are used for anything other than retrieval. Those questions go into the renewal agenda. The [SBOM request pack](https://circuits.fit/tools/sbom-request-pack.html) drafts the email.

## What this does not solve

An AI SBOM lists parts. It does not tell you whether the model is accurate, fair, or safe for your use. For those questions, use a risk framework such as NIST’s AI Risk Management Framework and its Generative AI Profile, NIST AI 600-1. Treat the SBOM as the inventory and the risk review as the judgment. You need both.

## Before you sign off

- Every AI feature in the product is listed, including ones switched on by default.
- You have the model name, version, and provider, or a written reason why not.
- You know how you will hear about a model or provider change.
- The general SBOM and the AI supplement arrived in a machine-readable format.
- Anything the vendor declined to share is recorded with the contract, so the next renewal starts from the same list.

For the general SBOM request, see [Ask a vendor for an SBOM](https://circuits.fit/guides/ask-a-vendor-for-an-sbom.html). For what the agent inside the product can do, see [Limit what an agent can touch](https://circuits.fit/guides/limit-what-an-agent-can-touch.html).

## Sources

- [CISA, Software Bill of Materials for AI — Minimum Elements, May 12, 2026](https://www.cisa.gov/resources-tools/resources/software-bill-materials-ai-minimum-elements)
- [CISA, 2026 general SBOM minimum elements](https://www.cisa.gov/resources-tools/resources/2026-minimum-elements-software-bill-materials-sbom)
- [CycloneDX, Machine Learning Bill of Materials (ML-BOM)](https://cyclonedx.org/capabilities/mlbom/)
- [SPDX specifications, including SPDX 3.0 AI and dataset profiles](https://spdx.dev/use/specifications/)
- [NIST AI 600-1, Generative Artificial Intelligence Profile, July 2024](https://doi.org/10.6028/NIST.AI.600-1)
- [CISA, Software Bill of Materials](https://www.cisa.gov/sbom)
