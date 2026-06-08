# Retrieve a deal

## Get deal

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/deal/:id`

This endpoint allows you to retrieve a specific deal by ID.

#### Path Parameters

| Name | Type   | Description                 |
| ---- | ------ | --------------------------- |
| id   | string | ID of the deal to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Deal successfully retrieved." %}
```javascript
{
  "parentRelationship": null,
  "relationshipUpdateRules": null,
  "id": 100,
  "revisionId": 0,
  "title": "Test Deal",
  "template": {
    "fields": [],
    "templateId": 2,
    "templateName": "Distribution Deal",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 2,
    "statusName": "Created"
  },
  "characteristics": {
    "contract_term_start": "1900-09-09",
    "deal_amount_money": {
      "locAmt": "",
      "locCur": 1,
      "locSym": "USD",
      "divAmt": null,
      "divCur": null,
      "divSym": null
    }
  },
  "comments": [],
  "createdById": 0,
  "createdDate": "2019-10-18T03:09:20.763Z",
  "lastUpdatedById": 0,
  "lastUpdatedDate": "2020-05-29T02:19:04.240Z"
}
```
{% endtab %}

{% tab title="404 Could not find a deal with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
