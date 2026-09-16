# Retrieve process draft templates

## Get process draft templates

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/process/:id/draft-templates`

This endpoint allows you to retrieve the available draft templates for a process.

#### Path Parameters

| Name | Type    | Description                                        |
| ---- | ------- | -------------------------------------------------- |
| id   | integer | ID of the process to retrieve draft templates for. |

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
