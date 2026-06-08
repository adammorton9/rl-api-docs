# Retrieve catalog item statuses

## Get catalog item statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/catalog-item-statuses/{templateId}`

This endpoint allows you to retrieve status data for catalog-items.

#### Path Parameters

| Name       | Type    | Description                   |
| ---------- | ------- | ----------------------------- |
| templateId | integer | The catalog-item template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Catalog-item statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Development"
        },
        {
            "statusId": 2,
            "statusName": "Packaging/Financing"
        },
        {
            "statusId": 16,
            "statusName": "Greenlit"
        },
        {
            "statusId": 3,
            "statusName": "Production"
        },
        {
            "statusId": 4,
            "statusName": "Post-Production"
        },
        {
            "statusId": 17,
            "statusName": "Delivery"
        },
        {
            "statusId": 14,
            "statusName": "Awaiting Release"
        },
        {
            "statusId": 6,
            "statusName": "Released"
        },
        {
            "statusId": 18,
            "statusName": "Active, Deletable, Unlocked"
        },
        {
            "statusId": 12,
            "statusName": "Inactive, Deletable, Unlocked"
        },
        {
            "statusId": 19,
            "statusName": "Inactive, Not Deletable, Locked"
        },
        {
            "statusId": 20,
            "statusName": "Inactive, Deletable, Locked"
        },
        {
            "statusId": 21,
            "statusName": "Inactive"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
