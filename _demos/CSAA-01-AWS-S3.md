---
title: "AWS S3"
excerpt: "Dome on AWS S3 service"
---

# Bucket creation and usage

## Create a bucket with az cli

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

## Upload website

## Create versioning