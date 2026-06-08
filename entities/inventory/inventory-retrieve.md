# Retrieve an inventory item

## Get inventory item

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/inventory/:id`

This endpoint allows you to retrieve a specific inventory item by ID.

#### Path Parameters

| Name | Type   | Description                           |
| ---- | ------ | ------------------------------------- |
| id   | string | ID of the inventory item to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Inventory successfully retrieved." %}
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

{% tab title="404 Could not find inventory with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

