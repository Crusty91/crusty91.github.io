---
title: "AWS Dev DynamoDB"
excerpt: "Demo on AWS DynamoDB"
toc: true
---

DynamoDB is a NoSQL managed database service from AWS.

## AWS Console

### Create New Table

In this example, we will create a table to store music information within a DynamoDB table.
We will use artist a Partition Key and Title as a Sort Key.

1. Open AWS Console
1. Open DynamoDB service
1. Create a Table
    1. Provide a value for table name: *music*
    1. Provide a value for partition key: *artist*
    1. Provide a value for sort key: *title*
1. Uncheck *Use default settings*
1. Secondary indexes
    1. Create one if desired: allow you to search by the index and improve performance
    1. Provide a value for partition key: *album*
    1. Provide a value for sort key: *rating*
1. Configure Auto-scaling or select on demand

### Create Items

1. Open the previously created table
1. Select *Items* tab
1. Click on *Create Item*
    1. artist: Dionysos
    1. title: Song for Jedi
    1. album: Western sous la neige
    1. rating: 5
1. Save
1. Click on *Create Item*
    1. artist: Dionysos
    1. title: She Is the Liquid Princess
    1. album: Western sous la neige
    1. rating: 4
1. Save

### Query Item

1. Search using keys
    1. In the search panel, select *Query*
    1. Search using Partition Key
        1. Enter a valid value for artist et search: you see your result
    1. Search using Partition Key and Sort Key
        1. Enter a valid value for artist and title: you see your result
1. Search using Other attribute
    1. In the search panel, select *Scan*
    1.  Use filter
        1. Enter attribute *rating*
        1. Enter value *5*
        1. See your result  