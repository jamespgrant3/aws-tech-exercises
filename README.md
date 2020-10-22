## VPC ##
  * make a private EC2 instance accessible through an ELB

  * peer two vpc's, allow two private EC2 instances to communicate.
    * ping the other ec2 instance

  * make a private EC2 instance communicate with S3 from within the VPC

  * make a private EC2 instance talk to SQS from within the VPC

## Lambda ##
  * create a Lambda that can describe your ec2 instances in a given region

  * create a Lambda that can be invoked on a private ec2 instance

  * todo:
    * think of scenarios that require the lambda to be attached to the VPC


## S3 ##
  * create an EC2 instance that can access S3 using a:
    * bucket policy
    * identity policy

  * setup replication to another region
    * todo: with kms key

  * using the CLI, write a file to a version enabled bucket. Update the file a few times, and get the object to fully delete

  * create an S3 hosted site

  * front an S3 hosted site with CloudFront, ensuring the bucket is not accessible directly

## EC2 ##
  * using the CLI, replicate an EBS volume across regions

## ELB ##
  * create an EC2 instance, fronted by an ELB, fronted by a CF distro. Update the ELB to only accept traffic from the CF distro.

## Helpers ##
To help with setting up a quick web server, here is a user data script from LA:

```
#!/bin/bash
yum update -y
yum install -y httpd
yum install -y wget
chkconfig httpd on
cd /var/www/html
wget https://raw.githubusercontent.com/linuxacademy/content-aws-csa2019/master/lab_files/03_compute/creating_an_ec2_instance/index.html
wget https://raw.githubusercontent.com/linuxacademy/content-aws-csa2019/master/lab_files/03_compute/creating_an_ec2_instance/catanimated.gif
wget https://raw.githubusercontent.com/linuxacademy/content-aws-csa2019/master/lab_files/03_compute/creating_an_ec2_instance/rainbow.gif
wget https://raw.githubusercontent.com/linuxacademy/content-aws-csa2019/master/lab_files/03_compute/creating_an_ec2_instance/penny.jpeg
wget https://raw.githubusercontent.com/linuxacademy/content-aws-csa2019/master/lab_files/03_compute/creating_an_ec2_instance/roffle.jpeg
wget https://raw.githubusercontent.com/linuxacademy/content-aws-csa2019/master/lab_files/03_compute/creating_an_ec2_instance/truffs.jpeg
wget https://raw.githubusercontent.com/linuxacademy/content-aws-csa2019/master/lab_files/03_compute/creating_an_ec2_instance/winkie.jpeg
service httpd start
```
