---
title : "2. Understanding IAM Roles and Policies"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---

If you are interest, I have a lesson recap for [IAM](https://catvy-learning-portfolio.vercel.app/overview-and-security/aws-iam).

If you're already familiar with IAM, here's a quick recap for this workshop. Anyway, it's important to understand the concept of IAM roles and IAM policies.

**1. IAM Roles**: a set of permissions that can be performed on AWS resources such as EC2, S3 Bucket, etc. In summary, using ***IAM Roles***, you can grant permission to

- User
- AWS Services

Here are some benefits that you get with the IAM roles -

- **Flexibility -** The IAM roles can be assigned to any IAM user or AWS resource, and you can customize the granularity of the IAM roles based on your needs.
- **Security -** IAM roles are very granular in nature, and hence, they always add an extra layer of security to your cloud infrastructure.
- **Scalability -** When you use Terraform to manage IAM roles, it becomes really scalable, and any developer can manage the roles from the code.

**2. IAM Policies -** It is a JSON formatted document that defines the permissions for IAM users as well as IAM roles. With the help of IAM policies, you can control what kinds of actions you can perform on specific A WS resources.

Here are two types of policies that exist:

- **Managed Policies -** IAM policies are managed policies that are administered by the account administrator.
- **Inline Policies -** These policies are directly embedded in the IAM user, IAM group, and IAM roles.