# Retrieve table workflow processes

## Get table workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/table-processes`

This endpoint allows you to retrieve workflow processes for rights.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Table processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 6,
            "processName": "Table Workflow",
            "sequenceNumber": 1,
            "description": "Table Workflow Description"
        },
        {
            "processId": 14,
            "processName": "Deliverable Workflow",
            "sequenceNumber": 2,
            "description": "Deliverable Workflow Description"
        },
        {
            "processId": 18,
            "processName": "Usages Workflow",
            "sequenceNumber": 3,
            "description": "Usages Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

