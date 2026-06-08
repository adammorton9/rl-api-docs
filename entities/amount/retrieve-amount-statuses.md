# Retrieve amount statuses

## Get amount statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/amount-statuses/{templateId}`

This endpoint allows you to retrieve status data for amounts.

#### Path Parameters

| Name       | Type    | Description             |
| ---------- | ------- | ----------------------- |
| templateId | integer | The amount template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Amount statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Amount Created"
        },
        {
            "statusId": 2,
            "statusName": "Added to Billing Document"
        },
        {
            "statusId": 3,
            "statusName": "Amount Paid"
        },
        {
            "statusId": 4,
            "statusName": "Amount Cancelled"
        },
        {
            "statusId": 5,
            "statusName": "Inactive, Deletable, Unlocked"
        },
        {
            "statusId": 6,
            "statusName": "Active, Not Deletable, Locked"
        },
        {
            "statusId": 7,
            "statusName": "Inactive, Not Deletable, Locked"
        },
        {
            "statusId": 9,
            "statusName": "Approved"
        },
        {
            "statusId": 10,
            "statusName": "Active, Deletable, Locked"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
