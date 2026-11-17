Source: this is a Markdown copy of the free page at https://circuits.fit/tools/agent-inventory.html.

# AI agent inventory and access map

List each agent, the identity it uses, and what it can change. Flags stale reviews and shared logins.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

A row is flagged when the agent uses a person's account or a shared account, when it can write and has no owner, or when the last access review is missing or 90 days old or older.

## How to use this

1. Replace the example rows. One agent per row. Use “Its own account” only when the agent does not sign in as a person.
2. Read the flag count. A shared login, write access with no owner, or a review older than 90 days stays on the row until you change it.
3. A fillable table is at the end of this file. On the source page, you can also export or import a CSV; that stays on your device.

## What this inventory does

An AI agent is software that can take actions, not only answer questions. It might reply to a ticket, update a record, send an email, or start a payment. Each of those actions runs under some identity, and that identity decides what the agent can touch. This page is a simple register: one row per agent, the account it uses, what it can read and change, whether it can spend money or send external messages, and when its access was last reviewed.

Gartner’s September 30, 2026 note on CISO priorities reported that 54% of organizations in a second-quarter survey of 297 security leaders had no defined approach to limiting agent access, or relied on access defined for a person. The first step out of that position is a list. You cannot limit what you have not written down.

## How the flags work

The page flags three conditions on each row:

- **Person’s or shared account.** If the agent signs in as an employee or a shared login, its actions are hard to tell apart from a human’s, and it usually has more access than its task needs. The OWASP Top 10 for LLM applications calls this kind of problem excessive agency: excessive functionality, permissions, or autonomy.
- **Can write, no owner.** An agent that can change systems needs a named person who answers for it.
- **Stale or missing review.** No access review date, or a review 90 days old or older. Access drifts. A quarterly review is a practical floor.

## Worked example

The page loads with two example rows. They are illustrations, not real systems.

**Example: invoice drafter.** Owner A. Patel. It drafts invoice notes, runs in the company tenant under its own account, can read billing, cannot write anywhere, cannot spend or send external messages, and was reviewed 10 days ago. No flags.

**Example: support reply.** No owner. It replies to tickets in the helpdesk, uses a person’s account, can read tickets and write ticket comments, can send external messages, handles customer data, and was last reviewed 120 days ago. It gets three flags: a person’s account, write access with no owner, and a review older than 90 days.

The fix list for the second row writes itself: give the agent its own service identity with only ticket-comment rights, name an owner, and schedule a review. Because it sends messages to customers, the owner should also decide which replies need a person to approve them.

## Filling in a row

1. **Name and purpose.** Use the name people actually call it, and one line on what it is for.
2. **Where it runs.** The product or platform: a helpdesk, a CRM, a cloud account, a developer tool.
3. **Identity.** Check the admin console. If the agent was connected by an employee clicking “authorize,” it probably uses that employee’s access.
4. **Can read and can write.** List systems, not vague scopes. “Billing” is better than “finance data.”
5. **Spend and external messages.** Mark Yes if it can make any payment, purchase, or refund, or send anything outside the company.
6. **Sensitivity and review date.** The most sensitive data it can reach, and the date someone last confirmed its access.

## Limitations

- The list is only as good as discovery. Agents built into SaaS products you already own may not appear in any IT inventory. Ask each application owner.
- The page does not connect to your systems or verify access. It records what you type.
- Three flags are a floor, not a full risk assessment. An agent with its own account can still have far too much access.

## FAQ

### Does my data leave the browser?

No. The CSV import is read on this device, and nothing is uploaded.

### What counts as an agent?

For this list, anything that can take an action in a system without a person clicking each step. A chatbot that only answers questions is lower priority, but list it if it can read sensitive data.

### How often should we review?

The page flags reviews at 90 days. Review sooner when the agent gains a new connection or permission.

### What comes after the inventory?

Set limits for each agent with the [agent access limit sheet](https://circuits.fit/tools/agent-access-limit.html), and write a one-page rule for staff with [A one-page AI use rule](https://circuits.fit/guides/one-page-ai-use-rule.html).

## Template

Copy the table and fill one row per agent. Example rows from the free CSV are included.

| Name | Owner | Purpose | Where it runs | Identity | Can read | Can write | Spend cap | External messages | Data sensitivity | Last review | Flags |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Invoice triage agent | AP manager | Sort inbound invoices | SaaS AP platform | Dedicated service account | AP inbox; vendor master | Draft invoices only | 50/day | No | Confidential | 2026-10-01 |  |
| Sales email assistant | Sales ops | Draft follow-ups | CRM add-on | Inherits rep's login | CRM contacts | Sends email | None set | Yes | Internal |  | Shared/inherited identity; no review date; no spend cap |
|  |  |  |  |  |  |  |  |  |  |  |  |
