---
description: Get the workflow statuses for a particular workflow process.
---

# Get workflow statuses

## Get workflow statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/processes/:processID/statuses`

This endpoint allows you to retrieve workflow statuses for a given workflow process.

#### Path Parameters

| Name                                        | Type | Description              |
| ------------------------------------------- | ---- | ------------------------ |
| processID<mark style="color:red;">\*</mark> | int  | The workflow process ID. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Workflow statuses retrieved successfully." %}
```json
{
    "statuses": [
        {
            "statusId": 3,
            "statusName": "Pending Review",
            "statusDescription": "Pending Review",
            "isActive": true,
            "isLocked": false,
            "isDeletable": false,
            "sequenceNumber": 1,
            "availableActions": [
                {
                    "actionId": 1,
                    "actionName": "Activate",
                    "isInitialAction": true
                },
                {
                    "actionId": 2,
                    "actionName": "Deactivate",
                    "isInitialAction": false
                },
                {
                    "actionId": 3,
                    "actionName": "Request Review",
                    "isInitialAction": false
                },
                {
                    "actionId": 4,
                    "actionName": "Activate, Make Not Deletable, Lock",
                    "isInitialAction": false
                },
                {
                    "actionId": 5,
                    "actionName": "Deactivate, Make Deletable, Lock",
                    "isInitialAction": false
                },
                {
                    "actionId": 6,
                    "actionName": "Generate Document",
                    "isInitialAction": false
                }
            ],
            "associatedRoles": [
                {
                    "roleId": 2,
                    "roleName": "Admin User",
                    "statusId": 3,
                    "statusName": "Active"
                },
                {
                    "roleId": 3,
                    "roleName": "Super Admin",
                    "statusId": 3,
                    "statusName": "Pending Review"
                },
                {
                    "roleId": 6,
                    "roleName": "Full User",
                    "statusId": 3,
                    "statusName": "Pending Review"
                }
            ]
        },
        {
            "statusId": 1,
            "statusName": "Active",
            "statusDescription": "Active",
            "isActive": true,
            "isLocked": false,
            "isDeletable": true,
            "sequenceNumber": 2,
            "availableActions": [
                {
                    "actionId": 2,
                    "actionName": "Deactivate",
                    "isInitialAction": false
                },
                {
                    "actionId": 3,
                    "actionName": "Request Review",
                    "isInitialAction": false
                },
                {
                    "actionId": 4,
                    "actionName": "Activate, Make Not Deletable, Lock",
                    "isInitialAction": false
                },
                {
                    "actionId": 5,
                    "actionName": "Deactivate, Make Deletable, Lock",
                    "isInitialAction": false
                },
                {
                    "actionId": 6,
                    "actionName": "Generate Document",
                    "isInitialAction": false
                },
                {
                    "actionId": 8,
                    "actionName": "CWF contact list",
                    "isInitialAction": false
                },
                {
                    "actionId": 9,
                    "actionName": "sample inactive chained action",
                    "isInitialAction": false
                }
            ],
            "associatedRoles": [
                {
                    "roleId": 2,
                    "roleName": "Admin User",
                    "statusId": 1,
                    "statusName": "Active"
                },
                {
                    "roleId": 3,
                    "roleName": "Super Admin",
                    "statusId": 1,
                    "statusName": "Active"
                },
                {
                    "roleId": 6,
                    "roleName": "Full User",
                    "statusId": 1,
                    "statusName": "Active"
                }
            ]
        },
        {
            "statusId": 2,
            "statusName": "Inactive, Deletable, Unlocked",
            "statusDescription": "",
            "isActive": false,
            "isLocked": false,
            "isDeletable": true,
            "sequenceNumber": 3,
            "availableActions": [
                {
                    "actionId": 1,
                    "actionName": "Activate",
                    "isInitialAction": true
                },
                {
                    "actionId": 3,
                    "actionName": "Request Review",
                    "isInitialAction": false
                },
                {
                    "actionId": 4,
                    "actionName": "Activate, Make Not Deletable, Lock",
                    "isInitialAction": false
                },
                {
                    "actionId": 5,
                    "actionName": "Deactivate, Make Deletable, Lock",
                    "isInitialAction": false
                },
                {
                    "actionId": 6,
                    "actionName": "Generate Document",
                    "isInitialAction": false
                }
            ],
            "associatedRoles": [
                {
                    "roleId": 2,
                    "roleName": "Admin User",
                    "statusId": 2,
                    "statusName": "Active"
                },
                {
                    "roleId": 3,
                    "roleName": "Super Admin",
                    "statusId": 2,
                    "statusName": "Inactive"
                },
                {
                    "roleId": 6,
                    "roleName": "Full User",
                    "statusId": 2,
                    "statusName": "Inactive"
                }
            ]
        }
    ]
}
```
{% endtab %}
{% endtabs %}

