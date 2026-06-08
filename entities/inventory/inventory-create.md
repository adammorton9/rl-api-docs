# Create an inventory item

## Create inventory

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/inventory`

This endpoint allows you to create an inventory record.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type    | Description                                       |
| ------------------- | ------- | ------------------------------------------------- |
| title               | string  | The title of the new inventory item.              |
| template            | object  | The template to assign the new inventory item.    |
| template.templateId | integer | The template ID to assign the new inventory item. |
| characteristics     | object  | The field values of the new inventory item.       |
| parentRelationship  | array   | The parent entities of the new inventory item.    |

{% tabs %}
{% tab title="200 Inventory successfully created.  Returns the ID of the newly created record." %}
```
14462
```
{% endtab %}

{% tab title="400 Request is missing information, or the information is invalid." %}
```javascript
{
  "message": "TemplateId is required"
}
```
{% endtab %}
{% endtabs %}

### Sample Request

```javascript
{
    "title": "My New Inventory",
    "template": {
        "templateId": 1
    },
    "characteristics": {
        "notes": "This is a great new inventory!"
    },
    "parentRelationship": [
        {
            "parentCharTypeId": 17,
            "parentRecordId": 100
        }
    ]
}
```
