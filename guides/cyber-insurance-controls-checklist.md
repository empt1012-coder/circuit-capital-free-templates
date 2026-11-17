Source: this is a Markdown copy of the free page at https://circuits.fit/guides/cyber-insurance-controls-checklist.html.

# What a cyber insurer will still ask: the controls evidence checklist

Five controls, and the proof behind each one. What to hand an underwriter, or a claims adjuster after an incident, for MFA, EDR, backups, privileged access and a named retainer.

## Who this is for

The CISO who fills the form. This page is the control list. The 2026 IT-budget packet — broker versus IT, questionnaire items, line items — is [the other guide](https://circuits.fit/guides/cyber-insurance-checklist-2026.html).

## Which guide do you need?

- **Preparing the renewal application**, with the broker, the questionnaire and the IT budget: [Cyber insurance renewal prep for mid-market IT budgets (2026)](https://circuits.fit/guides/cyber-insurance-checklist-2026.html).
- **Collecting proof for each control**, for an underwriter now or a claims adjuster later: [What a cyber insurer will still ask: the controls evidence checklist](https://circuits.fit/guides/cyber-insurance-controls-checklist.html).

Swiss Re’s 2026 cyber view, as reported September 2, still has global premium growing even as rates fall for a fourth year (about −5% in 2026 after −13% in 2025). AM Best, via *Insurance Journal*, had U.S. prices still cutting in the first quarter and a 2025 loss ratio of 53. Cheap paper does not mean a thin application. Underwriters lag the threat. They do not stop asking the same five things.

## The five lines that stall a binder

1. **MFA everywhere that matters** — email, VPN, admin, cloud consoles. “Rolling out” is not yes.
2. **EDR that is watched** — installed is not monitored. Who gets the 2 a.m. alert?
3. **Backups that are immutable or offline, and restored** — a screenshot of a backup job is not a restore test.
4. **Privileged access** — who can disable the tools in item 2, and is that logged?
5. **A named incident retainer** — counsel and a forensics shop you can call without a procurement cycle.

> If you cannot answer those in a staff meeting, you do not have a control program. You have hope.

## How to use a soft market

Shop limits if a payments or cloud outage would take a quarter. Put finance and IT in the same room in month nine, not month twelve. Do not skip hygiene to “save” on a premium that already assumes you have it. A cheaper policy written on controls you do not run is a denial at claim time.

Swiss Re also notes many AI-related incidents may already sit inside existing “computer system” wordings, with claims of that flavor still limited. Read the form. Do not assume a model leak into an unlisted vendor is covered because the market is soft.

## Control checklist

| Control | What they ask | What fails |
| --- | --- | --- |
| MFA | On for email, VPN, admin, cloud | “Rolling out” |
| EDR | Installed and watched | No named on-call |
| Backups | Immutable or offline, restore tested | A screenshot of a job |
| Privilege | Who can disable EDR, and is it logged | Shared admin |
| Retainer | Named counsel and forensics | A vendor list with no contract |

## What evidence to have ready

A yes on an application is easier to defend when you can show it. For each of the five lines, decide in advance what proof you would hand an underwriter, or a claims adjuster after an incident.

- **MFA.** A report from your identity provider showing enforcement on email, remote access, admin roles, and cloud consoles. CISA recommends phishing-resistant MFA, such as FIDO/WebAuthn security keys or PKI-based methods, as the strongest option. Start with administrators.
- **EDR.** Coverage percentage across endpoints and servers, and the after-hours escalation list with names.
- **Backups.** The date and result of the last restore test. CISA’s #StopRansomware guide recommends offline, encrypted backups that are tested regularly.
- **Privileged access.** The list of accounts that can disable security tools, and the log showing that action is recorded.
- **Retainer.** Signed engagement letters with counsel and a forensics firm, and whether they are on the insurer’s approved panel.

## A 60-day plan before renewal

1. **Day 1 to 10.** Pull last year’s application. Mark every answer that is not fully true today.
2. **Day 10 to 30.** Close the cheap gaps first: turn on MFA for remaining admin accounts, run a restore test, update the escalation list.
3. **Day 30 to 45.** Collect evidence for each line. Store it where finance and IT can both find it.

## Do not forget payment fraud

The FBI’s Internet Crime Complaint Center reported about $2.77 billion in business email compromise losses in 2024, out of $16.6 billion in total reported losses. Many policies treat social engineering and funds-transfer fraud differently from a network breach, sometimes with lower sub-limits. Ask where a fraudulent vendor bank change would fall, and require a call-back to a number on file before changing payment details. [Stop using a voice as approval](https://circuits.fit/guides/stop-using-a-voice-as-approval.html) covers the process.

## Before you sign off

- Every yes on the application has evidence behind it, stored where finance and IT can find it.
- Open gaps are in the risk exception register with an owner and a date.
- You know where social engineering and funds-transfer fraud sit in the policy, and the sub-limit.
- Counsel and forensics contacts are signed and known to the on-call team.

For the budget side, see the [2026 cyber insurance checklist for IT budgets](https://circuits.fit/guides/cyber-insurance-checklist-2026.html).

## Sources

- [Risk & Insurance / Swiss Re, Sept. 2, 2026](https://riskandinsurance.com/cyber-insurance-at-a-crossroads-ai-reshapes-risk-as-market-growth-stays-steady/)
- [Insurance Journal / AM Best, July 27, 2026](https://www.insurancejournal.com/magazines/mag-features/2026/07/27/878813.htm)
- [CISA, Implementing Phishing-Resistant MFA (PDF)](https://www.cisa.gov/sites/default/files/publications/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf)
- [CISA, #StopRansomware Guide](https://www.cisa.gov/stopransomware/ransomware-guide)
- [FBI IC3, 2024 Internet Crime Report (PDF)](https://www.ic3.gov/AnnualReport/Reports/2024_IC3Report.pdf)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)

## FAQ

### Does a cheaper premium mean a lighter application?

No. Rates can fall while the questionnaire stays mean. Underwriters lag the threat. They do not stop asking the same five things.

### What does “EDR that is watched” mean?

Someone is named, after hours, to the alert. Installed agents with nobody on call are a no.

### Do we need a retainer if we have an internal IR team?

You still want counsel and a forensics shop on paper. Internal teams do not replace a call you can make at 2 a.m. without procurement.

### Can we skip a control because the market is soft?

Not if you want the claim paid. A cheaper policy written on controls you do not run is a denial later.
