# Retrieve a table row

## Get table row

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/table/:id`

This endpoint allows you to retrieve a specific table row by ID.

#### Path Parameters

| Name | Type   | Description                      |
| ---- | ------ | -------------------------------- |
| id   | string | ID of the table row to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Table row successfully retrieved." %}
```javascript
{
  "parentRelationship": [
    {
      "id": 6240000,
      "relationshipType": {
        "relationshipTypeId": 0,
        "relationshipTypeName": "Default"
      },
      "createdById": 100,
      "createdDate": "2015-08-25T21:16:12.980Z",
      "lastUpdatedById": 100,
      "lastUpdatedDate": "2015-08-25T21:30:56.993Z",
      "parentTemplate": {
          "templateId": 1,
          "templateName": "Acquisition Deal",
          "templateGroupId": 0,
          "systemIndicatorId": 0,
          "processId": 0
      },
      "parentStatus": {
          "statusId": 19,
          "statusName": "Active"
      },
      "parentCharTypeId": 4,
      "parentRecordId": 4,
      "childCharTypeId": 5,
      "childRecordId": 8,
      "sequenceNumber": 32653332480
    }
  ],
  "relationshipUpdateRules": null,
  "id": 8,
  "revisionId": 0,
  "title": "Payment Schedule Record 8",
  "template": {
    "fields": [],
    "templateId": 21,
    "templateName": "Payment Schedule",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Created"
  },
  "characteristics": {
    "fee_type": [
      {
        "id": 17,
        "value": "Distribution Deal"
      }
    ],
    "fee_status": {
      "id": 5,
      "value": "Pending"
    }
  },
  "comments": [],
  "createdById": 100,
  "createdDate": "2015-09-01T19:45:10.327Z",
  "lastUpdatedById": 100,
  "lastUpdatedDate": "2018-10-30T05:54:26.543Z"
}
```
{% endtab %}

{% tab title="404 Could not find a table row with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

