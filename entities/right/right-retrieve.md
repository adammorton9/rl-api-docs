# Retrieve a right

## Get right

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/right/:id`

This endpoint allows you to retrieve a specific right by ID.

#### Path Parameters

| Name | Type   | Description                  |
| ---- | ------ | ---------------------------- |
| id   | string | ID of the right to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Right successfully retrieved." %}
```javascript
{
  "parentRelationship": null,
  "relationshipUpdateRules": null,
  "id": 2200,
  "revisionId": 0,
  "title": "The updated right",
  "template": {
    "fields": [],
    "templateId": 2,
    "templateName": "Rights Out",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Active"
  },
  "characteristics": {
    "language": [
      {
        "id": 29,
        "value": "English"
      }
    ]
  },
  "comments": [],
  "createdById": 3,
  "createdDate": "2020-06-25T18:41:08.600Z",
  "lastUpdatedById": 3,
  "lastUpdatedDate": "2020-06-25T19:56:05.187Z"
}
```
{% endtab %}

{% tab title="404 Could not find a right with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

