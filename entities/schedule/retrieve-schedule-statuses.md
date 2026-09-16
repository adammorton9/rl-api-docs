# Retrieve schedule statuses

## Get schedule statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/schedule-statuses/{templateId}`

This endpoint allows you to retrieve status data for schedules.

#### Path Parameters

| Name       | Type    | Description               |
| ---------- | ------- | ------------------------- |
| templateId | integer | The schedule template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Schedule statuses retrieved successfully." %}
```json
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Active"
        },
        {
            "statusId": 2,
            "statusName": "Inactive"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
