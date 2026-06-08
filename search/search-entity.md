---
description: Search for an entity or set of entities based on their characteristics.
---

# Entity search

### The entity search object

```javascript
{
  "keywords": "string",
  "query": {},
  "start": 0,
  "rows": 10,
  "cursorToken": "string",
  "sortOrders": [
    "string"
  ],
  "parentQuery": {},
  "childQuery": {}
}
```

## Entity search

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/:entityType/search`

This endpoint allows you to search for entities based on specific criteria.

#### Path Parameters

| Name       | Type   | Description                                                           |
| ---------- | ------ | --------------------------------------------------------------------- |
| entityType | string | The type of entity to search for. ex. deal, catalog-item, table, etc. |

#### Headers

<table><thead><tr><th>Name</th><th width="237">Type</th><th>Description</th></tr></thead><tbody><tr><td>x-api-key</td><td>string</td><td>Your company's API key.</td></tr><tr><td>Authentication</td><td>string</td><td>Authentication token.</td></tr></tbody></table>

#### Query Parameters

<table><thead><tr><th width="266">Name</th><th width="237">Type</th><th>Description</th></tr></thead><tbody><tr><td>extendedData</td><td>boolean (optional)</td><td>If true, returns <a href="../entities/the-entity-object.md#characteristics-extended-optional">Extended Characteristics</a> in the response.</td></tr></tbody></table>

#### Request Body

| Name        | Type   | Description                                         |
| ----------- | ------ | --------------------------------------------------- |
| query       | object | The search query to match the entity.               |
| childQuery  | object | The search query to match the child of the entity.  |
| parentQuery | object | The search query to match the parent of the entity. |

{% tabs %}
{% tab title="200 A result set of entities matching the search query." %}
```javascript
{
  "numFound": 1,
  "entities": [
    {
      "id": 44,
      "revisionId": 0,
      "title": "Rights In",
      "template": {
        "fields": [],
        "templateId": 1,
        "templateName": "Rights In",
        "processId": 0,
        "processName": null
      },
      "status": {
        "statusId": 1,
        "statusName": "Active"
      },
      "characteristics": {
        "media_right": [
          {
            "id": 2,
            "value": "All Media"
          }
        ],
        "actual_term_start": "2020-02-25",
        "territory": [
          {
            "id": 1,
            "value": "Worldwide"
          }
        ],
        "actual_term_end": "2020-02-27",
        "language": [
          {
            "id": 4,
            "value": "All Languages"
          }
        ],
        "exclusivity": {
          "id": 2,
          "value": "Non-Exclusive"
        }
      },
      "comments": null,
      "createdById": 1,
      "createdDate": "2019-05-30T22:35:07.337Z",
      "lastUpdatedById": 1,
      "lastUpdatedDate": "2019-09-05T03:35:52.950Z"
    }
  ]
}
```
{% endtab %}
{% endtabs %}

