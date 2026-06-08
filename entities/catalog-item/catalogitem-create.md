# Create a catalog item

## Create catalog item

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/catalog-item`

This endpoint allows you to create a new catalog item.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                           |
| ------------------- | ------ | --------------------------------------------------------------------- |
| title               | string | The title of the new catalog item.                                    |
| template            | object | The template of the new catalog item.                                 |
| template.templateId | string | The unique ID of the template to assign to the catalog item.          |
| characteristics     | object | The field values to assign to the catalog item.                       |
| parentRelationship  | array  | Create this catalog item as a child of a deal or other catalog items. |

{% tabs %}
{% tab title="200 Catalog item created successfully.  Returns the ID of the newly created catalog item." %}
```
302
```
{% endtab %}

{% tab title="400 Request is missing required information, or the information is invalid." %}
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
    "title": "The Three Stooges",
    "template": {
        "templateId": 1
    },
    "characteristics": {
        "notes": "This is a great movie!",
        "release_year": 1925
    },
    "parentRelationship": [
        {
            "parentCharTypeId": 4,
            "parentRecordId": 100
        }
    ]
}
```

