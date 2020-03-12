---
title: "AWS CSAA S3"
excerpt: "Demo on AWS S3 service"
toc: true
---

# AWS CLI

## Create a bucket

In this demo, we will create a bucket and upload a simple file to it using az-cli

1. Create the bucket
```bash
aws s3 mb s3://{MyUniqueBucketName}
```
1. View the bucket
```bash
aws s3 ls
```
2. Upload a file
```bash
aws s3 cp {myfile} s3://{MyUniqueBucketName}
```
2. View your bucket's content
```bash
aws s3 ls s3://{MyUniqueBucketName}
```
3. Download a file
```bash
aws s3 cp s3://{MyUniqueBucketName}/{myfile}
```

# AWS Console

## Static website

## Create versioning

1. Create a Bucket
1. Enable Versioning
    a. Go to properties
    a. Open Versioning property
    a. Click on enable versioning and save
1. Upload an object
1. Modify the object