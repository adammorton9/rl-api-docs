# Delete a deal

## Delete deal

<mark style="color:red;">`DELETE`</mark> `https://api.rightsline.com/v4/deal/:id`

This endpoint allows you to delete a deal.

#### Path Parameters

| Name | Type    | Description               |
| ---- | ------- | ------------------------- |
| id   | integer | ID of the deal to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Deal successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

