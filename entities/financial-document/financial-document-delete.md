# Delete a financial document

## Delete financial document

<mark style="color:red;">`DELETE`</mark> `https://api.rightsline.com/v4/financial-document/:id`

This endpoint allows you to delete a financial document.

#### Path Parameters

| Name | Type    | Description                             |
| ---- | ------- | --------------------------------------- |
| id   | integer | ID of the financial document to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial document successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

