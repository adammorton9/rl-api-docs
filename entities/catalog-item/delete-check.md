# Catalog item delete check

## Catalog item delete check

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/catalog-item/:id/delete-check`

This endpoint allows you to retrieve a specific catalog item by ID.

#### Path Parameters

| Name                                 | Type   | Description             |
| ------------------------------------ | ------ | ----------------------- |
| id<mark style="color:red;">\*</mark> | string | ID of the catalog item. |

#### Query Parameters

| Name | Type | Description                                             |
| ---- | ---- | ------------------------------------------------------- |
| skip | int  | Optional paging parameter for lockedRecordAssociations. |
| rows | int  | Optional paging parameter for lockedRecordAssociations. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Success." %}
```json
{
    "id": 100,
    "template": {
        "templateId": 3,
        "templateName": "Feature",
        "systemIndicatorId": 0,
        "processId": 0
    },
    "status": {
        "statusId": 1,
        "statusName": "Active"
    },
    "isLocked": false,
    "isDeletable": true,
    "hasLockedRecordAssociations": true,
    "lockedRecordAssociationCount": 3,
    "lockedRecordAssociations": [
        {
            "id": 2486256,
            "title": "Payment Schedule Record 2486256",
            "charTypeId": 5,
            "template": {
                "templateId": 21,
                "templateName": "Payment Schedule",
                "systemIndicatorId": 0,
                "processId": 0
            },
            "status": {
                "statusId": 5,
                "statusName": "Active, Not Deletable, Locked"
            },
            "relationshipDirection": "CHILD",
            "relationshipType": {
                "relationshipTypeId": 0,
                "relationshipTypeName": "Default"
            }
        },
        {
            "id": 209,
            "title": "Test Deal 1",
            "charTypeId": 4,
            "template": {
                "templateId": 1,
                "templateName": "Outgoing Submission",
                "systemIndicatorId": 0,
                "processId": 0
            },
            "status": {
                "statusId": 10,
                "statusName": "Active, Not Deletable, Locked"
            },
            "relationshipDirection": "PARENT",
            "relationshipType": {
                "relationshipTypeId": 6,
                "relationshipTypeName": "Submitted By"
            }
        },
        {
            "id": 4633,
            "title": "Test Deal 2",
            "charTypeId": 4,
            "template": {
                "templateId": 1,
                "templateName": "Acquisition Deal",
                "systemIndicatorId": 0,
                "processId": 0
            },
            "status": {
                "statusId": 17,
                "statusName": "Active, Deletable, Locked"
            },
            "relationshipDirection": "PARENT",
            "relationshipType": {
                "relationshipTypeId": 24,
                "relationshipTypeName": "Watcher"
            }
        }
    ]
}
```
{% endtab %}

{% tab title="404 Could not find a catalog item with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
