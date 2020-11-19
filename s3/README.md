# S3

[<- Back to list](../README.md)

## Create S3 Bucket
```
aws cloudformation create-stack --stack-name s3-demo --template-body file://s3.yml --profile \<PROFILE>
```

## Upload index.html
From the console upload the index.html file

## Visibility check
Try to access the website URL and analyze the actual permissions

## Make it public
Click on the file and edit the ACL, open the website URL and check that the index is now visible

## Upload logo
From the console upload the s3_logo.png file with the public ACL, refresh the website URL, the image is still not visible

## Enable Versioning
In the Bucket properties, enable Versioning. Take a look on the new option "List versions"

## Fix index.html
Open the local index.html and change the image name, upload it again, refresh the website URL

## Analyze versioning
With the "List versions" option enabled analyze how versioning works

## Clean environment
Delete files from S3 Bucket and delete the CloudFormation stack