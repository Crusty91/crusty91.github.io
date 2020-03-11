---
title: "AWS Demo"
excerpt: "Demo on AWS services"
---

# Configure CLI

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

