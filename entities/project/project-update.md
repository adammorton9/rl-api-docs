# Update a project

## Update project item

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/project/:id`

Update the characteristics of a project.

#### Path Parameters

| Name | Type   | Description                      |
| ---- | ------ | -------------------------------- |
| id   | string | The ID of the project to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                    |
| ------------------- | ------ | -------------------------------------------------------------- |
| title               | string | The new title of the project.                                  |
| template            | object | The template of the project.                                   |
| template.templateId | string | The unique ID of the template that is assigned to the project. |
| characteristics     | object | The field values to update on the project.                     |
| parentRelationship  | array  | Create this project as a child of other entities.              |

{% tabs %}
{% tab title="200 Project updated successfully." %}
```javascript
{
    "parentRelationship": null,
    "relationshipUpdateRules": null,
    "parentRelationshipCount": 13,
    "id": 1,
    "revisionId": 0,
    "title": "test",
    "template": {
        "templateId": 4,
        "templateName": "Sample",
        "processId": 0,
        "processName": null
    },
    "status": {
        "statusId": 3,
        "statusName": "Consider"
    },
    "characteristics": {
        "date_received": "2019-08-17"
    },
    "comments": [],
    "createdById": 46232,
    "createdDate": "2015-08-19T17:57:02.213Z",
    "lastUpdatedById": 611853,
    "lastUpdatedDate": "2021-05-06T22:32:06.263Z",
    "statusUpdatedById": 611853,
    "statusUpdatedDate": "2019-02-05T18:28:18.777Z"
}
```
{% endtab %}
{% endtabs %}

