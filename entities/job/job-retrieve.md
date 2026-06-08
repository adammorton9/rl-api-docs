# Retrieve a job

## Get job

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/job/:id`

This endpoint allows you to retrieve a specific job by ID.

#### Path Parameters

| Name | Type   | Description                |
| ---- | ------ | -------------------------- |
| id   | string | ID of the job to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Job successfully retrieved." %}
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

{% tab title="404 Could not find a job with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

