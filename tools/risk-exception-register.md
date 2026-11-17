Source: this is a Markdown copy of the free page at https://circuits.fit/tools/risk-exception-register.html.

# Risk exception register

Track an exception, its owner, and its expiry. Known-exploited bugs, MFA, backups, and EDR are marked not waivable.

Not legal, tax, insurance, or procurement advice. The interactive version on the source page runs in your browser and does not upload what you type.

Exceptions for a CISA Known Exploited Vulnerability, MFA, backups, or EDR are marked Not waivable. A row is also flagged when it has no owner, no expiry, or no funded fix, and when the expiry is past or inside 30 days.

## How to use this

1. Replace the example rows. Pick CISA KEV, MFA, Backups, or EDR when the exception is one of those. Those four stay Not waivable.
2. Give every other row an owner, an expiry, and a funded amount above zero. A blank expiry or a no on funding stays flagged.
3. A fillable table is at the end of this file. On the source page, you can also export or import a CSV; that stays on your device.

## Why a register, and why some rows are not waivable

Every security program carries exceptions: a server that cannot take a patch until a vendor certifies it, a break-glass account without multi-factor sign-in, a laptop group where the endpoint agent conflicts with an old application. Exceptions are normal. Exceptions with no owner, no end date and no money behind the fix are how a temporary gap becomes permanent.

This register treats four controls as not waivable: a vulnerability on CISA’s Known Exploited Vulnerabilities catalog, multi-factor authentication, backups and endpoint detection and response. That is an editorial choice, not a legal rule. We chose those four because they are the controls attackers most often find missing, and because cyber insurers routinely ask about them on applications (see [What a cyber insurer will still ask](https://circuits.fit/guides/cyber-insurance-controls-checklist.html)). For federal civilian agencies, CISA’s BOD 26-04 already sets a three-day remediation clock, plus forensic triage, for the highest-risk catalog entries on internet-facing systems. A row in one of those four categories can still be recorded. It is labeled Not waivable so nobody mistakes the record for permission.

## Worked example

Say that on October 21, 2026, your team records an exception for an internet-facing edge gateway affected by a known-exploited bug. The platform team owns it. The reason is the next change window. The compensating control is a source-address restriction. No fix is funded, the CIO accepted the risk, and the exception expires on October 31.

The register returns: “CISA KEV — Not waivable,” with flags “No funded fix” and “Expires in 10 days.” The summary line counts one not-waivable row and one row with another flag. That is the conversation to have: the change window is not a reason to leave a known-exploited edge device open for ten days, and an exception with no funded fix has no end.

A second example: an “Other” row for a vendor cutover with an owner, a funded amount of 12,000, and an expiry 70 days out returns no flags. That is what a healthy exception looks like.

## Assumptions and limits

- A row is flagged when the owner is blank, the expiry is blank or not a date, the fix is not marked funded with an amount above zero, or the expiry is past or within 30 days.
- Amounts are in whatever currency you type. The page does not convert or total them.
- Dates are compared with this device’s clock.
- On the source page, CSV export and import happen in the browser and the file is not uploaded. The CSV columns are control, system, owner, reason, compensating, funded, amount, expiry and accepted.
- This is a working list, not a governance, risk and compliance system. Keep the authoritative record where your auditors expect it.

## Questions readers ask

### Who should accept the risk?

Someone who owns the budget that would fix it. If the person accepting the risk cannot fund the fix, the exception is a note, not a decision.

### How long should an exception last?

As short as the funded fix allows. Set the expiry to the date the fix ships, and review anything inside 30 days at your weekly security meeting.

## Template

Copy the table and fill one row per exception. Example rows from the free CSV are included.

| Control | System | Owner | Reason | Compensating control | Funded | Amount | Expiry | Accepted by | Review note |
|---|---|---|---|---|---|---|---|---|---|
| CISA KEV | Internet-facing edge gateway | Platform team | Next change window | Source-address restriction | No | 0 | 2026-10-31 | CIO | Not waivable: known-exploited bug |
| Other | Legacy file server | IT operations | Vendor cutover in progress | Network segmentation | Yes | 12000 | 2027-01-05 | CFO |  |
|  |  |  |  |  |  |  |  |  |  |

Spreadsheet workbooks that include a risk exception register are described at https://circuits.fit/start/
