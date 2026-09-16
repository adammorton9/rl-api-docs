# Delete a royalty

## Delete royalty

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/royalty/:id`

This endpoint allows you to delete a royalty.

#### Path Parameters

| Name | Type    | Description                  |
| ---- | ------- | ---------------------------- |
| id   | integer | ID of the royalty to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Royalty successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}
