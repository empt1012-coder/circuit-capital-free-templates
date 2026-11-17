Source: this is a Markdown copy of the free page at https://circuits.fit/guides/stop-using-a-voice-as-approval.html.

# Stop using a voice as approval

Gartner’s September 30 note: do not authorize a decision because someone recognized a face or a voice. Pair detection with another authenticator and a provenance check.

## Who this is for

Anyone who can approve a payment, a vendor change, or a password reset because a call “sounded like” the boss.

Gartner’s September 30, 2026 release says deepfake threats are mainstream, and that CISOs should drive a process change: recognition is not an acceptable basis for authorizing a decision or an action. Detection software is one layer. Gartner also names contextual signals, additional authentication, and checks on content provenance.

## The rule

Write it in one sentence your accounts-payable clerk can repeat. Example: no payment, mailbox rule, or vendor-bank change is approved on a voice, a video, or a familiar writing style alone. A second channel, already on file, has to say yes. If you cannot write the sentence, the current process is “we know our people.”

## The redesign

- List the actions that move money, data, or access. Those are the ones recognition must not unlock.
- Name the second factor that already exists: a callback to a number on the vendor master, a hardware key, an approval in the system of record. Do not invent a new app if the second factor is already policy and simply unused.
- For public content, ask where a synthetic image or audio came from before it goes on a site or into a customer message. Provenance is the check Gartner pairs with detection.
- Tell staff that matching a voice is not a failure of attention. It is the attack.

## What the FBI has warned

This is not a hypothetical risk. On December 3, 2024, the FBI’s Internet Crime Complaint Center warned that criminals use generative AI to commit fraud on a larger scale and make it more believable, including AI-generated audio to impersonate a close relative or a person in authority. On May 15, 2025, the FBI warned of a campaign since April 2025 in which malicious actors sent text messages and AI-generated voice messages claiming to come from senior US officials, to build rapport before gaining access to accounts. A December 19, 2025 alert said the impersonation campaign was continuing.

The money at stake is large. The FBI’s 2024 Internet Crime Report recorded about $2.77 billion in reported business email compromise losses. Voice and video add a new way to make the same request look legitimate.

## How to put the rule in place, step by step

1. **List the high-risk actions.** Payments over a threshold, vendor bank detail changes, payroll changes, password and MFA resets, and access grants.
2. **Name the second channel for each.** A call-back to a number already in the vendor master or HR system, never a number given in the request. An approval in the system of record. A hardware security key for help-desk resets.
3. **Write the rule in one sentence.** Post it where approvers work.
4. **Give staff permission to slow down.** Say in writing that no one will be penalized for verifying a request from a senior person.
5. **Test it.** Run a drill with a harmless fake request and see whether the process holds.

## A worked example

Illustrative case. An accounts payable clerk gets a video call that appears to be the CFO, asking for an urgent wire to a new supplier before a deal closes. Under the rule, the clerk says the request must go through the payment system and will be confirmed by a call to the CFO’s number on file. The clerk calls that number. The real CFO knows nothing about it. No money moves. The process worked without anyone needing to spot that the video was fake.

## Help desk resets are the weak spot

Many account takeovers start with a call to the help desk asking to reset a password or MFA device. NIST’s digital identity guidelines, SP 800-63B, describe phishing-resistant authenticators and the importance of strong recovery processes. Require the same second channel for resets as for payments. If the person can prove identity with a hardware key or an in-person check, the voice does not matter.

## Before you sign off

- The high-risk actions are listed.
- Each has a second channel that uses contact details already on file.
- The rule is one sentence, posted where approvers work.
- Staff have written permission to verify senior requests.
- Help desk resets follow the same rule as payments.
- A drill has been run and the result recorded.

Review the rule after any near miss, not only after a loss. A clerk who stopped a fake request is the best source of what the attack looked like and where the process felt awkward. Fix the awkward step, or people will start skipping it. Share the story, without blame, so the next person recognizes the pattern. The insurance side of these losses is in [What a cyber insurer will still ask](https://circuits.fit/guides/cyber-insurance-controls-checklist.html).

## Sources

- [Gartner, five actions for CISOs, September 30, 2026](https://www.gartner.com/en/newsroom/press-releases/2026-09-30-gartner-identifies-top-five-actions-for-cisos-to-take-by-end-of-2026)
- [FBI IC3, PSA I-120324, December 3, 2024](https://www.ic3.gov/PSA/2024/PSA241203): criminals use generative AI to facilitate financial fraud
- [FBI IC3, PSA I-051525, May 15, 2025](https://www.ic3.gov/PSA/2025/PSA250515): senior US officials impersonated with text and AI-generated voice messages
- [FBI IC3, PSA I-121925, December 19, 2025](https://www.ic3.gov/PSA/2025/PSA251219): impersonation campaign continues
- [FBI IC3, 2024 Internet Crime Report (PDF)](https://www.ic3.gov/AnnualReport/Reports/2024_IC3Report.pdf)
- [NIST SP 800-63, Digital Identity Guidelines](https://pages.nist.gov/800-63-4/)
