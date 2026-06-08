# Retrieve a project

## Get project

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/project/:id`

This endpoint allows you to retrieve a specific project by ID.

#### Path Parameters

| Name | Type   | Description                    |
| ---- | ------ | ------------------------------ |
| id   | string | ID of the project to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Project successfully retrieved." %}
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

{% tab title="404 Could not find project with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

