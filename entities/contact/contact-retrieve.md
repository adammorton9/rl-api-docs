# Retrieve a contact

## Get contact

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/contact/:id`

This endpoint allows you to retrieve a specific contact by ID.

#### Path Parameters

| Name | Type   | Description                    |
| ---- | ------ | ------------------------------ |
| id   | string | ID of the contact to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Contact exists.  Return contact entity." %}
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

{% tab title="404 Contact does not exist." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
