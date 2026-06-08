# Contact delete check

## Contact delete check

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/contact/:id/delete-check`

This endpoint allows you to check if a contact can be deleted.

#### Path Parameters

| Name                                 | Type   | Description        |
| ------------------------------------ | ------ | ------------------ |
| id<mark style="color:red;">\*</mark> | string | ID of the contact. |

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
```javascript
{
    "id": 1908979,
    "template": {
        "templateId": 3,
        "templateName": "User",
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
            "title": "Deal 1",
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
            "title": "Deal 2",
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

{% tab title="404 Contact does not exist." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
