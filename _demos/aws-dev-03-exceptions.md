---
title: "AWS Dev Exceptions"
excerpt: "Demo on AWS Exceptions"
toc: true
---

In AWS sdk, you can catch exception from AWS services to act upon it.
Check the sdk documentation to check on available exception per resources.
Here are some example of exception catching.

## Python

```python
session = Session(profile_name="adminuser")
polly = session.client("polly")

try:
    # Request speech synthesis
    response = polly.synthesize_speech(Text="Hello world!", OutputFormat="mp3",
                                        VoiceId="Joanna")
except (BotoCoreError, ClientError) as error:
    # The service returned an error, exit gracefully
    print(error)
    sys.exit(-1)
```

[Source](https://docs.aws.amazon.com/polly/latest/dg/get-started-what-next.html)

## Java

```java
try {
    s3client.deleteBucket("{myuniquebucketname}");
} catch (AmazonServiceException e) {
    System.err.println("e.getErrorMessage());
    return;
}
```

## .Net C#

```c#
    try
    {
        GetObjectRequest request = new GetObjectRequest
        {
            BucketName = bucketName,
            Key = keyName
        };
        using (GetObjectResponse response = await client.GetObjectAsync(request))
        using (Stream responseStream = response.ResponseStream)
        using (StreamReader reader = new StreamReader(responseStream))
        {
            string title = response.Metadata["x-amz-meta-title"];
            responseBody = reader.ReadToEnd(); // Now you process the response body.
        }
    }
    catch (AmazonS3Exception e)
    {
        Console.WriteLine("Error encountered ***. Message:'{0}' when writing an object", e.Message);
    }
    catch (Exception e)
    {
        Console.WriteLine("Unknown encountered on server. Message:'{0}' when writing an object", e.Message);
    }
```

[source](https://docs.aws.amazon.com/AmazonS3/latest/dev/RetrievingObjectUsingNetSDK.html)