Source: this is a Markdown copy of the free page at https://circuits.fit/guides/what-belongs-in-a-processor-clause.html.

# What belongs in a processor clause

The Commission adopted two different sets of standard clauses on June 4, 2021. One governs a processor inside the EEA. The other governs a transfer out. Do not sign the wrong PDF.

## Who this is for

The person reviewing a data-processing addendum. This page is a reading list, not legal advice and not a conclusion that the GDPR applies to you.

On June 4, 2021 the European Commission adopted two sets of standard contractual clauses. Its questions-and-answers page says one set is for the relationship between controllers and processors and meets Article 28(3) and (4) of the GDPR, including for use inside the EEA. The other set is for transfers of personal data to countries outside the EEA. They are both called SCCs. They are not interchangeable.

## Two documents

When a vendor attaches “the SCCs,” ask which decision. If the vendor processes for you and you need an Article 28 contract, the controller-processor clauses are the Commission’s pre-approved text for that job. If the vendor moves personal data out of the EEA, that is the transfer set, and it has modules for who is sending and who is receiving. A transfer annex does not, by itself, describe the processing instructions. A processor clause does not, by itself, solve a transfer.

## What to check

- The subject matter, duration, nature, and purpose of the processing, and the type of personal data. If those annexes are blank, the clause is a shell.
- Whether the vendor is a processor, a separate controller, or both for different products. The role is not a logo.
- Sub-processors: who they are, and how you hear about a new one.
- Deletion or return at the end of the service, in a sentence you can test.
- If any data leaves the EEA, whether the transfer clauses are also attached, and which module.

## The Article 28 list, in plain English

Article 28(3) of the GDPR says the contract between a controller and a processor must set out the subject matter and duration of the processing, its nature and purpose, the type of personal data, the categories of data subjects, and the controller’s obligations and rights. It then requires that the processor:

1. processes the data only on documented instructions from the controller;
2. ensures the people authorised to process the data are bound by confidentiality;
3. takes the security measures required by Article 32;
4. respects the conditions for engaging another processor, a sub-processor;
5. helps the controller respond to data subjects exercising their rights;
6. helps the controller with security, breach notification, and data protection impact assessments under Articles 32 to 36;
7. deletes or returns all personal data at the end of the services, at the controller’s choice;
8. makes available the information needed to show compliance, and allows for and contributes to audits and inspections.

Article 28(2) adds that a processor may not engage a sub-processor without the controller’s prior specific or general written authorisation, and with general authorisation must inform the controller of changes so it can object.

## How to review a DPA, step by step

1. **Check the role.** The EDPB’s Guidelines 07/2020 explain how to tell a controller from a processor. A vendor that decides its own purposes for your data, such as training its own models, may be acting as a controller for that use.
2. **Read the annexes first.** Blank or generic descriptions of processing are the most common gap.
3. **Walk the eight items.** Tick each one against the text. Note where the vendor’s wording weakens it, for example audits limited to a summary report only.
4. **Check sub-processors.** Find the list, how changes are notified, and how long you have to object.
5. **Check transfers separately.** If data leaves the EEA, confirm which transfer mechanism and SCC module is used.

## A worked example

Illustrative case. A vendor’s DPA says it will “process data in accordance with applicable law and its privacy policy.” That is not a documented instruction from you. The fix is a clause that the vendor processes personal data only on your documented instructions, including those in the agreement. The same DPA says sub-processors are listed “on our website.” Ask for notice of changes by email and a defined objection period, for example 30 days. Its deletion clause says data is deleted “in line with our retention schedule.” Ask for deletion or return at your choice within a set number of days after termination. The [software renewal scorecard](https://circuits.fit/tools/software-renewal-scorecard.html) counts unlisted subprocessors and short data-return windows against a renewal.

## AI features and the processor clause

Many vendors now add AI features to existing products. Check whether the DPA or a new addendum lets the vendor use customer personal data to train or improve models. If it does, that use may need its own analysis of roles and lawful basis. Ask counsel. Do not assume the old DPA covers a new feature.

## Before you sign off

- The vendor’s role is clear for each product and each use of the data.
- The processing annex is filled in, not generic.
- All eight Article 28(3) items are present without weakening language.
- Sub-processor changes come with notice and an objection period.
- Transfer clauses, if needed, are attached with the right module.
- Any AI training use of personal data has been reviewed by counsel.

## Sources

- [European Commission, questions and answers on the 2021 standard contractual clauses](https://commission.europa.eu/law/law-topic/data-protection/international-dimension-data-protection/new-standard-contractual-clauses-questions-and-answers-overview_en)
- [European Commission, clauses for controllers and processors in the EU/EEA](https://commission.europa.eu/publications/standard-contractual-clauses-controllers-and-processors-eueea_en)
- [Regulation (EU) 2016/679, the GDPR, on EUR-Lex](https://eur-lex.europa.eu/eli/reg/2016/679/oj): Article 28
- [EDPB Guidelines 07/2020 on the concepts of controller and processor](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-072020-concepts-controller-and-processor-gdpr_en)
- [Commission Implementing Decision (EU) 2021/915, controller-processor SCCs](https://eur-lex.europa.eu/eli/dec_impl/2021/915/oj)
