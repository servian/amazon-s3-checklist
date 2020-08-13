# Amazon S3 Checklist

The Amazon S3 Checklist is an exhaustive list of all elements you need to have / to test before using S3 in production.

[How to use](#how-to-use) • [Contributing](#contributing)

## Sister Projects

- [Amazon Redshift Checklist](https://github.com/servian/amazon-redshift-checklist)

## Table of Contents

1. [Management](#management)
2. [Availability](#availability)
3. [Monitoring](#monitoring)
4. [Security](#security)
5. [Performance](#performance)
6. [Cost](#cost)

---

## How to use

All items in the **Amazon S3 Checklist** are required for the majority of the projects, but some elements can be omitted or are not essential. We choose to use 3 levels of flexibility:

- :green_circle: means that the item is **recommended** but can be omitted in some particular situations.
- :yellow_circle: means that the item is **highly recommended** and can eventually be omitted in some really particular cases.
- :red_circle: means that the item **can't be omitted** by any reason.

Some resources possess an emoticon to help you understand which type of content / help you may find on the checklist:

- :book: documentation or article
- :wrench: online tool / testing tool
- :video_camera: media or video content

---

## Management

- [ ] :red_circle: **Bucket Policy vs IAM Policy vs ACL:** Setting up the right access controls for your S3 buckets and objects.

  - :book: [IAM Policies and Bucket Policies and ACLs! Oh, My! (Controlling Access to S3 Resources)](https://aws.amazon.com/blogs/security/iam-policies-and-bucket-policies-and-acls-oh-my-controlling-access-to-s3-resources/)

- [ ] :yellow_circle: **Access Points:** Simplifies managing data access at scale for applications using shared data sets on S3.

  - :book: [Amazon S3 Access Points](https://aws.amazon.com/s3/features/access-points/)

- [ ] :yellow_circle: **Lifecycle policy:** Implement lifecycle needs according to frequency, durability, and latency requirements.

  - :book: [Object lifecycle management](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html)

- [ ] :green_circle: **Object tagging policy:** Object tagging is a powerful mechanism to attach metadata to objects managed in S3.

  - :book: [Object tagging](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-tagging.html)

[:arrow_up: back to top](#table-of-contents)

---

## Availability

- [ ] :red_circle: **Backup plan:** 11 9s of durability is not bulletproof. Consider cross-region replication or multi-cloud backups.

  - :book: [Replication](https://docs.aws.amazon.com/AmazonS3/latest/dev/replication.html)

- [ ] :yellow_circle: **Object versioning:** Object versioning, in conjunction with lifecycle management enhances application resilience.

  - :book: [Object Versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectVersioning.html)

[:arrow_up: back to top](#table-of-contents)

---

## Monitoring

- [ ] :red_circle: **Monitoring plan:** What metrics are recorded? Who is notified? How often are metrics monitored?

  - :book: [Monitoring Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/monitoring-overview.html)

- [ ] :red_circle: **CloudTrail:** CloudTrail logs cover general interactions with the S3 service.

  - :book: [Logging with Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/logging-with-S3.html)

- [ ] :red_circle: **Server access logging:** Server access logging provides detailed records for the requests that are made to a bucket.

  - :book: [Logging with Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/logging-with-S3.html)
  - :book: [Amazon S3 server access logging](https://docs.aws.amazon.com/AmazonS3/latest/dev/ServerLogs.html)

[:arrow_up: back to top](#table-of-contents)

---

## Security

- [ ] :red_circle: **Block all public access:** Low complexity mechanism to prevent public data breaches.

  - :book: [Using Amazon S3 block public access](https://docs.aws.amazon.com/AmazonS3/latest/dev/access-control-block-public-access.html)

- [ ] :red_circle: **Encryption:** Enabling SSE-S3 default encryption is free. SSE-KMS and SSE-C can be further used for extra levels of security and flexibility.

  - :book: [Protecting data using encryption](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingEncryption.html)
  - :book: [How do I enable default encryption for an Amazon S3 bucket?](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/default-bucket-encryption.html)
  - :book: [How Amazon Simple Storage Service (Amazon S3) uses AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/services-s3.html)

- [ ] :red_circle: **SSL requests only:** Enforce the use of SSL for all S3 API requests.

  - :book: [s3-bucket-ssl-requests-only](https://docs.aws.amazon.com/config/latest/developerguide/s3-bucket-ssl-requests-only.html)

- [ ] :yellow_circle: **MFA delete:** Adds another layer of security requiring additional authentication.

  - :book: [MFA delete](https://docs.amazonaws.cn/en_us/AmazonS3/latest/dev/Versioning.html#MultiFactorAuthenticationDelete)

- [ ] :yellow_circle: **VPC endpoints:** Where traffic being routed over the Internet is undesirable, VPC Endpoints should be used to access S3.

  - :book: [VPC endpoints](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html)

- [ ] :yellow_circle: **:new: Amazon GuardDuty:** Detect suspicious activities such as requests coming from an unusual geo-location, disabling of preventative controls such as S3 block public access, or API call patterns consistent with an attempt to discover misconfigured bucket permissions.

  - :book: [Using Amazon GuardDuty to Protect Your S3 Buckets](https://aws.amazon.com/blogs/aws/new-using-amazon-guardduty-to-protect-your-s3-buckets/)

- [ ] :green_circle: **Glacier Vault Lock:** Immutable policy for enforcing controls such as "write once read many" (WORM).

  - :book: [Amazon S3 Glacier Vault Lock](https://docs.aws.amazon.com/amazonglacier/latest/dev/vault-lock.html)

- [ ] :green_circle: **Amazon Macie:** Macie automates the discovery of sensitive data, such as personally identifiable information (PII) and intellectual property, to provide you with a better understanding of the data that your organization stores in Amazon S3.

  - :book: [What is Amazon Macie?](https://docs.aws.amazon.com/macie/latest/user/what-is-macie.html)

[:arrow_up: back to top](#table-of-contents)

---

## Performance

- [ ] :yellow_circle: **Partitioning strategy:** Consider storing your data in a fit-for-purpose directory structure for better read and write performance.

  - :book: [Best Practices Design Patterns: Optimizing Amazon S3 Performance](https://docs.aws.amazon.com/AmazonS3/latest/dev/optimizing-performance.html)
  - :book: [Amazon S3 Performance Tips & Tricks](https://aws.amazon.com/blogs/aws/amazon-s3-performance-tips-tricks-seattle-hiring-event/)

- [ ] :green_circle: **S3 Select:** Enables applications to retrieve only a subset of data from an object by using simple SQL expressions.

  - :book: [Selecting content from objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/selecting-content-from-objects.html)

- [ ] :green_circle: **Glacier Select:** Allows you to to perform filtering directly against a Glacier object using standard SQL statements.

  - :book: [Amazon S3 Glacier features](https://aws.amazon.com/glacier/features/#amazon-glacier-select)

[:arrow_up: back to top](#table-of-contents)

---

## Cost

- [ ] :red_circle: **Intelligent-Tiering:** Intelligent-Tiering storage class is designed to optimize costs by automatically moving data to the most cost-effective access tier.

  - :book: [Amazon S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)

- [ ] :green_circle: **Inventory:** Outputs files that list your objects and their corresponding metadata on a daily or weekly basis. Can be useful to setup your own lifecycle management or for big data jobs that require S3 object metadata without having to call individual object APIs.

  - :book: [Amazon S3 inventory](https://docs.aws.amazon.com/AmazonS3/latest/dev/storage-inventory.html)

[:arrow_up: back to top](#table-of-contents)

---

## Contributing

Open an issue or a pull request to suggest changes or additions.

[:arrow_up: back to top](#table-of-contents)
