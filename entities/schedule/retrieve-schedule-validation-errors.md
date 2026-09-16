# Retrieve schedule validation errors

## Get schedule validation errors

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/schedule/:id/validation-errors`

This endpoint allows you to retrieve all validation errors for a schedule.

#### Path Parameters

| Name | Type    | Description                                           |
| ---- | ------- | ----------------------------------------------------- |
| id   | integer | ID of the schedule to retrieve validation errors for. |

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
