Source: this is a Markdown copy of the free page at https://circuits.fit/guides/one-page-ai-use-rule.html.

# A one-page AI use rule

NIST’s AI RMF 1.0 is voluntary and organized as Govern, Map, Measure, and Manage. Use those four lines. Cite the version. A revision is in progress.

## Who this is for

A department that already has people pasting work into a model, and a manager who needs a rule shorter than a framework.

NIST released the AI Risk Management Framework 1.0 on January 26, 2023. It is voluntary. It is for organizations that design, develop, deploy, or use AI. The core is four functions: Govern, Map, Measure, and Manage. NIST’s AI Resource Center says a revision of 1.0 is in progress, and that the Generative AI Profile (NIST AI 600-1, July 26, 2024) is the profile for generative systems. Cite the document you actually used. Do not write “NIST compliant” on a one-pager.

## The four lines

- **Govern.** Who may turn a tool on, and who can turn it off. One name.
- **Map.** What the tool is allowed to see, and what decision it is allowed to shape. Customer data, source code, and health information are separate yes-or-no lines.
- **Measure.** What you will count so you know it worked: cycle time, error rate, or a review sample. “People like it” is not a measure.
- **Manage.** What happens when the output is wrong, and how a person overrides it. If there is no override, say so in the same paragraph that approves the tool.

## The page

Keep it to one page per tool, not one page for “AI.” Name the product, the owner, the data it may see, the decision it may not make alone, and the date you will look again. Link the NIST framework and, if the tool generates text or media, the generative profile, so a later reader can see you did not invent the four words.

## A sample one-page rule

The example below is a template, not legal advice. Edit it to match your tools and data.

| Section | Example wording |
| --- | --- |
| Approved tools | Staff may use the AI tools on the approved list, signed in with company accounts. Personal accounts are not allowed for company work. |
| Data you may not enter | Customer personal data, passwords and keys, unreleased financial results, and anything under a confidentiality agreement, unless the tool is approved for that data. |
| Checking output | A person reviews AI output before it is sent outside the company or used in a decision about a customer, employee, or payment. |
| Actions | AI tools may not send external messages, move money, or change access without a person approving each action. |
| Disclosure | Tell people when they are interacting with an AI system where law or contract requires it. |
| Owner and review | The rule has a named owner and is reviewed every six months. Date of this version: [date]. |

## How to roll it out, step by step

1. **List the tools people already use.** Ask, do not guess. Unapproved use is common when no rule exists.
2. **Decide the approved list.** Prefer tools with company accounts, admin controls, and clear data-use terms.
3. **Write the page.** Use the table above as a start. Keep it to one page so people read it.
4. **Train with examples.** Show two or three real cases from your work: what is fine, what is not.
5. **Review on a schedule.** Tools and laws change. Put the next review date on the page.

## How the page maps to the NIST framework

The NIST AI Risk Management Framework has four functions. A one-page rule touches each of them lightly. **Govern** is the owner and review date. **Map** is the list of tools and the data each may see. **Measure** is the output check. **Manage** is the action limits and what happens when someone breaks the rule. That is enough to start, and it gives you a structure to grow into. For agents that can take actions, add the controls in [Limit what an agent can touch](https://circuits.fit/guides/limit-what-an-agent-can-touch.html). For EU-facing features, the disclosure line connects to [What Article 50 asks a buyer](https://circuits.fit/guides/what-article-50-asks-a-buyer.html).

## Common mistakes

- Banning everything. People use personal accounts instead, and you lose visibility.
- Writing a ten-page policy. Nobody reads it, so nobody follows it.
- Forgetting AI features inside existing software. They count too.

## Before you sign off

- The approved tool list exists and staff know where it is.
- The data that must not go into AI tools is named in plain words.
- Output that leaves the company, or affects a person or a payment, is checked by a person.
- AI tools cannot take high-impact actions without approval.
- The page has an owner, a version date, and a next review date.
- Staff have seen two or three examples from their own work.

A rule is only useful if people can find it when they need it. Link it from the tools themselves where the admin console allows a custom notice, pin it in the main staff channel, and add it to onboarding. When the rule changes, say what changed in one line, so staff do not have to reread the whole page to spot the difference.

## Sources

- [NIST, AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [NIST AI 100-1, AI RMF 1.0, January 26, 2023](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10)
- [NIST AI Resource Center, AI RMF, including the note that a revision is in progress](https://airc.nist.gov/airmf-resources/airmf/)
- [NIST AI 600-1, Generative Artificial Intelligence Profile, July 26, 2024](https://doi.org/10.6028/NIST.AI.600-1)
- [OWASP Top 10 for LLM Applications 2025, LLM06: Excessive Agency](https://genai.owasp.org/llmrisk/llm062025-excessive-agency/)
