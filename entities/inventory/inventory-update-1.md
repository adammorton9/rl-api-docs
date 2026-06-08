# Update an inventory item

## Update inventory item

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/inventory/:id`

Update the characteristics of a inventory.

#### Path Parameters

| Name | Type   | Description                        |
| ---- | ------ | ---------------------------------- |
| id   | string | The ID of the inventory to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                      |
| ------------------- | ------ | ---------------------------------------------------------------- |
| title               | string | The new title of the inventory.                                  |
| template            | object | The template of the inventory.                                   |
| template.templateId | string | The unique ID of the template that is assigned to the inventory. |
| characteristics     | object | The field values to update on the inventory.                     |
| parentRelationship  | array  | Create this inventory as a child of other entities.              |

{% tabs %}
{% tab title="200 Inventory updated successfully." %}
```javascript
{
  "parentRelationship": null,
  "relationshipUpdateRules": null,
  "id": 2,
  "revisionId": 0,
  "title": "Physical Media 1",
  "template": {
    "fields": [],
    "templateId": 7,
    "templateName": "Physical Media",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Created"
  },
  "characteristics": {
    "image_aspect_ratio": {
      "id": 5,
      "value": "1.33:1 (4:3)"
    },
    "format": {
      "id": 1,
      "value": "DCP 2K"
    },
    "fedex_number": "2"
  },
  "comments": [],
  "createdById": 296242,
  "createdDate": "2015-11-02T23:12:10.963Z",
  "lastUpdatedById": 296242,
  "lastUpdatedDate": "2015-11-02T23:12:11.077Z"
}
```
{% endtab %}
{% endtabs %}

