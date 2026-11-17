Source: this is a Markdown copy of the free page at https://circuits.fit/guides/limit-what-an-agent-can-touch.html.

# Limit what an agent can touch

In Gartner’s second-quarter survey of 297 security leaders, 54% have no defined limit on agent access, or they reuse a person’s access.

## Who this is for

The owner of a workflow that an agent can now run, and the security lead who will be asked what that agent can open.

Gartner’s September 30, 2026 note says an AI system does not need general intelligence to create cyber risk. It needs a way to affect operations. In a second-quarter 2026 survey of 297 cybersecurity leaders, 54% of organizations had no defined approach to limit AI-agent access, or relied on access already defined for a person.

## The fact

Treat that 54% as a description of a default, not as a score you must beat for its own sake. The default is: the integration user, the service account, or the employee who clicked connect. Gartner’s recommended shift is to govern by action privileges, and to constrain how far a workflow can go.

## The list

| Write this down | A bad answer |
| --- | --- |
| Whose identity the agent uses | “The admin who set it up” |
| Which systems it can read | “Whatever the connector allows” |
| Which systems it can change | “Same as the user” |
| What it cannot do without a person | “It will ask if it is unsure” |
| Who can turn it off tonight | “The vendor” |

If the agent can send mail, move money, open a ticket, or change a record, those are separate lines. “It only helps” is not a line.

## Why “same as the user” fails

The OWASP Top 10 for large language model applications lists excessive agency as a top risk. OWASP says the root cause is typically one or more of three things: excessive functionality, excessive permissions, or excessive autonomy. An agent connected with an employee’s account usually has all three. It can reach everything the employee can, it can use tools the task does not need, and it can act without anyone checking.

The risk is not only a model making a mistake. OWASP notes that an agent can be steered by prompt injection, including instructions hidden in a document, an email, or a web page it reads. An agent that can read untrusted content and also send email or change records is the combination to limit first.

## How to set limits, step by step

1. **Inventory first.** List every agent, its owner, and the identity it uses. The [agent inventory](https://circuits.fit/tools/agent-inventory.html) does this and flags shared or personal accounts.
2. **Give each agent its own identity.** A dedicated service account or app registration, so its actions can be logged and its access removed without touching a person.
3. **Grant only the actions the task needs.** If it drafts replies, it does not need to close tickets. If it reads invoices, it does not need to pay them.
4. **Require a person for high-impact actions.** Payments, external messages to customers, deletions, and permission changes should need approval.
5. **Log and review.** Keep a log of what the agent did. Review its access at least every 90 days, and whenever it gains a new connection.
6. **Name the off switch.** Write down who can disable the agent tonight, and how.

## A worked example

Illustrative case. A finance team connects an AI assistant to email and the accounting system using the controller’s account. It summarizes invoices. Under the list above, the assistant gets its own account with read access to the accounts payable inbox and the invoice module. It cannot send email, approve payments, or change vendor records. When it finds an invoice that needs action, it creates a draft for a person. If a malicious invoice contains hidden instructions to change bank details, the assistant has no permission to do it. The [agent access limit sheet](https://circuits.fit/tools/agent-access-limit.html) records these choices.

## Where this fits in a wider program

NIST’s AI Risk Management Framework organizes AI risk work into four functions: Govern, Map, Measure, and Manage. Agent access limits sit mostly in Manage, but they depend on Map: you cannot limit what you have not listed. NIST AI 600-1, the Generative AI Profile, adds risks specific to generative systems. Use those documents to explain the program to auditors. Use this page to start.

## Before you sign off

- Every agent is listed with an owner and its own identity.
- Read and write rights are listed by system, and match the task.
- Payments, external messages, deletions, and permission changes need a person.
- Agents that read untrusted content cannot also take high-impact actions on their own.
- There is an access review date and a named person who can switch each agent off.

The five-line version for a staff meeting is the table at the top of this page.

If you only have time for one change this quarter, move every agent off a person’s account and onto its own identity. That single step makes its actions visible in logs, lets you cut its access without locking out an employee, and turns the rest of this list into configuration rather than a project. Record the change in the [agent inventory](https://circuits.fit/tools/agent-inventory.html) so the next review starts from facts.

## Sources

- [Gartner, five actions for CISOs, September 30, 2026](https://www.gartner.com/en/newsroom/press-releases/2026-09-30-gartner-identifies-top-five-actions-for-cisos-to-take-by-end-of-2026)
- [OWASP Top 10 for LLM Applications 2025, LLM06: Excessive Agency](https://genai.owasp.org/llmrisk/llm062025-excessive-agency/)
- [NIST, AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [NIST AI 600-1, Generative Artificial Intelligence Profile](https://doi.org/10.6028/NIST.AI.600-1)
