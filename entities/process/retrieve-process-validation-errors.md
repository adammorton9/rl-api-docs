# Retrieve process validation errors

## Get process validation errors

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/process/:id/validation-errors`

This endpoint allows you to retrieve all validation errors for a process.

#### Path Parameters

| Name | Type    | Description                                          |
| ---- | ------- | ---------------------------------------------------- |
| id   | integer | ID of the process to retrieve validation errors for. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Validation errors retrieved successfully." %}
```json
{
    "validationErrors": []
}
```
{% endtab %}
{% endtabs %}
