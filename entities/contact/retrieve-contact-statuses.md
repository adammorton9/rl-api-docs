# Retrieve contact statuses

## Get contact statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/contact-statuses/{templateId}`

This endpoint allows you to retrieve status data for contacts.

#### Path Parameters

| Name       | Type    | Description              |
| ---------- | ------- | ------------------------ |
| templateId | integer | The contact template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Contact statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 3,
            "statusName": "Pending Review"
        },
        {
            "statusId": 1,
            "statusName": "Active"
        },
        {
            "statusId": 2,
            "statusName": "Inactive, Deletable, Unlocked"
        },
        {
            "statusId": 4,
            "statusName": "Active, Not Deletable, Locked"
        },
        {
            "statusId": 5,
            "statusName": "Inactive, Not Deletable, Locked"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
