# Update a financial document

## Update financial document

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/financial-document/:id`

This endpoint allows you to update a financial document.

#### Path Parameters

| Name | Type    | Description                             |
| ---- | ------- | --------------------------------------- |
| id   | integer | ID of the financial document to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type    | Description                                          |
| ------------------- | ------- | ---------------------------------------------------- |
| title               | string  | The new title of the financial document.             |
| template            | object  | The template of the financial document to update.    |
| template.templateId | integer | The template ID of the financial document to update. |
| characteristics     | object  | The fields to update on the financial document.      |

{% tabs %}
{% tab title="200 Financial document successfully updated." %}
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
{% endtabs %}

