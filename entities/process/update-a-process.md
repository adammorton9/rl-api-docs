# Update a process

## Update process

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/process/:id`

Update the characteristics of a process.

#### Path Parameters

| Name | Type    | Description                      |
| ---- | ------- | -------------------------------- |
| id   | integer | The ID of the process to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                    |
| ------------------- | ------ | -------------------------------------------------------------- |
| title               | string | The new title of the process.                                  |
| template            | object | The template of the process.                                   |
| template.templateId | string | The unique ID of the template that is assigned to the process. |
| characteristics     | object | The field values to update on the process.                     |

{% tabs %}
{% tab title="200 Process updated successfully." %}
```json
{
  "parentRelationship": null,
  "id": 100,
  "revisionId": 0,
  "title": "Updated Process",
  "template": {
    "fields": [],
    "templateId": 1,
    "templateName": "Standard Process",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Active"
  },
  "characteristics": {},
  "comments": [],
  "createdById": 1,
  "createdDate": "2024-01-15T10:00:00.000Z",
  "lastUpdatedById": 1,
  "lastUpdatedDate": "2024-06-01T14:30:00.000Z"
}
```
{% endtab %}
{% endtabs %}
