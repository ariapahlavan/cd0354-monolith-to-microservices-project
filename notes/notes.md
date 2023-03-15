# Bucket policy
Add bucket policy allowing other AWS services 
(Kubernetes) to access the bucket contents. 
You can use the policy generator tool to 
generate such an IAM policy.

```JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1625306057759",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:*",
            "Resource": "arn:aws:s3:::[bucket_name]"
        }
    ]
}
```

# CORS
Add the CORS configuration to allow the application
running outside of AWS to interact with your bucket.
```JSON
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "POST",
            "GET",
            "PUT",
            "DELETE",
            "HEAD"
        ],
        "AllowedOrigins": [
            "*"
        ],
        "ExposeHeaders": []
    }
]
```
