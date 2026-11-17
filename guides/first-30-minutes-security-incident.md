Source: this is a Markdown copy of the free page at https://circuits.fit/guides/first-30-minutes-security-incident.html.

# First 30 minutes after a security incident

A one-page checklist for small teams with no security staff. Print it and keep it by the phone, because the moment you need it, your email may be the thing that is down.

## Who this is for

The owner, office manager or one “IT person” at a small company who gets the call: a strange pop-up, files that won’t open, a colleague who typed a password into a fake page, or a bank asking about a payment nobody made.

The steps below follow published guidance from CISA, the FBI’s Internet Crime Complaint Center, Microsoft and Google. Numbers in brackets point to the sources at the end.

## Minutes 0 to 5: stop and call

- [ ] **Don't wipe, reinstall or switch anything off.** Leave it as it is for now.
- [ ] **Phone, don't email,** your IT provider and whoever runs the response. If someone is in your email, they can read it. CISA advises out-of-band contact, such as phone calls [1].
- [ ] **Start a written log:** the time, what was noticed, by whom. Add a line for every step after this.

## Minutes 5 to 15: contain

- [ ] **Unplug the network cable or turn off Wi-Fi** on any computer that looks affected. Power it down only if you can't disconnect it, since that loses evidence [1].
- [ ] **Many machines affected?** Take the whole network offline at the router or switch [1].
- [ ] **Password typed into a fake page?** Change it now from a different, clean device, and sign that account out everywhere [2][3].
- [ ] **Money may have moved?** Call your bank now and ask for a recall of the funds. The FBI's IC3 says time is of the essence. Then file at ic3.gov [4].

## Minutes 15 to 30: get help and decide

- [ ] **Call your cyber insurer's claims line** if you have a policy, before you hire anyone. Note the claim number.
- [ ] **Tell staff only what they need,** in person or by phone: "Don't use X until we say so. Don't open emails about this. Don't post about it."
- [ ] **Keep suspicious emails.** Move them to a folder rather than deleting them.
- [ ] **Report it:** CISA at cisa.gov/report or 1-844-729-2472, and the FBI at ic3.gov [1].
- [ ] **Customer or staff personal data involved?** Talk to a lawyer about notification rules before you tell anyone outside. They vary by state [5].

## Don't

- Pay a ransom or reply to an attacker before talking to your insurer, a lawyer and law enforcement. The U.S. Treasury strongly discourages ransom payments [6].
- Post about it publicly, or guess at causes in writing.

## Sources

1. CISA, MS-ISAC, NSA and FBI, [#StopRansomware Guide](https://www.cisa.gov/stopransomware/ransomware-guide), Part 2: Ransomware and Data Extortion Response Checklist.
2. Microsoft, [Respond to a compromised email account in Microsoft 365](https://learn.microsoft.com/en-us/defender-office-365/responding-to-a-compromised-email-account).
3. Google Workspace Admin Help, [Identify and secure compromised accounts](https://support.google.com/a/answer/2984349).
4. FBI Internet Crime Complaint Center, [Business Email Compromise: The $55 Billion Scam](https://www.ic3.gov/PSA/2024/PSA240911) (PSA I-091124-PSA, September 11, 2024).
5. FTC, [Data Breach Response: A Guide for Business](https://www.ftc.gov/business-guidance/resources/data-breach-response-guide-business); see also NCSL, [Security Breach Notification Laws](https://www.ncsl.org/technology-and-communication/security-breach-notification-laws).
6. U.S. Treasury OFAC, [Updated Advisory on Potential Sanctions Risks for Facilitating Ransomware Payments](https://ofac.treasury.gov/system/files/126/ofac_ransomware_advisory.pdf) (September 21, 2021).

This is general guidance, not legal or insurance advice. Sources checked November 16, 2026.

A longer set of incident playbooks is on the Incident Response Kit page: https://circuits.fit/services/incident-response-kit.html
