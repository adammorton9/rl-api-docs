# Update a table row

## Update table row

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/table/:id`

This endpoint allows you to update a table row.

#### Path Parameters

| Name | Type    | Description                    |
| ---- | ------- | ------------------------------ |
| id   | integer | ID of the table row to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type    | Description                                 |
| ------------------- | ------- | ------------------------------------------- |
| title               | string  | The new title of the table row to update.   |
| template            | object  | The template of the table row to update.    |
| template.templateId | integer | The template ID of the table row to update. |
| characteristics     | object  | The fields on the table row to update.      |

{% tabs %}
{% tab title="200 Table row successfully updated." %}
```javascript
{    
    "title": "Your updated table row",    
    "template": {
        "templateId":1
    },    
    "characteristics": {}
}
```
{% endtab %}
{% endtabs %}

