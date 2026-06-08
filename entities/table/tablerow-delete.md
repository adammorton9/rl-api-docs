# Delete a table row

## Delete table row

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/table/:id`

This endpoint allows you to delete a table row.

#### Path Parameters

| Name | Type    | Description                    |
| ---- | ------- | ------------------------------ |
| id   | integer | ID of the table row to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Table row successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}
