# Update a royalty

## Update royalty

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/royalty/:id`

Update the characteristics of a royalty.

#### Path Parameters

| Name | Type    | Description                      |
| ---- | ------- | -------------------------------- |
| id   | integer | The ID of the royalty to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                    |
| ------------------- | ------ | -------------------------------------------------------------- |
| title               | string | The new title of the royalty.                                  |
| template            | object | The template of the royalty.                                   |
| template.templateId | string | The unique ID of the template that is assigned to the royalty. |
| characteristics     | object | The field values to update on the royalty.                     |

{% tabs %}
{% tab title="200 Royalty updated successfully." %}
```json
{
  "parentRelationship": null,
  "id": 100,
  "revisionId": 0,
  "title": "Updated Royalty",
  "template": {
    "fields": [],
    "templateId": 1,
    "templateName": "Standard Royalty",
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
