# Update a catalog item

## Update catalog item

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/catalog-item/:id`

This endpoint allows you to update a catalog item.

#### Path Parameters

| Name | Type    | Description                       |
| ---- | ------- | --------------------------------- |
| id   | integer | ID of the catalog item to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type    | Description                               |
| ------------------- | ------- | ----------------------------------------- |
| title               | string  | The new title of the catalog item.        |
| template            | object  | The template of the catalog item.         |
| template.templateId | integer | The template ID of the catalog item.      |
| characteristics     | object  | The fields of the catalog item to update. |

{% tabs %}
{% tab title="200 Catalog item successfully updated." %}
```javascript
{    
    "title": "Your updated catalog item",    
    "template": {
        "templateId":1
    },    
    "characteristics": {}
}
```
{% endtab %}
{% endtabs %}

