# Update an amount

## Update amount

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/amount/:id`

This endpoint allows you to update an amount record.

#### Path Parameters

| Name | Type    | Description                 |
| ---- | ------- | --------------------------- |
| id   | integer | ID of the amount to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Amount successfully updated." %}
```javascript
{
  "parentRelationship": [
    {
      "id": 6240018,
      "parentURL": "https://api.rightsline.com/v3/relationship/6240000",
      "childURL": "https://api.rightsline.com/v3/amount/1",
      "relationshipType": {
        "relationshipTypeId": 0,
        "relationshipTypeName": "Default"
      },
      "createdById": 1,
      "createdDate": "2015-08-25T21:16:12.980Z",
      "lastUpdatedById": 1,
      "lastUpdatedDate": "2015-08-25T21:30:56.993Z",
      "parentCharTypeId": 0,
      "parentRecordId": 6240000,
      "childCharTypeId": 10,
      "childRecordId": 1,
      "sequenceNumber": 32646852608
    }
  ],
  "relationshipUpdateRules": null,
  "id": 1,
  "revisionId": 0,
  "title": "Fee Record 1",
  "template": {
    "fields": [],
    "templateId": 2,
    "templateName": "Fee",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Amount Created"
  },
  "characteristics": {},
  "comments": [],
  "createdById": 296252,
  "createdDate": "2015-09-01T19:45:44.490Z",
  "lastUpdatedById": 3,
  "lastUpdatedDate": "2016-08-18T03:05:25.920Z"
}
```
{% endtab %}
{% endtabs %}
