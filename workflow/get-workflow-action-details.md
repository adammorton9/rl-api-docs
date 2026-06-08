---
description: Get the workflow action details for a particular workflow action.
---

# Get workflow action details

## Get workflow action details

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/processes/:processID/actions/:actionID`

This endpoint allows you to retrieve workflow actions for a given workflow process.

#### Path Parameters

| Name                                        | Type | Description              |
| ------------------------------------------- | ---- | ------------------------ |
| processID<mark style="color:red;">\*</mark> | int  | The workflow process ID. |
| actionID<mark style="color:red;">\*</mark>  | int  | The workflow action ID.  |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Workflow action retrieved successfully." %}
```json
{
    "actionId": 16,
    "actionName": "Greenlit",
    "actionDescription": "Record is Greenlit",
    "isInitialAction": false,
    "resultingStatus": "Greenlit",
    "sequenceNumber": 1,
    "updateCurrencyConversion": true,
    "documentOption": {
        "documentOptionId": 0,
        "documentOptionName": "None"
    },
    "extensions": [
        {
            "name": "usp_wf_CreateRecordAmendment",
            "type": "Stored Proc"
        }
    ],
    "associatedRoles": [
        {
            "roleId": 1,
            "roleName": "External User"
        },
        {
            "roleId": 2,
            "roleName": "Admin User"
        },
        {
            "roleId": 3,
            "roleName": "Super Admin"
        },
        {
            "roleId": 6,
            "roleName": "Full User"
        }
    ],
    "chainedActions": [
        {
            "processId": 5,
            "actionId": 2
        }
    ],
    "roleNotifications": [
        {
            "roleId": 20,
            "notificationId": 466
        }
    ],
    "partyNotifications": [
        {
            "partyId": 10,
            "notificationId": 200
        }
    ]
}
```
{% endtab %}
{% endtabs %}
