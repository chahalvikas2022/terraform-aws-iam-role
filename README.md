# # 🏗️ Terraform-AWS-iam-role

[![vikas](https://img.shields.io/badge/Made%20by-vikas-blue?style=flat-square&logo=terraform)]
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Terraform](https://img.shields.io/badge/Terraform-1.13%2B-purple.svg?logo=terraform)](#)
[![CI](https://github.com/chahalvikas/terraform-aws-ec2/actions/workflows/ci.yml/badge.svg)](https://github.com/chahalvikas/terraform-aws-ec2/actions/workflows/ci.yml)

> 🌩️ **A production-grade, reusable AWS Ec2 module by [vikas]**
> Designed for reliability, performance, and security — following AWS networking best practices.
---

## 🏢 About OpsStation

**vikas** delivers **Cloud & DevOps excellence** for modern teams:
- 🚀 **Infrastructure Automation** with Terraform, Ansible & Kubernetes
- 💰 **Cost Optimization** via scaling & right-sizing
- 🛡️ **Security & Compliance** baked into CI/CD pipelines
- ⚙️ **Fully Managed Operations** across AWS, Azure, and GCP



---

## 🌟 Features

- ✅ Creates and manages **AWS IAM Roles** with customizable trust policies
- ✅ Supports **inline** and **managed policy attachments**
- ✅ Allows **assume role policy** customization for services or federated identities
- ✅ Integrates seamlessly with **AWS IAM Policies**, **Users**, and **Groups**
- ✅ Optional creation of **IAM Instance Profiles** for EC2 or ECS services
- ✅ Supports **role path**, **permissions boundary**, and **max session duration** configurations
- ✅ Enables tagging and naming conventions through the **Labels module**
- ✅ Follows AWS best practices for **least-privilege** and **secure access control**
- ✅ Fully compatible with other **OpsStation Terraform modules**

---
## 🚀 Usage Example

```hcl

module "iam-role" {
  source             = "git::https://github.com/chahalvikas2022/terraform-aws-iam-role.git"
  name               = "iam"
  environment        = "test"
  assume_role_policy = data.aws_iam_policy_document.default.json
  policy_enabled     = true
  policy             = data.aws_iam_policy_document.iam-policy.json
}
```

### 🔐 Outputs (AWS IAM Role Module)

| Name                    | Description                                                                 |
|--------------------------|------------------------------------------------------------------------------|
| `id`                     | The unique identifier (ID) of the created **IAM Role**.                     |
| `arn`                    | The ARN (Amazon Resource Name) of the created **IAM Role**.                 |
| `name`                   | The name of the created **IAM Role**.                                       |
| `path`                   | The path to the IAM Role within AWS IAM.                                   |
| `create_date`            | The date and time when the IAM Role was created.                            |
| `unique_id`              | The stable and unique string identifying the IAM Role.                      |
| `role_policy_arns`       | A list of attached **managed policy ARNs** associated with the IAM Role.    |
| `assume_role_policy`     | The **trust policy** document that grants entities permission to assume the role. |
| `permissions_boundary`   | The ARN of the **permissions boundary policy** attached to the IAM Role (if any). |
| `instance_profile_arn`   | The ARN of the associated **IAM Instance Profile** (if created).            |
| `tags`                   | A mapping of **tags** assigned to the IAM Role.                             |

### ☁️ Tag Normalization Rules (AWS)

| Cloud | Case      | Allowed Characters | Example                            |
|--------|-----------|------------------|------------------------------------|
| **AWS** | TitleCase | Any              | `Name`, `Environment`, `CostCenter` |

---

### 💙 Maintained by [vikas]
> vikas — Simplifying Cloud, Securing Scale.
