# Retrieve deal statuses

## Get deal statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/deal-statuses/{templateId}`

This endpoint allows you to retrieve status data for deals.

#### Path Parameters

| Name       | Type    | Description           |
| ---------- | ------- | --------------------- |
| templateId | integer | The deal template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Deal statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 2,
            "statusName": "Created"
        },
        {
            "statusId": 4,
            "statusName": "DM Signed"
        },
        {
            "statusId": 6,
            "statusName": "LFA Outstanding (Yes DM)"
        },
        {
            "statusId": 15,
            "statusName": "LFA Outstanding (No DM)"
        },
        {
            "statusId": 3,
            "statusName": "LFA Partially Signed"
        },
        {
            "statusId": 7,
            "statusName": "LFA Fully Signed"
        },
        {
            "statusId": 16,
            "statusName": "In Default"
        },
        {
            "statusId": 17,
            "statusName": "Active, Deletable, Locked"
        },
        {
            "statusId": 18,
            "statusName": "Active, Deletable, Unlocked"
        },
        {
            "statusId": 9,
            "statusName": "Active, Not Deletable, Locked"
        },
        {
            "statusId": 19,
            "statusName": "Active, Not Deletable, Unlocked"
        },
        {
            "statusId": 20,
            "statusName": "Inactive, Deletable, Locked"
        },
        {
            "statusId": 14,
            "statusName": "Inactive, Deletable, Unlocked"
        },
        {
            "statusId": 10,
            "statusName": "Inactive, Not Deletable, Locked"
        },
        {
            "statusId": 21,
            "statusName": "Inactive, Not Deletable, Unlocked"
        },
        {
            "statusId": 22,
            "statusName": "Out for Signature"
        },
        {
            "statusId": 23,
            "statusName": "Fully Signed"
        },
        {
            "statusId": 24,
            "statusName": "Approval Requested"
        },
        {
            "statusId": 25,
            "statusName": "Approved"
        },
        {
            "statusId": 26,
            "statusName": "Rejected"
        },
        {
            "statusId": 27,
            "statusName": "Completed"
        },
        {
            "statusId": 28,
            "statusName": "Approved_RG"
        },
        {
            "statusId": 29,
            "statusName": "Amended"
        },
        {
            "statusId": 30,
            "statusName": "Lock Royalty Records (Chained)"
        },
        {
            "statusId": 31,
            "statusName": "Unlock Royalty Records (Chained)"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
