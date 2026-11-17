Source: this is a Markdown copy of the free page at https://circuits.fit/tools/agent-access-limit.html.

# Agent access limit sheet

Write down what an agent may touch before it is turned on.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

## Why write the limit down first

On September 30, 2026, Gartner reported that 54% of organizations have no defined approach to limiting AI agent access, or rely on predefined human access, based on a second-quarter survey of 297 cybersecurity leaders. Gartner’s advice is to treat frontier AI deployments as insider risks and to govern agents by their action privileges rather than by how capable the model is. An agent that reuses a person’s login can do everything that person can do, at machine speed, and the logs will show the person.

This sheet makes the limit explicit before an agent is switched on: what it may read, what it may write, which tools or APIs it may call, how much it may spend per day, who owns it, and whether a person approves writes and spending.

## How to use this

1. Name the agent and list the systems it may read, the systems it may write and the tools or APIs it may call. Leave a line blank if it gets nothing; the sheet prints “not listed” rather than filling it in.
2. Set a daily spend cap, name an owner, and choose whether a human approves writes and spending and whether logs are retained.
3. Answer the key question: can it inherit the user’s access? If yes, the sheet prints a gap line telling you not to turn it on until that is off or the limit is written down.
4. Copy the sheet into the change ticket or the [agent inventory](https://circuits.fit/tools/agent-inventory.html).

## Worked example

A finance team wants an invoice-matching agent. It may read the accounts-payable mailbox and the ERP vendor table, write only draft match records, and call the ERP’s matching API. The spend cap is 20 dollars a day in model usage, the AP manager owns it, a human approves every write, and logs are kept. Inherit is set to No. The sheet prints an ALLOW block with those lines, a DENY line for inheriting the user’s access, and “Gap: none on inherit.”

Change inherit to Yes, as happens when an agent is set up under the AP manager’s own account, and the gap line changes: the agent still inherits a person’s access, so do not turn it on. That single line is the conversation most teams skip.

## Assumptions and limits

- The sheet documents intended access. It does not enforce it. Enforcement lives in your identity provider, API gateway or agent platform.
- “Spend cap” is whatever unit you type: dollars, tokens or calls.
- Review the sheet when the agent gains a new tool or data source, not only once a year.
- On the source page, nothing you type leaves the browser.

## Template

Copy the table and fill one row per agent. Example rows from the free CSV are included.

| Agent name | Systems it can read | Systems it can write | Tools or APIs it can call | Spend cap per day | Owner named | Can it inherit the user's access | Human approves write and spend | Log retained | Allow or deny | Notes |
|---|---|---|---|---|---|---|---|---|---|---|
| Invoice triage agent | AP inbox; vendor master | Draft invoices | OCR API | 50 | Yes | No | Yes | Yes, 1 year | Allow |  |
| Sales email assistant | CRM contacts | Email send | Email API |  | No | Yes | No | No | Deny until fixed | Name an owner; give it its own identity; require approval to send |
|  |  |  |  |  |  |  |  |  |  |  |
