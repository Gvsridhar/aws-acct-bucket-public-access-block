# aws-acct-bucket-public-access-block
AWS CLI command to impose public access block on the AWS account
In order to avoid any incorrect policy definition at the S3 bucket level, public bucket ACL or Object ACL, its good practice to have global public access block policy defined at the account level. 
This blocks from creating any public access and acts as checks and balance to avoid data leakage.

Public access block can be done at account level or at bucket level

AWS cli command for public access block at the account level

aws s3control put-public-access-block --account-id ************ --public-access-block-configuration BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true

AWS cli command for public access block at the bucket level

aws s3api put-public-access-block --bucket bucketname1 --public-access-block-configuration BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true
