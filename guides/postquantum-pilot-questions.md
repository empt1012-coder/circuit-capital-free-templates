Source: this is a Markdown copy of the free page at https://circuits.fit/guides/postquantum-pilot-questions.html.

# Questions before a post-quantum pilot

Gartner’s September 30 note: start a pilot, or expect at least double the migration cost after 2027. Fifty-one percent of surveyed CISOs had not started.

## Who this is for

The security lead who owns keys and certificates, and the finance lead who will otherwise meet this as a surprise migration.

Gartner’s September 30, 2026 release says organizations that do not begin piloting post-quantum cryptography by 2027 will face at least 200% higher costs for the full migration. The same release says a survey of CISOs found 51% had not begun any post-quantum work. Christopher Mixter, a Gartner vice president analyst, describes harvest-now-decrypt-later and harvest-now-forge-later as reasons the data you store now is already part of the decision.

## The claim

The 200% figure is Gartner’s prediction, not a quote you have measured in your own estate. Use it as a reason to inventory, not as a number to paste into a budget as if it were your quote. The 51% figure is a description of peers who have not started. It is not a reason to wait with them.

## The pilot

- Where do you use public-key cryptography today: TLS, VPN, code signing, email, document signing, and the keys inside vendor products? A pilot that only covers the website certificate is a demo.
- Which data, if stolen this year and decrypted later, would still matter? That is the harvest-now list. Customer secrets and long-lived signatures belong on it. Ephemeral session data often does not.
- Who owns the inventory, and what does “begun” mean? Gartner’s 51% is “have not begun any PQC-related activities.” A slide titled “quantum” with no system in scope is not a beginning.
- What would the pilot change in ninety days: one protocol, one vendor that already offers a hybrid mode, or a list of products that cannot? Write the change, not the theme.

## The standards are published

The pilot has a target. On August 13, 2024, NIST released its first three finalized post-quantum cryptography standards:

- **FIPS 203**, ML-KEM, a key-encapsulation mechanism for establishing shared keys, derived from CRYSTALS-Kyber.
- **FIPS 204**, ML-DSA, a digital signature algorithm derived from CRYSTALS-Dilithium.
- **FIPS 205**, SLH-DSA, a stateless hash-based digital signature algorithm derived from SPHINCS+.

NIST has also published a draft transition report, NIST IR 8547, describing its expected approach to moving from quantum-vulnerable algorithms such as RSA and elliptic-curve cryptography to these standards. The initial public draft proposed deprecating those quantum-vulnerable algorithms after 2030 and disallowing them after 2035. It is a draft, so check the current version before you put a date in a plan. CISA keeps a post-quantum page with resources for organizations planning the move.

## A 90-day pilot plan

1. **Weeks 1 to 3: inventory.** List where public-key cryptography is used: TLS certificates, VPNs, SSH, code signing, document signing, and inside vendor products. Start with internet-facing systems.
2. **Weeks 3 to 5: rank by data lifetime.** Data that must stay secret for ten years or more, and signatures that must stay trusted for a long time, go first.
3. **Weeks 5 to 8: ask vendors.** For your top systems, ask each vendor whether it supports ML-KEM or a hybrid key exchange today, and if not, when.
4. **Weeks 8 to 12: test one change.** Turn on a hybrid post-quantum key exchange in one test environment where your software supports it, and measure compatibility and performance.
5. **Week 12: report.** What was inventoried, what was tested, what failed, and what it would take to extend.

## A worked example of the vendor ask

Illustrative email: “We are planning our transition to NIST’s post-quantum standards, FIPS 203, 204, and 205. For [product], please tell us: which cryptographic algorithms the product uses for key exchange and signatures today; whether it supports ML-KEM or a hybrid key exchange now, and in which version; your roadmap date for ML-DSA or SLH-DSA signatures; and whether cryptographic algorithms can be changed by configuration or require an upgrade.” File the answers. A vendor with no roadmap is a risk you can now name.

## What finance should know

Most of the cost is labor and replacement of products that cannot be upgraded, not new software licenses. The inventory is what turns Gartner’s prediction into your own estimate. Budget the inventory now. Budget the migration once you know what is in it.

## Before you sign off

- An inventory of public-key cryptography exists, starting with internet-facing systems.
- Systems are ranked by how long their data or signatures must stay safe.
- Top vendors have been asked about FIPS 203, 204, and 205 support, in writing.
- One test environment has tried a hybrid key exchange, and the result is written down.
- Finance has a budget line for the inventory, separate from the migration.

Report progress in the same terms each quarter: systems inventoried, systems ranked, vendors asked, vendors with a dated roadmap, and changes tested. Those five counts tell a board more than a maturity score, and they show whether the program is moving. When NIST finalizes its transition report, update the dates in the plan to match the final text.

## Sources

- [Gartner, five actions for CISOs, September 30, 2026](https://www.gartner.com/en/newsroom/press-releases/2026-09-30-gartner-identifies-top-five-actions-for-cisos-to-take-by-end-of-2026)
- [NIST, first three finalized post-quantum encryption standards, August 13, 2024](https://www.nist.gov/news-events/news/2024/08/nist-releases-first-3-finalized-post-quantum-encryption-standards)
- [NIST FIPS 203, ML-KEM](https://csrc.nist.gov/pubs/fips/203/final)
- [NIST FIPS 204, ML-DSA](https://csrc.nist.gov/pubs/fips/204/final)
- [NIST FIPS 205, SLH-DSA](https://csrc.nist.gov/pubs/fips/205/final)
- [NIST IR 8547 (initial public draft), Transition to Post-Quantum Cryptography Standards](https://csrc.nist.gov/pubs/ir/8547/ipd)
- [CISA, Post-Quantum Cryptography Initiative](https://www.cisa.gov/quantum)
