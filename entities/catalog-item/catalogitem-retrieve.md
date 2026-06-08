# Retrieve a catalog item

## Get catalog item

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/catalog-item/:id`

This endpoint allows you to retrieve a specific catalog item by ID.

#### Path Parameters

| Name | Type   | Description                         |
| ---- | ------ | ----------------------------------- |
| id   | string | ID of the catalog item to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Catalog item successfully retrieved." %}
```javascript
{
  "parentRelationship": [
   {
      "id": 255317359,
      "relationshipType": {
        "relationshipTypeId": 0,
        "relationshipTypeName": "Default"
      },
      "createdById": 1,
      "createdDate": "2019-10-30T20:54:23.297Z",
      "lastUpdatedById": 1,
      "lastUpdatedDate": "2019-10-30T20:54:23.297Z",
      "parentCharTypeId": 4,
      "parentRecordId": 1,
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
      "sequenceNumber": 992654028800
    }
  ],
  "relationshipUpdateRules": null,
  "id": 1,
  "revisionId": 0,
  "title": "The Three Stooges",
  "template": {
    "fields": [],
    "templateId": 1,
    "templateName": "Collection",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Active"
  },
  "characteristics": {
    "release_year": 1925
  },
  "comments": [],
  "createdById": 1,
  "createdDate": "2015-08-25T21:07:02.487Z",
  "lastUpdatedById": 1,
  "lastUpdatedDate": "2020-05-02T02:17:13.717"
  }
```
{% endtab %}

{% tab title="404 Could not find a catalog item with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

