---
layout: post
title: IAM and IAM Identity Center
date: 2024-01-18 18:18:10
description: About AWS Sign-In
tags: Tools AWS
categories: posts
giscus_comments: true
related_posts: true
---

## [What is IAM?](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. With IAM, you can centrally manage permissions that control which AWS resources users can access. You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources.

### IAM gives you the following features:

- Shared access to your AWS account
You can grant other people permission to administer and use resources in your AWS account without having to share your password or access key.

- Granular permissions
You can grant different permissions to different people for different resources.

- Secure access to AWS resources for applications that run on Amazon EC2
You can use IAM features to securely provide credentials for applications that run on EC2 instances. These credentials provide permissions for your application to access other AWS resources. Examples include S3 buckets and DynamoDB tables.

- Multi-factor authentication (MFA)
You can add two-factor authentication to your account and to individual users for extra security.

- Identity federation
You can allow users who already have passwords elsewhere—for example, in your corporate network or with an internet identity provider—to get temporary access to your AWS account.

- Identity information for assurance
If you use AWS CloudTrail, you receive log records that include information about those who made requests for resources in your account. That information is based on IAM identities.


## [What is IAM Identity Center?](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html)


AWS IAM Identity Center is the recommended AWS service for managing human user access to AWS resources. It is a single place where you can assign your workforce users, also known as workforce identities, consistent access to multiple AWS accounts and applications.

With IAM Identity Center, you can create or connect workforce users and centrally manage their access across all their AWS accounts and applications. You can use multi-account permissions to assign your workforce users access to AWS accounts. You can use application assignments to assign your users access to AWS managed and customer managed applications.

### IAM Identity Center includes the following core capabilities and features:

- Manage workforce identities
Human users who build or operate workloads in AWS are also known as workforce users, or workforce identities. Workforce users are employees or contractors who you allow to access AWS accounts in your organization and internal business applications.

- Manage instances of IAM Identity Center
IAM Identity Center supports two types of instances: organization instances and account instances. An organization instance is the best practice. It's the only instance that enables you to manage access to AWS accounts and it's recommended for all production use of applications. An organization instance is deployed in the AWS Organizations management account and gives you a single point from which to manage user access across the AWS environment.

- Manage access to multiple AWS accounts
With multi-account permissions, you can plan for and centrally implement permissions across multiple AWS accounts at one time without needing to configure each of your accounts manually. 

- Manage access to applications
IAM Identity Center enables you to simplify application access management. With IAM Identity Center, you can grant your workforce users in IAM Identity Center single sign-on access to applications.


### What is the difference between IAM and IAM Identity Center?

AWS IAM Identity Center, formerly known as AWS Single Sign-On (SSO), is a different service from AWS Identity and Access Management (IAM), although they both deal with identity and access control within AWS environments. Here are the key differences.


#### AWS Identity and Access Management (IAM):

- IAM allows you to manage access to AWS services and resources securely. Using IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources.
- IAM is focused on providing fine-grained access control to resources in a single AWS account, with the ability to extend to multiple accounts if necessary.
- IAM policies define permissions and can be applied to users, groups, or roles within AWS to control what actions a user or system can perform on which resources.
- IAM is a fundamental component of AWS and does not support federation with external identity providers out of the box; additional setup is needed for that.

#### IAM Identity Center (formerly AWS SSO):

- IAM Identity Center is designed to simplify the process of managing SSO access to multiple AWS accounts and applications. It allows users to sign in to a central portal with a single set of credentials and access all of their assigned AWS accounts and third-party applications.
It integrates with external identity providers, such as Microsoft Active Directory, Azure AD, and Okta, making it easier to manage users across an organization.
- IAM Identity Center provides a user portal where end-users can find and access all their assigned AWS accounts, cloud applications, and custom applications in one place.
- It allows for centralized control over who can access what across multiple AWS accounts within AWS Organizations. It can also set up SSO for SAML 2.0 compatible services.

In summary, IAM is a core AWS service for access control within AWS accounts, while IAM Identity Center extends this capability to provide an easy-to-use SSO solution that supports centralized access management across multiple AWS accounts and business applications. IAM Identity Center is particularly useful for organizations that need a unified user experience and centralized permission management across a broad and diverse environment.

