# EC2

[<- Back to list](../README.md)

## Launch EC2 instance
From the console, in the EC2 service, launch a new instance with the standard Linux 2 AMI, use the following User-Data
```
#!/bin/bash
yum update -y
yum install -y httpd
systemctl enable httpd
echo "Apache HTTP Server installed!"
```
create a new SecurityGroup with the SSH access allowed, complete the wizard and launch the instance, use your existing Key Pair.

## Check
When the instance is running, right-click and from Monitoring menu get the System Log, it will need several minutes to be updated. You can also check the /var/log/messages using the SSH access

## Generate the AMI
Right-click and from 'Images and templates' create the new image, the operation will took several minutes to be completed

## Clean environment
Terminate the instance, remove the AMI, EBS Snapshots and the SecurityGroup