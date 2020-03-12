---
title: "AWS Dev S3"
excerpt: "Demo on AWS S3 service"
toc: true
---

# Python API example

## list object in bucket using Client API

```python
# import sdk
import boto3
# connect to s3
s3client = boto3.client('s3')
# connect to a bucket
response = s3client.list_objects_v2(Bucket='{uniquebucketname}')
# list all objects in the bucket
for content in response['Contents']:
    print(content['Key'], content['LastModified'])
```

## list object in bucket using Resource API

```python
# import sdk
import boto3
# connect to s3 resources
s3 = boto3.resource('s3')
```

# AWS Console example

## Static Website

