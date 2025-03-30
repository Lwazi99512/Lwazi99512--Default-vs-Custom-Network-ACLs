# Lwazi99512--Default-vs-Custom-Network-ACLs
Lwazi99512/-Default-vs-Custom-Network-ACLs
# AWS IAM Security Project: Environment Access Control

![AWS IAM Logo](https://d1.awsstatic.com/logos/aws-logo-lockups/poweredbyaws/PB_AWS_logo_RGB_stacked_REV_SQ.91cd4af40773cbfbd15577a3c2b8a346fe3e8fa2.png)

## 📌 Project Overview
Implemented **AWS Identity and Access Management (IAM)** to create secure development and production environments with granular permissions. Key achievements:
- Created **tag-based access control** for EC2 instances
- Designed IAM policies using **JSON** to restrict destructive actions
- Established **user groups** with inherited permissions
- Tested policy enforcement through practical scenarios

## 🔧 AWS Services Used
- **IAM** (Users, Groups, Policies)
- **EC2** (Environment tagging: `production`/`development`)
- **AWS Account Alias** (Custom login URL)

## 🛠️ Key Implementations
### IAM Policy Design
```json
{
  "Effect": "Allow",
  "Action": "ec2:*",
  "Resource": "*",
  "Condition": {
    "StringEquals": {
      "aws:ResourceTag/ENV": "development"
    }
  }
}
