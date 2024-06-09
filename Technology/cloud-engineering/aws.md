# AWS

## Overview

AWS (Amazon Web Services) is a cloud services provider first launched in 2006. Cloud computing is the delivery of computing power over the internet on a pay-as-you-go basis. It's essentially renting the usage of another computer over the internet. Services include database storage, virtual servers, analytics, networking, etc

## IAM

Identity and Access Management controls access to your AWS resources. Namely, who can access (authentication) and what they can do (authorisation). It's considered best practice to work in an IAM account and not the root account. The root account has access to everything and so is particularly vulnerable if it's ever compromised.

A `User` is an identity with certain permissions that you can assign to a user of your resources within your organisation. Users can be categorised into `User groups`.

A `Role` is an identity with specific permissions (like a user) but not associated with a specific person and is temporarily assumed. Roles also do not have credentials (automatically deploys them to resources) so they don't have to be hard-coded.

A `Policy` is used to define what permissions a particular entity or resource has. Only the permissions are specified in the policy and then they can be attached to any user or role.

## S3

Simple Storage Service was the very first AWS product. It's general purpose file storage and can store any type of file

## EC2

Elastic Compute Cloud allows you to build a virtual computer in the cloud. You can choose the OS, memory, and computing power and then rent this as you use it. It's most commonly used as servers for web applications.

## Lambda

Lambda functions run code without a server and is instead based on events.
Many computing jobs are very short and so don't require a server to always be running. You don't anythin when the code isn't running

## Redshift

Redshift is a data warehouse which stores data from multiple sources to be analysed together. The data is structured allowing for it ot be queried.

## Glue

Glue is a serverless tool that performs ETL on data to simplify data prep for analytics. It can connect to AWS data sources and perform `jobs` on the data.
