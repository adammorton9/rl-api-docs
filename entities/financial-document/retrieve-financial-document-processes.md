# Retrieve financial document workflow processes

## Get financial document workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/financial-document-processes`

This endpoint allows you to retrieve workflow processes for financial documents.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial document processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 10,
            "processName": "Billing Doc Workflow",
            "sequenceNumber": 1,
            "description": "Billing Doc Workflow Description"
        },
        {
            "processId": 25,
            "processName": "Accounting Workflow",
            "sequenceNumber": 2,
            "description": "Accounting Workflow Description"
        },
        {
            "processId": 68,
            "processName": "Expense Workflow",
            "sequenceNumber": 3,
            "description": "Expense Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

