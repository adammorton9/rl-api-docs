# Retrieve right statuses

## Get right statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/right-statuses/{templateId}`

#### Path Parameters

| Name       | Type    | Description            |
| ---------- | ------- | ---------------------- |
| templateId | integer | The right template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Rightset statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Active"
        },
        {
            "statusId": 2,
            "statusName": "Active, Not Deletable, Locked"
        },
        {
            "statusId": 3,
            "statusName": "Active, Deletable, Locked"
        },
        {
            "statusId": 4,
            "statusName": "Active, Not Deletable, Unlocked"
        },
        {
            "statusId": 5,
            "statusName": "Inactive, Deletable, Locked"
        },
        {
            "statusId": 6,
            "statusName": "Inactive, Deletable, Unlocked"
        },
        {
            "statusId": 7,
            "statusName": "Inactive, Not Deletable, Unlocked"
        },
        {
            "statusId": 8,
            "statusName": "Inactive, Not Deletable, Locked"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
