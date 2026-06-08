---
description: Get the workflow notifications for a particular workflow process.
---

# Get workflow notifications

## Get workflow notifications

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/processes/:processID/`notifications

This endpoint allows you to retrieve workflow notifications for a given workflow process.

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
{% tab title="200 Workflow notifications retrieved successfully." %}
```json5
{
    "notifications": [
        {
            "notificationId": 1,
            "notificationName": "Send Long Form Notification                                                                                                                                                                             ",
            "sequenceNumber": 1,
            "subject": "Long form for <<transaction.entity_title>> attached.",
            "previewBeforeSend": true,
            "addActionButton": false,
            "triggerMessage": false,
            "plainText": "",
            "html": "",
            "attachmentTypes": [
                {
                    "templateId": 9,
                    "templateName": "Test Draft Template",
                    "templateDescription": "Test Draft Template",
                    "fileName": "Deal_Draft_Template.docx"
                }
            ]
        },
        {
            "notificationId": 2,
            "notificationName": "Approve/Reject Deal                                                                                                                                                                                     ",
            "sequenceNumber": 2,
            "subject": "Approval Requested on Deal <<transaction.entity_id>>",
            "previewBeforeSend": true,
            "addActionButton": true,
            "triggerMessage": false,
            "plainText": "Hello <<recipient.entity_title>>,\n\nYour approval is requested on the following Deal <<transaction.entity_title>>.",
            "html": "<p>Hello <i>&lt;&lt;recipient.entity_title&gt;&gt;</i>,</p><p>Your approval is requested on the following Deal: <b>&lt;&lt;transaction.entity_title&gt;&gt;</b>.</p>",
            "attachmentTypes": [
                {
                    "templateId": 2,
                    "templateName": "Sales Sheet",
                    "templateDescription": "Sales Sheet",
                    "fileName": "RL_SALES_SHEET.docx"
                }
            ]
        }    
    ]
}
```
{% endtab %}
{% endtabs %}

