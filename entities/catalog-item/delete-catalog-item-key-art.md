---
description: Delete the key art for a catalog item.
---

# Delete catalog item key art

## Delete catalog item key art

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/catalog-item/:id/keyart`

This endpoint allows you to get free cakes.

#### Path Parameters

| Name | Type    | Description             |
| ---- | ------- | ----------------------- |
| id   | integer | ID of the catalog item. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Catalog item key art successfully deleted." %}
```javascript
{
    "message": "Keyart deleted."
}
```
{% endtab %}

{% tab title="404 Could not find a key art for catalog item." %}
```javascript
{    
    "message": "No keyart found."
}
```
{% endtab %}
{% endtabs %}

