# Batch structure

Every batch has the following fields:

**batchId** (int) - The Batch ID.

**batchStatus** (string) - The [Batch status](batch-statuses.md).

**batchResults** (object) - The [record](batch-structure.md#batch-records) and [relationship](batch-structure.md#batch-relationships) objects that are the result of the batch.&#x20;

```json
{
    "batchId": Int,
    "batchStatus": "Created"/"InProgress"/"Errored"/"Cancelled"/"Complete",
    "batchResults": {
        "records": {EntityObjectDictionary},
        "relationships": [RelationshipObject]
    }
}
```

### Batch records

Batch records are organized in a key-value collection, where the records are grouped by the char type ID.  For example, the following JSON contains four records, two contacts (char type ID = 2) and two catalog items (char type ID = 1).

```json
{
    "records": {
        "2": [
            {
                "characteristics": {
                    "department": "Sales",
                    "first_name": "John",
                    "last_name": "Smith"
                },
                "template": {
                    "templateId": 1
                },
                "title": "Person 1"
            },
            {
                "characteristics": {
                    "department": "Accounting",
                    "first_name": "Susan",
                    "last_name": "Williams"
                },
                "template": {
                    "templateId": 1
                },
                "title": "Person 2"
            }
        ],
        "1": [
            {
                "characteristics": {
                    "release_year": 2006
                },
                "template": {
                    "templateId": 1
                },
                "title": "Catalog 1"
            },
            {
                "characteristics": {
                    "release_year": 2013
                },
                "template": {
                    "templateId": 1
                },
                "title": "Catalog 2"
            }
        ]
    }
}
```

When retrieving a batch, the records will be organized in a slightly different structure. The records will still be organized in a key-value collection by char type ID, but each individual entity will have a few new fields:

**record** (object) - The entity object.

**code** (int) - The HTTP status code indicating the status of creating/updating/deleting/retrieving the record. Examples are 200, 400, 403, 404, 409

&#x20;**message** (int) - A human-readable message of the status of the batch record. Examples would be "Found.", "Created.", "Updated.", "Deleted.", "Action Executed.", "Copied.", "Record Not Found.", "Access Denied.", "Invalid Record.", "Record Locked."&#x20;

**id** (int) - The ID of the record.

```json
 "records": {
    "1": [
        {
            "record": {
                "id": 5,
                "revisionId": 0,
                "title": "test",
                "template": {
                    "templateId": 1,
                    "templateName": "Feature",
                    "processId": 0
                },
                "status": {
                    "statusId": 19,
                    "statusName": "Inactive, Not Deletable, Locked"
                },
                "characteristics": {
                    "notes": [
                        "test"
                    ]
                },
                "createdById": 46232,
                "createdDate": "2015-09-03T00:59:01.507Z",
                "lastUpdatedById": 1100491,
                "lastUpdatedDate": "2023-02-14T18:30:19.857Z",
                "statusUpdatedById": 1100491,
                "statusUpdatedDate": "2020-12-11T17:51:50.830Z"
            },
            "code": 200,
            "message": "Found.",
            "id": 5
        }
    ]
}
```

### Batch relationships

```json
{
    "relationships":[
        {
            "parentCharTypeId": 4,
            "parentRecordId": 4958,
            "childCharTypeId": 1,
            "childRecordId": 23456
        },
        {
            "parentCharTypeId": 4,
            "parentRecordId": 4958,
            "childCharTypeId": 2,
            "childRecordId": 12345
        }
    ]
}
```

When retrieving a batch, the relationships will take on a similar structure as the records in the response, containing the additional fields below:

**relationship**(object) - The relationship object.

**code** (int) - The HTTP status code indicating the status of creating/deleting/retrieving the relationship. Examples are 200, 400, 403, 404, 409

&#x20;**message** (int) - A human-readable message of the status of the batch record. Examples would be "Found.", "Created.", "Deleted.", "Access Denied."&#x20;

**id** (int) - The ID of the relationship.

```json
"relationships": [
    {
        "relationship": {
            "id": 431235011,
            "relationshipType": {
                "relationshipTypeId": 0,
                "relationshipTypeName": "Default"
            },
            "createdById": 1091106,
            "createdDate": "2020-07-10T20:24:34.263Z",
            "lastUpdatedById": 1091106,
            "lastUpdatedDate": "2020-07-10T20:24:34.263Z",
            "parentCharTypeId": 4,
            "parentRecordId": 1493,
            "childCharTypeId": 1,
            "childRecordId": 8327,
            "sequenceNumber": 1602064027648
        },
        "code": 200,
        "message": "Found.",
        "id": 431235011
    }
]
```
