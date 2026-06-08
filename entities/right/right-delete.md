# Delete a right

## Delete right

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/right/:id`

This endpoint allows you to delete a right.

#### Path Parameters

| Name | Type    | Description                |
| ---- | ------- | -------------------------- |
| id   | integer | ID of the right to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Right successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

