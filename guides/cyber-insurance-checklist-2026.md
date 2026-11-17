Source: this is a Markdown copy of the free page at https://circuits.fit/guides/cyber-insurance-checklist-2026.html.

# Cyber insurance renewal prep for mid-market IT budgets (2026)

Getting the renewal application ready. Who owns the broker and who owns the packet, which questionnaire answers stall a binder, and how to put each control on the IT budget.

## Who this is for

The U.S. mid-market CFO who signs the premium and the operator who owns the packet. The five-line control list is [What a cyber insurer will still ask](https://circuits.fit/guides/cyber-insurance-controls-checklist.html). This page is the 2026 budget version: broker versus IT, questionnaire items, line items.

## Which guide do you need?

- **Preparing the renewal application**, with the broker, the questionnaire and the IT budget: [Cyber insurance renewal prep for mid-market IT budgets (2026)](https://circuits.fit/guides/cyber-insurance-checklist-2026.html).
- **Collecting proof for each control**, for an underwriter now or a claims adjuster later: [What a cyber insurer will still ask: the controls evidence checklist](https://circuits.fit/guides/cyber-insurance-controls-checklist.html).

Swiss Re’s 2026 cyber view, as covered September 2, still has global premium on track for $16.4 billion, growing about 5% a year since 2022, even as rates fell for a fourth year. The cut shrank: roughly −13% globally in 2025 versus about −5% in 2026, with the U.S. stabilizing faster than Europe. Marsh’s Global Insurance Market Index put the U.S. cyber rate change at −2% in the second quarter of 2026 — the twelfth consecutive quarterly decline globally (−4%). Cheap paper is not a thin application.

Mid-market is the layer insurers still want. Swiss Re’s segment split, in that same coverage, put mid-market at 40–50% penetration and about $4.1 billion of premium. You are not too small to be asked the same five things a large corporate is asked. You are large enough for the no to hurt.

## The questionnaire is a budget

Map each yes/no on the form to a named owner, a vendor, and a line on the IT plan. If MFA is “rolling out,” that is a no. If EDR is installed and nobody is on call, that is a no. If backups exist and restores have not been tested, that is a no. Underwriters do not fund a roadmap. They price a current state.

AM Best, via *Insurance Journal* in July, still had U.S. prices cutting in the first quarter and a 2025 loss ratio around 53. A soft market is not a reason to skip hygiene. It is a reason to lock the control list while the rate is still walking down.

Use the form as a floor, not a strategy. Controls that please an underwriter can still fail a determined attacker. They will, however, decide whether you have a policy or a brochure.

## Who owns broker versus IT

If the broker sits only with finance, IT will be surprised by a control they cannot implement in 30 days. If IT owns the packet alone, finance will be surprised by the premium, the retention, and the sublimit on social engineering. Put both in the room in month nine, not month twelve.

Name three seats: the person who signs, the person who can change identity and endpoint settings, and the person who will call counsel at 2 a.m. If one chair is empty, you will renew by default or you will scramble in a denial.

The broker’s job is the market: markets, wordings, retentions, additional insureds, and whether “computer system” still means what you think it means when a model leaks into an unlisted vendor. IT’s job is evidence: MFA coverage reports, EDR on-call, restore test dates, privilege logs. Do not let either side fill in the other’s blanks.

## Controls that stall a binder

| Control | What “yes” means | What fails |
| --- | --- | --- |
| MFA | Enforced on email, VPN, RDP, cloud admin, and other accounts that touch business data | “Rolling out.” SMS-only on privileged accounts. Shared logins |
| EDR | Deployed and watched. A named on-call for the 2 a.m. alert | Agents installed, nobody paged. A dashboard nobody opens |
| Immutable or offline backups | A restore has been tested on a date you can show | A screenshot of a backup job. Tapes nobody has mounted |
| Privilege | Who can disable EDR and identity tools, and is that logged | Shared admin. Domain admin on every laptop |
| IR retainer | Named counsel and forensics you can call without a procurement cycle | A vendor list with no contract. “We’ll figure it out” |

Shared logins are the easiest line to fix. A team password manager gives each person their own vault entry and lets you revoke access when someone leaves. 1Password, Bitwarden and NordPass all offer business plans.

## What operators actually get asked

The packet varies by carrier. The repeats do not. Operators in U.S. mid-market shops keep seeing some version of these:

- Is MFA enforced (not offered) on email, remote access, and cloud consoles? Can you export the coverage report?
- Is EDR or MDR on every endpoint that matters, and who is on call after hours?
- Are backups immutable or offline, and when was the last restore test?
- Who can disable those tools? Is privileged access logged and reviewed?
- Do you have a named incident retainer — counsel and forensics — already on paper?
- How do you handle third-party software and vendor access after the last supply-chain headline?
- What AI tools sit in production, and are they in the system inventory the policy already assumes?

Marsh’s U.S. Q2 2026 note said some insurers included clarifying AI language, with most asking questions on AI exposure, use, and controls. Swiss Re argues many AI incidents may already sit inside existing “computer system” wordings, with claims of that flavor still limited. Read the form. Do not assume a model leak into an unlisted vendor is covered because the rate is down 2%.

> A cheaper policy written on controls you do not run is a denial at claim time.

Shop limits if a payments or cloud outage would take a quarter. Do not skip the line items the questionnaire already priced in to “save” a premium that assumed you had them.

## Sources

- [Risk & Insurance / Swiss Re, Sept. 2, 2026](https://riskandinsurance.com/cyber-insurance-at-a-crossroads-ai-reshapes-risk-as-market-growth-stays-steady/)
- [Marsh, Global Insurance Market Index, Q2 2026](https://www.marsh.com/en/about/media/global-commercial-insurance-falls-6-percent-q2-2026.html) (U.S. detail: [U.S. insurance rates](https://www.marsh.com/en/services/international-placement-services/insights/us-insurance-rates.html))
- [Insurance Journal / AM Best, July 27, 2026](https://www.insurancejournal.com/magazines/mag-features/2026/07/27/878813.htm)

## FAQ

### Does a cheaper premium mean we can skip a control?

No. Marsh had U.S. cyber rates down 2% in Q2 2026. The questionnaire still wants MFA, watched EDR, and a restore test. The rate cut is not a waiver.

### Who should own the broker?

Finance signs. IT supplies evidence. Both sit in month nine. The broker does not fill in MFA coverage from memory.

### Is an IR retainer required if we have an internal team?

You still want counsel and forensics on paper. Internal teams do not replace a call you can make at 2 a.m. without procurement.

### Will a soft market last?

Nobody who is honest will guarantee it. Swiss Re already flagged loss ratios walking up while prices walked down. Take the rate. Keep the controls.
