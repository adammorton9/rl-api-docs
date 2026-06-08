# Retrieve a financial document

## Get financial document

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/financial-document/:id`

This endpoint allows you to retrieve a specific financial document by ID.

#### Path Parameters

| Name | Type   | Description                               |
| ---- | ------ | ----------------------------------------- |
| id   | string | ID of the financial document to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial document successfully retrieved." %}
```javascript
{
  "parentRelationship": null,
  "relationshipUpdateRules": null,
  "id": 1,
  "revisionId": 0,
  "title": "Invoice Record 1",
  "template": {
    "fields": [],
    "templateId": 1,
    "templateName": "Invoice",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 2,
    "statusName": "Billing Document Drafted"
  },
  "characteristics": {
    "due_date": "2015-10-21"
  },
  "comments": [],
  "createdById": 296242,
  "createdDate": "2015-10-27T17:34:26.160Z",
  "lastUpdatedById": 296242,
  "lastUpdatedDate": "2015-10-28T22:15:42.633Z"
}
```
{% endtab %}

{% tab title="404 Could not find a financial document with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

