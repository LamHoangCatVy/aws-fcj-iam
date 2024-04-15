---
title : "3. Create an IAM User with `aws_iam_user`"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---

Let's start by creating an User which we call an IAM user. To keep our Terraform project code clean, I am going to create a file called iam-user.tf and put the following code inside the file.

```hcl
resource "aws_iam_user" "kathy" {
    name = "Kathy"
}
```
Code explanation
- The above code will create an IAM user named `Kathy`.
- To run the above code, simply run `terraform plan` and `terraform apply` commands.
- After running the terraform code, you can verify the user by going into the **AWS console -> IAM -> Access Management -> User**

![IAM User Created Image](/workshop1/iam-user.png)
