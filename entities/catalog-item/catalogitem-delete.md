# Delete a catalog item

## Delete catalog item

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/catalog-item/:id`

This endpoint allows you to delete a catalog item.

#### Path Parameters

| Name | Type    | Description                       |
| ---- | ------- | --------------------------------- |
| id   | integer | ID of the catalog item to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Catalog item successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

