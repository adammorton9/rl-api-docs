---
description: Retrieve the audit history for a financial document record.
---

# Retrieve financial document audit history

## Get financial document audit history

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/financial-document/:id/audit-history`

This endpoint allows you to retrieve the audit history of a specific financial document by ID.

#### Path Parameters

| Name | Type   | Description                               |
| ---- | ------ | ----------------------------------------- |
| id   | string | ID of the financial document to retrieve. |

#### Query Parameters

| Name         | Type     | Description                                                                      |
| ------------ | -------- | -------------------------------------------------------------------------------- |
| userId       | number   | Filter by actions from a specific user.                                          |
| page         | number   | Paging - The page to retrieve (default 1).                                       |
| rows         | number   | Paging - The number of rows to retrieve (default 10).                            |
| startDate    | dateTime | Return history after this date.                                                  |
| endDate      | dateTime | Return history before this date.                                                 |
| charTypeIds  | int\[]   | An array of char type IDs of related entities to include in the history results. |
| showWorkflow | bool     | Include workflow history in results (default false).                             |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial document history retrieved successfully." %}
```javascript
{
    "totalCount": 1,
    "entries": [
        {
            "isHeader": 1,
            "auditId": "0x00663C390001A63E0008",
            "sequence": "0x00663C390001A63E0002",
            "operationId": 2,
            "operationLabel": "Added",
            "charTypeId": 7,
            "recordId": 1122615,
            "title": "Document Record 1122615",
            "templateId": 1,
            "templateName": "Document",
            "userId": 112151,
            "userName": "Donald Glover",
            "auditDate": "2022-07-07T22:55:49.687Z",
            "changedField": null
        }
    ]
}
```
{% endtab %}

{% tab title="404 Could not find a financial document with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

## Get financial document audit history details

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/financial-document/:id/audit-history-detail`

This endpoint allows you to retrieve the audit history details of a specific audit record.

#### Path Parameters

| Name | Type   | Description                               |
| ---- | ------ | ----------------------------------------- |
| id   | string | ID of the financial document to retrieve. |

#### Query Parameters

| Name                                          | Type    | Description                          |
| --------------------------------------------- | ------- | ------------------------------------ |
| auditId<mark style="color:red;">\*</mark>     | string  | From audit history response.         |
| sequence<mark style="color:red;">\*</mark>    | string  | From audit history response.         |
| operationId<mark style="color:red;">\*</mark> | number  | From audit history response.         |
| isHeader<mark style="color:red;">\*</mark>    | number  | From audit history response.         |
| includeMessages                               | boolean | Include message details in response. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial document history details retrieved successfully." %}
```javascript
{
    "changedField": "notes",
    "oldValue": "old note",
    "newValue": "new note",
    "messageId": "7d664774-c0b5-431a-99a1-978ec257d1fe", // if includeMessages = true
    "destination": "queue-name.fifo", // if includeMessages = true
    "auditDate": "2022-11-09T18:10:10.133Z" // if includeMessages = true
}
```
{% endtab %}

{% tab title="404 Could not find an amount with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
