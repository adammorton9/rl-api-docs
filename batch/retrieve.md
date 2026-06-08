# Retrieve a batch

When you retrieve a batch, the batch will be in one of the following [Batch Statuses](overview/batch-statuses.md). If the batch is not in a Final Status, you can wait a few seconds, and try to retrieve the batch again.

## Retrieve batch

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/batch/:id`

This endpoint allows you to retrieve batch results.

#### Path Parameters

| Name | Type   | Description                  |
| ---- | ------ | ---------------------------- |
| id   | number | ID of the batch to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Batch successfully retrieved." %}
```javascript
{
    "batchId": 48865381,
    "batchStatus": "Complete",
    "batchResults": {
        "records": {
            "1": [
                {
                    "record": {
                        "id": 5,
                        "revisionId": 0,
                        "title": "test",
                        "template": {
                            "fields": [],
                            "templateId": 1,
                            "templateName": "Feature",
                            "processId": 0,
                            "processName": null
                        },
                        "status": {
                            "statusId": 1,
                            "statusName": "Active"
                        },
                        "characteristics": {},
                        "comments": null,
                        "createdById": 10101,
                        "createdDate": "2015-09-03T00:59:01.507Z",
                        "lastUpdatedById": 10101,
                        "lastUpdatedDate": "2021-06-23T22:33:11.830Z",
                        "statusUpdatedById": 10101,
                        "statusUpdatedDate": "2020-12-11T17:51:50.830Z"
                    },
                    "code": 200,
                    "message": "Found.",
                    "id": 5
                },
                {
                    "code": 404,
                    "message": "Record Not Found.",
                    "id": 101
                }
            ],
            "3": [
                {
                    "code": 404,
                    "message": "Record Not Found.",
                    "id": 100
                }
            ]
        },
        "relationships": [
            {
                "relationship": {
                    "id": 301,
                    "relationshipType": {
                        "relationshipTypeId": 0,
                        "relationshipTypeName": "Default"
                    },
                    "createdById": 10101,
                    "createdDate": "2020-07-10T20:24:34.263Z",
                    "lastUpdatedById": 10101,
                    "lastUpdatedDate": "2020-07-10T20:24:34.263Z",
                    "parentCharTypeId": 0,
                    "parentRecordId": 305,
                    "childCharTypeId": 1,
                    "childRecordId": 105,
                    "sequenceNumber": 16246727648
                },
                "code": 200,
                "message": "Found.",
                "id": 301
            }
        ]
    }
}
```
{% endtab %}
{% endtabs %}
