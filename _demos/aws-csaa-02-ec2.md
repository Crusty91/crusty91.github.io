---
title: "AWS CSAA EC2"
excerpt: "Demo on AWS EC2 instance"
toc: true
sidebar:
    nav: "aws"
---

## AWS Console

### Create a website with user data
1. Launch an EC2 instance
    1. Select Amazon Linux
    1. Select t2.micro
    1. Assign public IP
    1. Fill User Data
```bash
#!/bin/bash
yum update -y
yum install httpd -y
service httpd start
chkconfig httpd on
cd /var/www/html
hostname=$(curl -s http://169.254.169.254/latest/meta-data/public-hostname)
echo "<html><h1>Hello Students Welcome To My Webpage on ${hostname}</h1></html>" > index.html
```
    1. Storage default
    1. Tag Name: Website
    1. Select Security group with http enabled from everywhere
    1. Launch instance
1. Wait
1. Open the Public DNS name from AWS Console
1. What if user-data is not working?
    1. Open ssh connection to ec2
```bash
cat /var/log/cloud-init.log
cat /var/log/cloud-init-output.log
```
