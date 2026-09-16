# Retrieve schedule draft templates

## Get schedule draft templates

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/schedule/:id/draft-templates`

This endpoint allows you to retrieve the available draft templates for a schedule.

#### Path Parameters

| Name | Type    | Description                                         |
| ---- | ------- | --------------------------------------------------- |
| id   | integer | ID of the schedule to retrieve draft templates for. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Draft templates retrieved successfully." %}
```json
[
    {
        "templateId": 1,
        "templateName": "Standard Draft"
    }
]
```
{% endtab %}
{% endtabs %}
