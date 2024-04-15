---
title : "5. Create IAM Policy ``aws_iam_policy``"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---



An ***[AWS IAM policy](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)*** is like a set of rules that decide who can do what in the digital world of AWS.

These rules help make sure that people or programs can only get to the things they need and can't touch anything they shouldn't.

Here is the IAM Policy for `AllowS3Access`:

```hcl
resource "aws_iam_policy" "allow_s3_access" {
    name = "AllowS3Access"
    description = "Allow Kathy to access specific S3 resources"
    policy = jsonencode({
        Version = "2012-10-17"
        Statement = [
            {
                Action = [
                    "s3:ListBucket",
                    "s3:GetObject",
                    "s3:PutObject"
                ]
                Effect = "Allow"
                Resource = [
                    "arn:aws:s3:::test-bucket-for-kathy",
                    "arn:aws:s3:::test-bucket-for-kathy/*"
                ]
            }
        ]
    })
}
```
<details>
<summary>Code explanation</summary>

- **`AllowS3Access` :** It is the name of the policy.
- **`description` :** A meaningful description to tell more about the policy
- **`policy` :** A Json string containing all the ***Actions*** and ***Resources***
- **`Version = "2012-10-17"`**: This line indicates the policy language version. In this case, it is the 2012-10-17 version.
- **`Statement = [...]`:** This is an array of policy statements. In this example, there's only one statement that is defined as follows:
- **`Action = [...]` :** This lists the actions that are allowed by the policy. In this case, it includes:
- **`"s3:ListBucket"`:** Listing the contents of a bucket.
- **`"s3:GetObject"`:** Retrieving an object from the bucket.
- **`"s3:PutObject"`:** Uploading an object to the bucket.
- **`Effect = "Allow"`:** This indicates that the actions listed above are allowed by the policy.
- **`Resource = [...]`:** This specifies the resources the policy applies to. In this example, there are two resources:
- **`"arn:aws:s3:::test-bucket-for-kathy"`:** The Amazon Resource Name (ARN) of the S3 bucket is "test-bucket-for-kathy". This allows the policy to apply to the bucket itself.
- **`"arn:aws:s3:::test-bucket-for-kathy/*"`:** This allows the policy to apply to all objects within the "test-bucket-for-kathy" bucket.
</details>
1. To create the policy, run the above code: simply run `terraform plan` and `terraform apply` command
2. After running the Terraform code, you can verify the user by going into the **AWS console -> IAM -> Access Management -> Policies**


3. Click on the `AllowS3Access` Policy and you will find all the details related to that policy.
![AWS IAM S3 Policy with Read, List and Write permission](/workshop1/allows3access-policy.png)