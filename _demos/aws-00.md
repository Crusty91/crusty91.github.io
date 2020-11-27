---
title: "AWS Demo"
excerpt: "Demo on AWS services"
toc: true
sidebar:
    nav: "aws"
---

## Configure CLI

1. [Install the cli](https://aws.amazon.com/fr/cli/)
1. Retrieve a valid access key from aws console
1. Configure the access key:
```bash
aws configure
```
1. Use it!
```bash
aws s3 ls
```

If you want to check your local configuration, it is located in the directory *[~/.aws/](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)*:
- **config**: *configuration pour l'utilisation du cli aws.* 
   * region par defaut
   * format de sortie des commandes
- **credentials**: *configuration des différentes acces key pour se connecter a aws.*

## Connect to Console

## Configure SDK

### Python

region specified in file system config file.

[Boto3 QuickStart](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/quickstart.html)

### Java

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

### .Net C#

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