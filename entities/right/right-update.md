# Update a right

## Update right

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/right/:id`

Update the characteristics of a right.

#### Path Parameters

| Name | Type   | Description                    |
| ---- | ------ | ------------------------------ |
| id   | string | The ID of the right to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                  |
| ------------------- | ------ | ------------------------------------------------------------ |
| title               | string | The new title of the right.                                  |
| template            | object | The template of the right.                                   |
| template.templateId | string | The unique ID of the template that is assigned to the right. |
| characteristics     | object | The field values to update on the right.                     |
| parentRelationship  | array  | Add or update a parent to this right.                        |

{% tabs %}
{% tab title="200 Rightset updated successfully." %}
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
{% endtabs %}

