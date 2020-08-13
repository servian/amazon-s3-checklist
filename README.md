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

All items in the **Amazon Redshift Checklist** are required for the majority of the projects, but some elements can be omitted or are not essential. We choose to use 3 levels of flexibility:

- :o: means that the item is **recommended** but can be omitted in some particular situations.
- :interrobang: means that the item is **highly recommended** and can eventually be omitted in some really particular cases.
- :bangbang: means that the item **can't be omitted** by any reason.

Some resources possess an emoticon to help you understand which type of content / help you may find on the checklist:

- :book: documentation or article
- :wrench: online tool / testing tool
- :video_camera: media or video content

---

## Management

- [ ] :bangbang: **Bucket Policy vs IAM Policy vs ACL:** Setting up the right access controls for your S3 buckets and objects.

  - :book: [IAM Policies and Bucket Policies and ACLs! Oh, My! (Controlling Access to S3 Resources)](https://aws.amazon.com/blogs/security/iam-policies-and-bucket-policies-and-acls-oh-my-controlling-access-to-s3-resources/)

- [ ] :interrobang: **Lifecycle policy:** Implement lifecycle needs according to frequency, durability, and latency requirements.

  - :book: [Object lifecycle management](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html)

- [ ] :o: **Object tagging policy:** Object tagging is a powerful mechanism to attach metadata to objects managed in S3.

  - :book: [Object tagging](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-tagging.html)

[:arrow_up: back to top](#table-of-contents)

---

## Availability

[:arrow_up: back to top](#table-of-contents)

---

## Monitoring

[:arrow_up: back to top](#table-of-contents)

---

## Security

[:arrow_up: back to top](#table-of-contents)

---

## Performance

[:arrow_up: back to top](#table-of-contents)

---

## Cost

[:arrow_up: back to top](#table-of-contents)

---

## Contributing

Open an issue or a pull request to suggest changes or additions.

[:arrow_up: back to top](#table-of-contents)
