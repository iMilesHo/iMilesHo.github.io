---
layout: post
title: AWS Sign-In
date: 2024-01-17 20:10:10
description: About AWS Sign-In
tags: Shell
categories: posts
giscus_comments: true
related_posts: true
---


# AWS Sign-In

Based on what type of account you are using, you have different ways to sign in.

Here are the 5 ways to sign in:
- Sign in to the AWS Management Console
- Sign in to the AWS access portal
- Sign in as a federated identity
- Sign in through the AWS Command Line Interface
- Sign in with AWS Builder ID

## Terminology regarding AWS Sign-In
We can see detials in [AWS Terminology](https://docs.aws.amazon.com/signin/latest/userguide/terminology.html)
- Administrator
- Account
- credentials
- Corporate credentials
## User Types
We can see detials in [AWS User Types](https://docs.aws.amazon.com/signin/latest/userguide/user-types-list.html)
- Root user: create by you.
  
- IAM user: Administrator or help desk employee provided within an AWS account
  
- IAM Identity Center user: 
  - Regardless of the identity provider, users in IAM Identity Center sign in using the AWS access portal, which is a specific sign-in URL for their organization. IAM Identity Center users can't sign in through the AWS Management Console URL.
  - An IAM Identity Center user is a member of AWS Organizations and can be granted access to multiple AWS accounts and applications through the AWS access portal. 
  - You received an email from your administrator or no-reply@login.awsapps.com with an AWS access portal URL.
  - You use the same credentials to sign-in to both corporate systems and the AWS access portal, and your AWS account is part of AWS Organizations.

- Federated identity:
  A user who signs in using an external identity provider (IdP). Access your AWS account or resources with third party credentials like Login with Amazon, Facebook, or Google. Use the same credentials to sign in to corporate systems and AWS services and you use a custom company portal to sign-in to AWS.
- AWS Builder ID: 
  A personal profile where you specifically sign in to the AWS service or tool that you want to access. 

## AWS Management Console
### Sign in to the AWS Management Console as the root user

Here is the steps to sign in to the AWS Management Console as the root user:
1. Open the AWS Management Console at https://console.aws.amazon.com/
2. Choose Root user.
3. follow the prompt.


#### Tasks that require root user credentials

1. tasks about your account settings, such as changing your password or contact information.
2. tasks about managing your IAM identity center users's permissions.
3. others


### Sign in to the AWS Management Console as an IAM user

1. Open the AWS Management Console at https://console.aws.amazon.com/.

2. The main sign-in page appears. Choose IAM user, enter the account ID (12 digits) or alias, and select Next...

## AWS access portal
### Sign in to the AWS access portal
A user in IAM Identity Center is a member of AWS Organizations. A user in IAM Identity Center can access multiple AWS accounts and business applications by signing in to the AWS access portal with a specific sign-in URL. For more information about the specific sign-in URL, see [AWS access portal.](https://docs.aws.amazon.com/signin/latest/userguide/sign-in-urls-defined.html#access-portal-url)

Before you sign in to an AWS account as a user in IAM Identity Center, gather the following required information.
- Corporate user name
- Corporate password
- Specific sign-in URL





