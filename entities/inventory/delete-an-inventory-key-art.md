---
description: Delete the key art for an inventory item.
---

# Delete an inventory key art

## Delete inventory key art

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/inventory/:id/keyart`

This endpoint allows you to delete the key art for an inventory item.

#### Path Parameters

| Name | Type    | Description               |
| ---- | ------- | ------------------------- |
| id   | integer | ID of the inventory item. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Key art successfully deleted." %}
```javascript
{    
    "message": "Keyart deleted."
}
```
{% endtab %}

{% tab title="404 Key art not found for this inventory item." %}
```javascript
{    
    "message": "No keyart found."
}
```
{% endtab %}
{% endtabs %}

