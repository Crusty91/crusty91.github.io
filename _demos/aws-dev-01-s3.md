---
title: "AWS Dev S3"
excerpt: "Demo on AWS S3 service"
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
# connect to a bucket
mybucket = s3.Bucket('{uniquebucketname}')
# list all objects in the bucket
for object in mybucket.objects.all():
    print(object)
# download a file
s3.Bucket('{uniquebucketname}').download_file('{myfile}')
```

## Versionning

[Demo of versionning with S3]({% link _demos/aws-csaa-01-s3.md %}#create-versioning)