# Retrieve process audit history

## Get process audit history

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/process/:id/audit-history`

This endpoint allows you to retrieve the audit history for a process.

#### Path Parameters

| Name | Type    | Description                                      |
| ---- | ------- | ------------------------------------------------ |
| id   | integer | ID of the process to retrieve audit history for. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Audit history retrieved successfully." %}
```json
[
    {
        "auditHistoryId": 1,
        "action": "Created",
        "userId": 123,
        "userName": "John Doe",
        "date": "2024-01-15T10:00:00.000Z"
    }
]
```
{% endtab %}
{% endtabs %}
