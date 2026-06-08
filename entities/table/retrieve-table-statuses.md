# Retrieve table statuses

## Get table statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/table-statuses/{templateId}`

#### Path Parameters

| Name       | Type    | Description            |
| ---------- | ------- | ---------------------- |
| templateId | integer | The table template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Table statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Created"
        },
        {
            "statusId": 2,
            "statusName": "Operative"
        },
        {
            "statusId": 3,
            "statusName": "Inactive"
        },
        {
            "statusId": 4,
            "statusName": "Triggered"
        },
        {
            "statusId": 5,
            "statusName": "Active, Not Deletable, Locked"
        },
        {
            "statusId": 6,
            "statusName": "Active, Deletable, Locked"
        },
        {
            "statusId": 7,
            "statusName": "Active, Not Deletable, UnLocked"
        },
        {
            "statusId": 9,
            "statusName": "In Review"
        },
        {
            "statusId": 10,
            "statusName": "Approved"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
