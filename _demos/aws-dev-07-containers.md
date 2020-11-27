---
title: "Containers on AWS"
excerpt: "Demo on working with containers on AWS"
toc: true
sidebar:
    nav: "aws"
---

## Dockerfile

For the purpose of the demo, I'm using the app package [here](/assets/files/app.zip)
It is a simple express.js hello world app.

1. Open the package and go into the directory
1. To build the image, download the file and go to directory. Then run:
```bash
docker build -t test-image .
```
1. To view the image:
```bash
docker images
```
1. To test the image:
```bash
docker run -d -p 8080:8080 test-image
```
1. You can now open the url http://localhost:8080/ and view "Hello World".
1. To connect to the container:
```bash
docker exec -i -t test-image /bin/bash
```
1. To remove the container
    1. Stop the container
        ```bash
        docker stop test-image
        ```
    1. Delete the container
        ```bash
        docker container rm test-image
        ```

## ECS

## EKS