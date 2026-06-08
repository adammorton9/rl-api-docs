# Update a contact

## Update contact

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/contact/:id`

This endpoint allows you to update a contact.

#### Path Parameters

| Name | Type    | Description                  |
| ---- | ------- | ---------------------------- |
| id   | integer | ID of the contact to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type    | Description                               |
| ------------------- | ------- | ----------------------------------------- |
| title               | string  | The new title for the contact.            |
| template            | object  | The template of the contact to update.    |
| template.templateId | integer | The template ID of the contact to update. |
| characteristics     | object  | The fields on the contact to update.      |

{% tabs %}
{% tab title="200 Contact successfully updated." %}
```javascript
{
  "parentRelationship": null,
  "relationshipUpdateRules": null,
  "id": 100,
  "revisionId": 0,
  "title": " ",
  "template": {
    "fields": [],
    "templateId": 1,
    "templateName": "Producer",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Active"
  },
  "characteristics": {},
  "comments": [],
  "createdById": 100,
  "createdDate": "2017-11-28T21:56:52.743Z",
  "lastUpdatedById": 100,
  "lastUpdatedDate": "2019-10-18T04:28:35.790Z"
}
```
{% endtab %}
{% endtabs %}

