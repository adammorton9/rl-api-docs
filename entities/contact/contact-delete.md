# Delete a contact

## Delete contact

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/contact/:id`

This endpoint allows you to delete a contact.

#### Path Parameters

| Name | Type    | Description                  |
| ---- | ------- | ---------------------------- |
| id   | integer | ID of the contact to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Contact successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

