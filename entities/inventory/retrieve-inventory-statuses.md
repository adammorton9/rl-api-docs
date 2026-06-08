# Retrieve inventory statuses

## Get inventory statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/inventory-statuses/{templateId}`

#### Path Parameters

| Name       | Type    | Description                |
| ---------- | ------- | -------------------------- |
| templateId | integer | The inventory template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Inventory statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Created"
        },
        {
            "statusId": 2,
            "statusName": "Solicited"
        },
        {
            "statusId": 3,
            "statusName": "QC Required"
        },
        {
            "statusId": 4,
            "statusName": "Checked In"
        },
        {
            "statusId": 6,
            "statusName": "Checked Out"
        },
        {
            "statusId": 8,
            "statusName": "QC Rejected"
        },
        {
            "statusId": 5,
            "statusName": "Deprecated"
        },
        {
            "statusId": 7,
            "statusName": "Inactive, Deletable, Unlocked"
        },
        {
            "statusId": 9,
            "statusName": "Active, Not Deletable, Locked"
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
