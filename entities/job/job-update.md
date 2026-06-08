# Update a job

## Update job

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/job/:id`

Update the characteristics of a job.

#### Path Parameters

| Name | Type   | Description                  |
| ---- | ------ | ---------------------------- |
| id   | string | The ID of the job to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                |
| ------------------- | ------ | ---------------------------------------------------------- |
| title               | string | The new title of the job.                                  |
| template            | object | The template of the job.                                   |
| template.templateId | string | The unique ID of the template that is assigned to the job. |
| characteristics     | object | The field values to update on the job.                     |
| parentRelationship  | array  | Create this job as a child of other entities.              |

{% tabs %}
{% tab title="200 Job updated successfully." %}
```javascript
{
  "parentRelationship": null,
  "relationshipUpdateRules": null,
  "id": 2200,
  "revisionId": 0,
  "title": "The updated job",
  "template": {
    "fields": [],
    "templateId": 2,
    "templateName": "Delivery In",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Active"
  },
  "characteristics": {
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

