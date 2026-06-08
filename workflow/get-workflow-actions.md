---
description: Get the workflow actions for a particular workflow process.
---

# Get workflow actions

## Get workflow actions

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/processes/:processID/actions`

This endpoint allows you to retrieve workflow actions for a given workflow process.

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
{% tab title="200 Workflow actions retrieved successfully." %}
```json
{
    "actions": [
        {
            "actionId": 1,
            "actionName": "Development",
            "actionDescription": "Development",
            "isInitialAction": true,
            "sequenceNumber": 1,
            "resultingStatus": "Development"
        },
        {
            "actionId": 2,
            "actionName": "Packaging/Financing",
            "actionDescription": "",
            "isInitialAction": false,
            "sequenceNumber": 2,
            "resultingStatus": "Packaging/Financing"
        },
        {
            "actionId": 16,
            "actionName": "Greenlit",
            "actionDescription": "Greenlit",
            "isInitialAction": false,
            "sequenceNumber": 3,
            "resultingStatus": "Greenlit"
        },
        {
            "actionId": 3,
            "actionName": "Production",
            "actionDescription": "Production",
            "isInitialAction": false,
            "sequenceNumber": 4,
            "resultingStatus": "Production"
        },
        {
            "actionId": 4,
            "actionName": "Post-Production",
            "actionDescription": "Post-Production",
            "isInitialAction": false,
            "sequenceNumber": 5,
            "resultingStatus": "Post-Production"
        },
        {
            "actionId": 17,
            "actionName": "Delivery",
            "actionDescription": "Delivery",
            "isInitialAction": false,
            "sequenceNumber": 6,
            "resultingStatus": "Delivery"
        },
        {
            "actionId": 15,
            "actionName": "Wait for Release",
            "actionDescription": "",
            "isInitialAction": false,
            "sequenceNumber": 7,
            "resultingStatus": "Awaiting Release"
        },
        {
            "actionId": 6,
            "actionName": "Released",
            "actionDescription": "Released",
            "isInitialAction": false,
            "sequenceNumber": 8,
            "resultingStatus": "Released"
        },
        {
            "actionId": 18,
            "actionName": "Activate, Make Deletable, Unlock",
            "actionDescription": "",
            "isInitialAction": false,
            "sequenceNumber": 9,
            "resultingStatus": "Active, Deletable, Unlocked"
        },
        {
            "actionId": 12,
            "actionName": "Deactivate, Make Deletable, Unlock",
            "actionDescription": "",
            "isInitialAction": false,
            "sequenceNumber": 10,
            "resultingStatus": "Inactive, Deletable, Unlocked"
        },
        {
            "actionId": 19,
            "actionName": "Activate, Make Not Deletable, Lock",
            "actionDescription": "",
            "isInitialAction": false,
            "sequenceNumber": 11,
            "resultingStatus": "Inactive, Not Deletable, Locked"
        },
        {
            "actionId": 20,
            "actionName": "Deactivate, Make Not Deletable, Lock",
            "actionDescription": "",
            "isInitialAction": false,
            "sequenceNumber": 12,
            "resultingStatus": "Inactive, Deletable, Locked"
        },
        {
            "actionId": 21,
            "actionName": "Generate Document",
            "actionDescription": "",
            "isInitialAction": false,
            "sequenceNumber": 13,
            "resultingStatus": "No Status Change"
        },
        {
            "actionId": 24,
            "actionName": "Deactivate",
            "actionDescription": "Deactivate",
            "isInitialAction": false,
            "sequenceNumber": 14,
            "resultingStatus": "Inactive"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

