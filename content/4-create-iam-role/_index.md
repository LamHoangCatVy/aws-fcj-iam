---
title : "4. Create an IAM Role using `aws_iam_role`"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---

```hcl
resource "aws_iam_role" "kathy_role" {
    name = "KathyRole"
    assume_role_policy = jsonencode({
        Version = "2012-10-17"
        Statement = [
            {
                Action = "sts:AssumeRole"
                Effect = "Allow"
                Principal = {
                    Service = "ec2.amazonaws.com"
                }
            }
        ]
    })
}
```

Code explanation

- The above code will create an IAM role named `KathyRole`.
- To run the above code, simply run `terraform plan` and `terraform apply` commands.
- After running the Terraform code, you can verify the user by going into the **AWS console -> IAM -> Access Management -> Roles**

![IAM Role Created](/workshop1/iam-role.png)

Click on the `KathyRole` to view the details about the roles .e.g., Creation Date, ARN, Instance Profile ARN etc..

![KathyRole](/workshop1/kathy-role.png)
