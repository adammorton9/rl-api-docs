# Retrieve project statuses

## Get project statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/project-statuses/:templateId`

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
{% tab title="200 Project statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Created"
        },
        {
            "statusId": 2,
            "statusName": "In Review"
        },
        {
            "statusId": 3,
            "statusName": "In Negotiation"
        },
        {
            "statusId": 4,
            "statusName": "Rejected"
        },
        {
            "statusId": 5,
            "statusName": "Greenlit"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
