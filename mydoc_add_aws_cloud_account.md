---
title: How to setup a CloudCoreo WebUI AWS Cloud Account
tags:
keywords: ""
last_updated: "October 30, 2016"
summary: How to add a AWS Cloud Account to CloudCoreo WebUI to access your AWS account.
published: true
sidebar: faq_sidebar
permalink: faq_add_aws_cloud_acct.html
folder: faq
toc: false
---

### Details  
The CloudCoreo WebUI can access an AWS account and manage its assets. This is possible once a CloudCoreo WebUI Cloud Account has been set up for an AWS account.

When a Cloud Account is set up CloudCoreo WebUI creates a IAM Role called CloudCoreoAssumedRole assigned to your account. And attaches to CloudCoreoAssumedRole a policy CloudCoreoAssumedRolePolicy which will allow CloudCoreo WebUI to perform its necessary operations in your AWS account. After a Cloud Account has been set up the enabling User is no longer necessary and may be removed. It is recommended that the user is removed as best security practice.

There is a video on this process [HOW TO CREATE AN AWS USER](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html)

### Adding a AWS Cloud Account to CloudCoreo WebUI  

To Adding a AWS Cloud Account to to CloudCoreo WebUI perform the following:

1. Create a temporary IAM user in your AWS account
	  1. Follow instructions: [Creating an IAM User in Your AWS Account](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html)
	  2. The name of the user created is arbitrary will use for reference MyCloudCoreoUser
	  3. You may capture the AWS key at the end of the user creation process or in step 4.
2. Create a custom policy for the IAM  
	1.  Use the script at end of article to create the custom policy
	2. Follow instructions: [Creating a New Policy](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html), use the create your own policy option.
	3. The name of the policy is arbitrary here we use MyCloudCoreoPolicy for reference.
3. Attach the new MyCloudCoreoPolicy policy to the MyCloudCoreoUser usesr.
	1. In the IAM console selected users from the left navigation bar.
	2. From the list of users select the newly created MyCloudCoreoUser.
	3. Select the permissions tab.
	4. click the Attach Policy button.
	5. To locate the custom policy were created use the filter box and enter MyCloudCoreoPolicy.
	6. Select the policy MyCloudCoreoPolicy, on selected click the Attach Policy button.
4. Generate an AWS key for this user
	1. if you have not already done this in step one follow the instructions [Managing Access Keys for IAM Users](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) Follow the instructions for creating keys in the section Creating, Modifying, and Viewing Access Keys (AWS Management Console).
	2. Either download the file or copy the Access Key ID and Secret Access Key from the interface.
5. Add the AWS account to the CloudCoreo WebUI using this newly generated key
	1. In CloudCoreo WebUI, select Settings from the left navigation bar.
	2. Select the Cloud Accounts tab.
	3. Click the ADD NEW button.
	4. Create the account use any nick name, paste the IAM Access Key ID and Secret Access Key you obtained in step 4.
	5. Click Create, if the process succeeds, the nickname for the Cloud Account will now appear.
6. Remove the temporary AWS IAM user
	1. In the IAM console selected users from the left navigation bar.
	2. From the list of users select the MyCloudCoreoUser user.
	3. Select the permissions tab.
	4. Detach the MyCloudCoreoPolicy policy.
	5. delete access keys.
	6. Delete user.

AWS Cloud Account Setup Policy
``` javascript
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "iam:GetUser",
        "iam:CreatePolicy",
        "iam:GetPolicy",
        "iam:CreateRole",
        "iam:GetRole",
        "iam:AttachRolePolicy"
      ],
      "Resource": "*"
    }
  ]
}
```