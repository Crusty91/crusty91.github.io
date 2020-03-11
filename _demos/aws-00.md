---
title: "AWS Demo"
excerpt: "Demo on AWS services"
---

# Configure CLI

#. [Install the cli](https://aws.amazon.com/fr/cli/)
#. Retrieve a valid access key from aws console
#. Configure the access key:
```bash
aws configure
```
3. Use it!
```bash
aws s3 ls
```

ls ~/.aws/
 - config:
    * region
    * output format
 - credentials
    * access key
    * access secret

# Connect to Console

# Configure SDK

## Python

region specified in file system config file.

[Boto3 QuickStart](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/quickstart.html)

## Java

region is specified in code

```java
import com.amazonaws.regions.Region;
import com.amazonaws.regions.Regions;
// ...
Region region = Regions.getCurrentRegion();
// For local testing only
if (region == null) {
    region = Region.getRegion(Regions.US_WEST_1);
}
```

## .Net C#

region specified in app.config
```xml
<configuration>
  <configSections>
    <section name="aws" type="Amazon.AWSSection, AWSSDK.Core"/>
  </configSections>
  <aws region="us-west-2">
    <logging logTo="Log4Net"/>
  </aws>
</configuration>
```