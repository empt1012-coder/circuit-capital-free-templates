Source: this is a Markdown copy of the free page at https://circuits.fit/guides/risk-exception-register-template.html.

# How to build a risk exception register

Owner, reason, compensating control, residual score and an expiry date that enforces itself. Columns, formulas and common mistakes.

## Who this is for

The security lead who approves exceptions to policy, the risk owner who asks for them, and the auditor or insurer who will eventually ask to see the list.

Every company has controls it does not apply everywhere. The difference between a managed exception and a hole is a written row with an owner, a reason, a compensating control and an expiry date.

A risk exception register, sometimes called a policy exception log or risk acceptance register, is where those rows live. This guide covers what to record, how to score it, how to make expiry dates enforce themselves, and the mistakes that turn a register into a list of permanent waivers. It works in any spreadsheet.

## What a risk exception is

An exception is an approved, time-limited departure from a specific control or policy. A legacy server that cannot run the endpoint agent. A vendor integration that needs a service account with a password that does not rotate. A lab instrument on an operating system that no longer receives updates. In each case the business has a reason, the control cannot be applied today, and someone senior enough accepts the remaining risk for a defined period.

That definition excludes three things that often end up in the same spreadsheet:

- **Open findings.** A vulnerability nobody has looked at yet is not an exception. It becomes one only when someone decides not to fix it on the normal timeline and says why.
- **General risks.** "Ransomware" is a risk register entry, not an exception. Keep a separate [IT risk register](https://circuits.fit/guides/it-risk-register-excel.html) for those.
- **Things that should never be waived.** Some controls are close to non-negotiable for most organizations, and many teams mark them as not eligible for exception at all. The site's free [risk exception register tool](https://circuits.fit/tools/risk-exception-register.html) treats known-exploited vulnerabilities, MFA, backups and EDR that way. Decide your own list and write it at the top of the register.

## The columns

| Column | What to enter |
| --- | --- |
| Exception ID | A unique reference such as EX-014. Never reuse one. |
| Risk or control exception | One sentence: what is not being done, where. |
| Control or policy reference | The clause or control ID being departed from, so reviewers can read the original requirement. |
| System or asset | The specific host, application or vendor, matching your asset inventory name. |
| Risk owner | The named person accountable for the system and the fix. |
| Business reason | Why the control cannot be applied now. "Vendor does not support it until version 9" is a reason. "Too hard" is not. |
| Compensating controls | What reduces the risk in the meantime, specifically enough that someone could check it. |
| Inherent likelihood and impact (1 to 5) | The risk with the control missing and nothing else done. |
| Residual likelihood and impact (1 to 5) | The risk with the compensating controls that exist today. |
| Approval | Requested, Approved, Rejected, Closed or Withdrawn. |
| Approved by | The person who accepted the risk. Not the person who asked for it. |
| Granted date and expiry date | When it started and when it stops being valid. |
| Notes | The fix plan, ticket references, anything a reviewer needs. |

Those are the inputs. Everything else in the register should be calculated, so nobody has to remember to update it.

## Scoring inherent and residual risk

Score each exception twice on the same likelihood by impact matrix: once as if nothing compensates, and once with the compensating controls in place. The gap between the two is the value of those controls, and it is what the approver is really being asked to rely on.

A 5 by 5 matrix is the usual choice. Multiply likelihood (1 Rare to 5 Almost certain) by impact (1 Minimal to 5 Severe) for a score from 1 to 25. Keep the matrix itself on a settings tab and look scores up from it rather than multiplying in each row, so you can adjust individual cells later without rewriting formulas:

```
Inherent score: =INDEX(Settings!$C$12:$G$16,H5,I5)
Severity:       =VLOOKUP(Q5,Settings!$B$20:$C$23,2,TRUE)
```

The severity lookup uses an approximate match against a small table of minimum scores. One workable set of bands:

| Minimum score | Severity | Review every |
| --- | --- | --- |
| 1 | Low | 180 days |
| 5 | Medium | 90 days |
| 10 | High | 60 days |
| 20 | Critical | 30 days |

Write one-line definitions for each likelihood and impact level next to the matrix. Without them, two people will score the same exception differently and the register will measure who filled it in rather than the risk. The [IT risk register guide](https://circuits.fit/guides/it-risk-register-excel.html) goes further into writing those scales.

The rule that matters most: residual risk is scored on controls that exist today. A compensating control that is "planned for next quarter" does not lower the residual score until it is running.

## Status, expiry and review dates

Status should be a formula built from the approval column and the expiry date, checked in order:

1. Rejected if the approval says Rejected.
2. Closed if it says Closed or Withdrawn.
3. Pending approval if it is anything other than Approved.
4. No expiry set if it is approved but the expiry date is blank.
5. Expired if the expiry date is in the past.
6. Expiring soon if the expiry is within a set window, such as 30 days.
7. Active otherwise.

"No expiry set" is its own status on purpose. An approved exception with no end date is the most common way a register fails, and it should be impossible to miss on the dashboard.

Next review due is the last review date plus the review interval for the exception's severity, using residual severity where it exists. A simple overdue flag compares that date with today. With this in place, a Critical exception that has not been looked at in a month shows up without anyone having to remember.

Two integrity checks are worth adding. A duplicate ID check (`=IF(COUNTIF($A$5:$A$304,A5)>1,"Duplicate ID","")`) catches copied rows. And an expiry check, described below, catches a register that disagrees with its own review history.

## The review log

Keep reviews on a separate tab, one row per review: date, exception ID, reviewer, decision (Keep, Extend, Close), new expiry date if extended, and the evidence checked. Do not overwrite the register's history in place. An auditor asking "who extended this, and on what basis" needs the log, not the latest value.

The register can then look up its own last review date from the log with `MAXIFS`, which returns the newest review date for that ID. It can also compare its expiry date with the new expiry from the latest Extend decision and flag any mismatch. That catches the common case where the meeting agreed an extension and nobody updated the register. Note that `MAXIFS` needs Excel 2019 or later, Microsoft 365, LibreOffice or Google Sheets.

## A worked example

An invented exception, as of November 2, 2026.

- **EX-014.** Lab analysis PC runs an operating system that no longer receives security updates. Policy reference: patching standard, section 3.
- **Business reason:** the instrument vendor's control software only supports that operating system. A supported version is promised in the vendor's next release.
- **Compensating controls:** PC moved to an isolated network segment with no internet access; file transfer only through one monitored share; local admin removed from users.
- **Inherent:** likelihood 4, impact 4, score 16, High.
- **Residual:** likelihood 2, impact 4, score 8, Medium. Review every 90 days.
- **Approved by:** the head of operations, granted October 1, 2026, expiring March 31, 2027.

The register shows it as Active. The next review is due 90 days after the last review date. Suppose the January review finds the vendor release has slipped, and the reviewer extends to June 30, 2027 with a dated plan. The reviewer adds a Review Log row with decision Extend and the new date. Until someone also changes the expiry date on the register, the expiry check flags the row. That flag is the whole point: the register and its history must agree.

Now suppose the network segmentation is undone during an office move. The residual likelihood is no longer 2. The honest response is to rescore residual on the controls that exist today, which here puts it back to the inherent 16, High, and to bring it to the next review early.

## Common mistakes

- **No expiry date.** An exception without an end date is a policy change nobody approved.
- **Residual scored on intentions.** Planned controls do not reduce today's risk.
- **The requester approves their own exception.** Approval should come from someone who owns the consequence and is not the person who benefits.
- **Vague compensating controls.** "Monitoring" is not checkable. "Alerts on any outbound connection from host X, reviewed daily by the SOC" is.
- **Extending without a plan.** Each extension should carry a new date and a reason the fix slipped.
- **Mixing findings and exceptions.** The register loses meaning when half the rows are unresolved tickets.
- **Overwriting history.** Without a review log, nobody can show how an exception came to be three years old.

## FAQ

### How long should an exception last?

As long as the fix realistically takes, and no longer than your policy allows. Many teams cap exceptions at a year and require a fresh approval after that.

### Who should approve?

Someone with authority over the business area that carries the risk, with security's recommendation recorded. Higher residual severity should need a more senior approver.

### How often should we review the whole register?

Monthly or quarterly, working through Expired, Expiring soon, Pending approval, then housekeeping such as missing expiry dates and overdue reviews.

### Will an auditor or insurer accept a spreadsheet?

What they usually look for is evidence: owner, approval, compensating controls, expiry and review history. The format matters less than whether those are present and current. Check with your own auditor.

Spreadsheet workbooks that include a risk exception register are described at https://circuits.fit/start/
