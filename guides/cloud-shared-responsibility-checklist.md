Source: this is a Markdown copy of the free page at https://circuits.fit/guides/cloud-shared-responsibility-checklist.html.

# The cloud shared-responsibility checklist

AWS’s model is security of the cloud versus security in the cloud. A managed database does not move your backup duty. An EC2 instance does not move the patch duty.

## Who this is for

The finance lead comparing a cloud bill with a colo quote, and the operator who will be asked who patches the guest.

Amazon Web Services states the shared-responsibility model in public. AWS is responsible for security of the cloud: the hardware, software, networking, and facilities that run AWS services. The customer is responsible for security in the cloud. AWS says that responsibility depends on which services you pick. For Amazon EC2, AWS says the customer manages the guest operating system, including updates and security patches, the application software the customer installs, and the security-group firewall on the instance.

## The split

Read this before a repatriation argument or a board slide that says “AWS is certified, so we are covered.” A certification of the provider’s infrastructure is not a patch on your image, a backup of your bucket, or a rule on your security group. AWS also says customers should look at the services they chose, because the work changes with the service, and because laws and regulations still apply to the customer.

## The lines

| Question | Write the owner |
| --- | --- |
| Who patches the guest OS on each EC2 image? | A person’s name, not “AWS” |
| Who sets the security group? | The team that can open a port |
| Who backs up data in a managed store, and who has tested a restore? | Still you, unless a contract names the provider’s backup product and you have a restore date |
| Who configures encryption and keys? | The person who can lose the key |
| Which of these would move if you left for a colo? | The guest, the app, the data, the firewall rules. The building would not. |

## How Microsoft and Google describe the split

The lines above use AWS’s wording. Other providers publish their own, and they differ in useful ways.

**Microsoft Azure.** Microsoft’s shared responsibility page lays out a table by deployment type: software as a service, platform as a service, infrastructure as a service, and on-premises. Physical hosts, network, and datacenter sit with Microsoft for the cloud models. The page also lists responsibilities the customer always retains, regardless of deployment type: data, endpoints, accounts, and access management. That list is a good summary for a board slide. No matter how managed the service is, your data, your devices, and your identities are yours.

**Google Cloud.** Google describes shared responsibility together with what it calls “shared fate,” where it aims to give customers secure defaults, blueprints, and guidance to help them meet their side. That is a statement of intent and tooling. It does not move your responsibilities to Google.

## How to use this checklist, step by step

1. **List your top services.** Start with the services that make up most of the bill or hold the most sensitive data.
2. **Classify each one.** Infrastructure (virtual machines), platform (managed databases, containers), or software as a service. Your share of the work shrinks as you move up, but it never reaches zero.
3. **Write an owner for each line.** Patching, network rules, backups, keys, identities. A person’s name, not a team alias.
4. **Check evidence.** A patch report, a recent restore, a key rotation log. If there is no evidence, the line is a gap.
5. **Revisit before any move.** Before repatriation or a provider switch, mark which lines change hands. The [cloud repatriation note](https://circuits.fit/articles/cloud-repatriation.html) has the cost side.

## A worked example

Illustrative case. A company runs its customer app on virtual machines, a managed database, and object storage. On the VMs, the company patches the operating system and the app, and sets the firewall rules. On the managed database, the provider patches the engine, but the company sets who can connect, turns on encryption options, and tests restores. On object storage, the company sets access policies. A misconfigured public bucket is the customer’s mistake under every provider’s model. If the company moved to a colo, it would also take on the hardware, the facility, and the physical network.

## Common mistakes

- Assuming the provider’s compliance certifications cover your configuration. They cover the provider’s side.
- Assuming managed services are backed up the way you need. Check retention and test a restore.
- Forgetting identities. Most cloud incidents start with an account, not a broken data center.

## Before you sign off

- Each major service is classified as infrastructure, platform, or software as a service.
- Each line on the checklist has a person’s name.
- You have evidence for patching, backups, keys, and access rules, not only a policy.
- You have read the split for every provider you use, in that provider’s own words.
- Any planned move shows which lines would change hands.

## FAQ

### Does this page cover Azure or Google Cloud?

The wording here is AWS’s, because that is the page linked below. Other providers publish their own split. Do not paste the AWS sentence onto another logo. Open that provider’s page and redo the table.

### Is the provider responsible for nothing in the guest?

AWS’s page draws the line at the host and the facility for EC2, and at the customer for the guest and the security group. Managed services move some of the platform work. They do not move your data-retention choices. Read the service you actually bought.

## Sources

- [AWS, Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)
- [Microsoft Learn, Shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility): responsibilities the customer always retains: data, endpoints, accounts, access management
- [Google Cloud Architecture Framework, shared responsibility and shared fate](https://cloud.google.com/architecture/framework/security/shared-responsibility-shared-fate)
