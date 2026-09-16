# Retrieve process statuses

## Get process statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/process-statuses/{templateId}`

This endpoint allows you to retrieve status data for processes.

#### Path Parameters

| Name       | Type    | Description              |
| ---------- | ------- | ------------------------ |
| templateId | integer | The process template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Process statuses retrieved successfully." %}
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
