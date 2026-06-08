# Retrieve an amount

## Get amount

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/amount/:id`

This endpoint allows you to retrieve a specific amount by ID.

#### Path Parameters

| Name | Type   | Description                   |
| ---- | ------ | ----------------------------- |
| id   | string | ID of the amount to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Amount successfully retrieved." %}
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
      "parentTemplate": {
          "templateId": 1,
          "templateName": "Acquisition Deal",
          "templateGroupId": 0,
          "systemIndicatorId": 0,
          "processId": 0
      },
      "parentStatus": {
          "statusId": 19,
          "statusName": "Active"
      },
      "parentCharTypeId": 4,
      "parentRecordId": 1,
      "childCharTypeId": 1,
      "childRecordId": 1,
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

{% tab title="404 Could not find an amount with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
