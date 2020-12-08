# IAM

[<- Back to list](../README.md)

## Create demo resources
Use CloudFormation to create 1 EC2 instance and 2 S3 Buckets
```
aws cloudformation create-stack --stack-name iam-demo --template-body file://iam.yml --parameters file://parameters.json --profile <PROFILE>
```
## Try to access resources
Login with SSH to EC2 instance, try to use from CLI
```
aws s3 ls
```
you will receive an error message, is ok!

## Create a new Policy
Using the Visual Editor to create a Policy with access to S3, at least the s3:ListAllMyBuckets permission.

## Create a IAM Role
Create a new IAM Role with the previous Policy associated.

## Assign IAM
Assign the Role to EC2 instance and try to rerun the previous command

## Inspect credential generations
Use the following command to see what is included in Instance Metadata
```
 TOKEN=`curl -X PUT "http://169.254.169.254/latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 21600"` && curl -H "X-aws-ec2-metadata-token: $TOKEN" http://169.254.169.254/latest/meta-data/iam/info/
```
the SDK will do ad sts:AssumeRole for the InstanceProfile

## Clean environment
Remove Role, Policy and delete the CloudFormation stack


