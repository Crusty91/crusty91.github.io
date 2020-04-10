---
title: "AWS FAQ"
excerpt: "Frequently Asked Question during AWS Trainings"
toc: true
---

## Databases

### What are the file format supported by S3 when performing a data migration?
> When performing a database migration with S3 as source or destination, the file format on S3 is csv.

### Can I migrate from another managed db service (like Heroku)?
> If you don't have full admins credentials, you will have to perform an export/import to load your DB content into an RDS instance. Depending on your scenario, you can leverage Lambda functions to perform it on a regular basis, therefore facilitate the full migration when you are ready.

## S3

### Why should S3 buckets names be globally uniques?
> When creating a Bucket, a virtual host style URL is created to access its content, which is not linked to the region or account. As this URL has to be unique, the bucket name has to be globally unique too.

### Can I search S3 object on the metadata only?
> Short answer, No. If you want to be able to look for objects based on metadata whitouth downloading the whole object, the most effective way is to build an event based architecture with a Lambda function and a DynamoDB table. whenever a new object is pushed whithin the bucket, the function will asynchronously extract the meta-data and push it into a DynamoDB table.

### How can I expose S3 files to user for upload/download purpose (whithout CloudFront)?
> There is 2 ways you can do it securly:
>   - You can use signed URLs. Whenever a user need access to object whithin an S3 bucket, you generated a signed url he can directly use.
>   - You can integrate levarage roles and integrate with SKS to generate a token so the user can upload/download S3 objects.

## Networks

### I'm used to Telnet to debug network connections issue. Can I do it on AWS?
> Whereas you may be able to use telnet within an EC2 instance, the best way to diagnose connection issue is to activate VPC Flow Logs.

### How Am I protected against DDos Attacks?
> You can leverage different services to protect your infrastructure agains Distributed Denial Of Service attack:
> [AWS Shield](https://aws.amazon.com/shield/?nc1=h_ls) Standard: free service integrated with your AWS ressources that give a protection against most common DDos Attack
> AWS Shield Advanced: Give a better protection on specifics services (ELB, CloudFront, Route53...), and also give you access to AWS WAF
> [AWS Web Application Firewall](https://aws.amazon.com/waf/?nc1=h_ls) is a web application firewall that helps protect your web applications or APIs against common web exploits that may affect availability, compromise security, or consume excessive resources.

### If I activate VPC Endpoint on an S3 Bucket, is public access disabled?
> No, you have to configure ACL or Resource Policy to do that. A good example can be found [here](https://aws.amazon.com/premiumsupport/knowledge-center/block-s3-traffic-vpc-ip/)

## Normes

### Is AWS Compliant to a specific norm?
> If you want to validate if AWS is compliant with a specific norme, you can check on [The compliance programs page](https://aws.amazon.com/fr/compliance/programs/)

### Where can I find specific report on compliance to provide in case of an Audit?
> All audit results from AWS are available on [AWS Artifcat](https://console.aws.amazon.com/artifact/home)

### Where can I see the list of services compliant to a specific norm?
> You can check on the [Services in scope](https://aws.amazon.com/fr/compliance/services-in-scope/) page. You can filter per norm and see which services you can use while stayong compliant with your requirements.