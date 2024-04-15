---
title : "6. Create IAM Role and Policy attachment"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---


IAM roles and policy attachments are crucial in AWS for maintaining secure and organized access control. They offer several advantages:

1. **Limited access**: IAM roles and policies ensure that only authorized individuals or programs have access to specific resources, enhancing security by preventing unauthorized actions.
2. **Centralized management**: Instead of managing access rights across various platforms or using disparate methods, IAM roles and policies provide a centralized platform for easy management and tracking of permissions.
3. **Reusable rules**: Similar to creating a universal rule for specific actions, IAM roles and policies enable the creation of reusable access rules, reducing redundancy and simplifying permission management.
4. **Flexible updates**: When access requirements change, IAM roles and policies facilitate easy updates without the need for manual adjustments across multiple resources.
5. **Secure sharing**: IAM roles and policies enable secure sharing of resources by granting controlled access to authorized individuals or entities, ensuring that shared access remains within predefined boundaries.

Here is the IAM Role and Policy Attachment for the `KathyRole` and `AllowS3Access` policies:

```hcl
# IAM Role and IAM Policy Attachment
resource "aws_iam_role_policy_attachment" "attach_s3_access" {
    policy_arn = aws_iam_policy.allow_s3_access.arn
    role = aws_iam_role.kathy_role.name
}    
```
Here is a detailed explanation of each policy:

To view `Permission Policy` of the role click on the `Permission` and then click on the `+` icon to expand the policy permission.

![Role-Policy-Permission-Image](/workshop1/permission-policy.png)
*IAM role permission policy description for `KathyRole`*
