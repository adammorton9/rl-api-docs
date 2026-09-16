# Retrieve a process

## Get process

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/process/:id`

This endpoint allows you to retrieve a specific process by ID.

#### Path Parameters

| Name | Type    | Description                    |
| ---- | ------- | ------------------------------ |
| id   | integer | ID of the process to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Process successfully retrieved." %}
```json
{
  "parentRelationship": null,
  "id": 100,
  "revisionId": 0,
  "title": "Test Process",
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
  "lastUpdatedDate": "2024-01-15T10:00:00.000Z"
}
```
{% endtab %}

{% tab title="404 Could not find a process with this ID." %}
```json
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
