---
title: "AWS CSAA S3"
excerpt: "Demo on AWS S3 service"
toc: true
---

On this page, you'll find the demo related to the AWS S3 service.
You can, for example, see how a s3 bucket is created through command line, how to easily host a static website or configure versioning.

## AWS CLI

### Create a bucket

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

## AWS Console

### Static website
1. Create a Bucket
1. Upload your static website
1. Enable Static Website Hosting
    1. Go to properties
    1. Open **Static website hosting**
        1. Chose **use this bucket to host a website**
        1. Enter the name of the index page (e.g. *index.html*)
        1. If required, enter the name of the error page (e.g. *error.html*)
        1. Save
    1. In the same panel, you can see the Endpoint of your website
1. Open the endpoint: **You receive an error**. It is expected as the files are not publicly visible by default
    1. Go back to the list of files in your bucket
    1. Select all the files related to your web site
    1. In ***Actions***, select ***Make Public***
    1. Open your endpoint again, your website should appear!

[If you are interested, you can read more on the subject in AWS documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html)

---
### Create versioning

1. Create a Bucket
1. Enable Versioning.
    1. Go to properties,
    1. Open Versioning property,
    1. Click on enable versioning and save,
1. Upload an object and validate it is availables.
1. Modify the object and view the multiple version.
1. Soft-Delete the object and view the delete flag on latest version.
1. Delete all version of the object to delete it.

[If you are interested, you can read more on the subject in AWS documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectVersioning.html)
