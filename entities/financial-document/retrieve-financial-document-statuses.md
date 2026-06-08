# Retrieve financial document statuses

## Get financial document statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/financial-document-statuses/{templateId}`

This endpoint allows you to retrieve status data for financial documents.

#### Path Parameters

| Name       | Type    | Description                         |
| ---------- | ------- | ----------------------------------- |
| templateId | integer | The financial document template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial document statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Billing Document Created"
        },
        {
            "statusId": 2,
            "statusName": "Billing Document Drafted"
        },
        {
            "statusId": 3,
            "statusName": "Billing Document Sent"
        },
        {
            "statusId": 4,
            "statusName": "Billing Document Paid"
        },
        {
            "statusId": 5,
            "statusName": "Revenue Recognized"
        },
        {
            "statusId": 6,
            "statusName": "Billing Document Paid & Revenue Recognized"
        },
        {
            "statusId": 7,
            "statusName": "Billing Document Cancelled"
        },
        {
            "statusId": 8,
            "statusName": "Active, Not Deletable, Locked"
        },
        {
            "statusId": 9,
            "statusName": "Inactive, Deletable, Unlocked"
        },
        {
            "statusId": 10,
            "statusName": "Inactive, Not Deletable, Locked"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
