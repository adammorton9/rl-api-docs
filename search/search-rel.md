---
description: Search for a relationship between two entities.
---

# Relationship search

## Relationship search

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/relationship/search`

This endpoint allows you to search for a specific relationship between entities.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name       | Type   | Description                       |
| ---------- | ------ | --------------------------------- |
| query      | string | The search query.                 |
| sortOrders | array  | The order to sort the result set. |

{% tabs %}
{% tab title="200 A result set of relationships that match the search query." %}
```javascript
{
  "numFound": 1,
  "entities": [
    {
      "id": 401961455,
      "relationshipType": {
        "relationshipTypeId": 0,
        "relationshipTypeName": "Default"
      },
      "createdById": 1,
      "createdDate": "2020-06-03T02:09:48.970Z",
      "lastUpdatedById": 1,
      "lastUpdatedDate": "2020-06-03T02:09:48.970Z",
      "parentCharTypeId": 4,
      "parentRecordId": 1000,
      "parentTemplate": {
        "templateId": 1,
        "templateName": "Rights In"
      },
      "parentStatus": {
        "statusId": 1,
        "statusName": "Active"
      },
      "childCharTypeId": 1,
      "childRecordId": 1,
      "childTemplate": {
        "templateId": 1,
        "templateName": "Feature"
      },
      "childStatus": {
      "statusId": 1,
        "statusName": "Active"
      },
      "sequenceNumber": 1482159542272
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Example Request

#### Request all relationships between deal ID #4 and child rights, sorted by most recently created date.

```javascript
{
    "query": {
        "$and":[
            {"$eq":["parentrecordid", 4]},
            {"$eq":["parentchartypeid", 4]},
            {"$eq":["childchartypeid", 3]}
        ]
    },
    "sortOrders": [
        "created desc"
    ]
}

```
