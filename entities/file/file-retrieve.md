# Retrieve a file

## Get file

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/file/:id`

This endpoint allows you to retrieve a specific file by ID.

#### Path Parameters

| Name | Type   | Description                 |
| ---- | ------ | --------------------------- |
| id   | string | ID of the file to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 File successfully retrieved." %}
```javascript
{
    "parentRelationship": [
        {
            "id": 6269691,
            "relationshipType": {
                "relationshipTypeId": 0,
                "relationshipTypeName": "Default"
            },
            "createdById": 296252,
            "createdDate": "2015-09-04T01:31:01.740Z",
            "lastUpdatedById": 296242,
            "lastUpdatedDate": "2015-10-27T17:45:45.107Z",
            "parentCharTypeId": 4,
            "parentRecordId": 6,
            "parentTemplate": {
                "templateId": 4,
                "templateName": "Exec Producer Deal",
                "processId": 0,
                "processName": null
            },
            "parentStatus": {
                "statusId": 2,
                "statusName": "Created"
            },
            "childCharTypeId": 14,
            "childRecordId": 1,
            "sequenceNumber": 32653352960
        }
    ],
    "relationshipUpdateRules": null,
    "parentRelationshipCount": 1,
    "id": 1,
    "revisionId": 0,
    "title": "File Test",
    "template": {
        "templateId": 2,
        "templateName": "File Upload",
        "processId": 0,
        "processName": null
    },
    "status": {
        "statusId": 1,
        "statusName": "Document Created"
    },
    "characteristics": {
        "file_type": [
            {
                "id": 39,
                "value": "Sample"
            }
        ],
        "uri": "S3/documents/File_Test.docx"
    },
    "comments": [],
    "createdById": 296242,
    "createdDate": "2015-09-09T16:52:30.137Z",
    "lastUpdatedById": 296242,
    "lastUpdatedDate": "2015-09-09T16:52:30.200Z",
    "statusUpdatedById": 296242,
    "statusUpdatedDate": "2015-09-09T16:52:30.137Z"
}
```
{% endtab %}

{% tab title="404 Could not find a file with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

