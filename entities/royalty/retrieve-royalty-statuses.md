# Retrieve royalty statuses

## Get royalty statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/royalty-statuses/{templateId}`

This endpoint allows you to retrieve status data for royalties.

#### Path Parameters

| Name       | Type    | Description              |
| ---------- | ------- | ------------------------ |
| templateId | integer | The royalty template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Royalty statuses retrieved successfully." %}
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
