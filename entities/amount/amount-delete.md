# Delete an amount

## Delete amount

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/amount/:id`

This endpoint allows you to delete an amount.

#### Path Parameters

| Name | Type    | Description                 |
| ---- | ------- | --------------------------- |
| id   | integer | ID of the amount to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Amount successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}
