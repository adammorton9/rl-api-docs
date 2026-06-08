# Retrieve file statuses

## Get file statuses

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/file-statuses/{templateId}`

This endpoint allows you to retrieve status data for files.

#### Path Parameters

| Name       | Type    | Description           |
| ---------- | ------- | --------------------- |
| templateId | integer | The file template ID. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 File statuses retrieved successfully." %}
```javascript
{
    "statuses": [
        {
            "statusId": 1,
            "statusName": "Document Created"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
