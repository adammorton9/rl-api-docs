# Delete an inventory item

## Delete inventory

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/inventory/:id`

This endpoint allows you to delete a inventory item.

#### Path Parameters

| Name | Type    | Description                         |
| ---- | ------- | ----------------------------------- |
| id   | integer | ID of the inventory item to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Inventory item successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

