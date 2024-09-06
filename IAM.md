# Idenity and Access Management (IAM)

## What is IAM
- Allows you to manage users and their level of access to the AWS Console
    - Create users and assign permissions to those users
    - Create groups and roles
    - Control access to AWS resources


## Securing a root account
1. Enable MFA on the root account.
2. Create an admin group for administrators.
3. Assign appropiate permissions to the admin group
4. Create user accounts for administrators.
5. Add users accounts to the admin group

# Managing IAM Credentials

- IAM is universal - does not apply to a specific region

## Root Account:
- Default account created when you first setup your AWS account and it has complete admin access. Secure it as soon a possible and **do not** use it to login day-to-day.

## Users
- A physical person
- Users have no permissions when first created
- Can belong to multiple groups
- Need not belong to any group at all
- New users have no permissions when they are first created

## Groups 
- Contains users
- Users should inherit permissions from groups
- IAM policy documents should be applied to groups, not users
- Group cannot belong to another group

## Roles
- Internal to AWS
- Allows one AWS resource to access another AWS resouce

**Amazon Cognito provides authentication, authorization, and user management for your web and mobile apps.**

# IAM Policy Documents

## Permissions with IAM
- Permissions are assigned using policy documents (made up of JSON)
- Key/Value Pairs

- Policy document example for full admin access: 
    - Effect: Allow or Deny
    - Principal: To who the policy applies to
    - Action:  What the user can do
    - Reource:  What resource is impacted

- IAM Policy Documents can be assigned to Groups, Users, Roles

## Principle of Least Privilege
- Only assign a user the minimm amount of privileges they need to do their job


# MFA ( Multi Factor Authentication)
- MFA = passwd + security device you own
- benefit - if psswd is hacked, account is not compromised

**To access AWS, you have three options :**

 1. AWS Management Console (protected by password + MFA)
 2. AWS Command Line Interface (CLI) : protected by access keys
 3. AWS Software Developer Kit (SDK) - for code : protected by access keys
 
 - Access Keys are generated through the AWS Console
 - Users manage their own access keys
 - Access Keys are secret, just like a password
 - Access Key ID = username and Secret Access Key = password
 - You cannot use the access key ID and secret access key to login to the console. They are used to access AWS via the API or command line.


# AWS CLI
- tool to enable you to interact with AWS services using command line
- direct acces to public APIs

# AWS CloudShell
- web-based application by AWS, which you can easily use to manage your AWS services
- easier to use than CLI