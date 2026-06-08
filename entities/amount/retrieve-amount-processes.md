# Retrieve amount workflow processes

## Get amount workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/amount-processes`

This endpoint allows you to retrieve workflow processes for amounts.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Amount processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 8,
            "processName": "Amount Workflow",
            "sequenceNumber": 10,
            "description": "Amount Workflow"
        },
        {
            "processId": 38,
            "processName": "Locked Amounts",
            "sequenceNumber": 21,
            "description": "Locked Amounts"
        },
        {
            "processId": 64,
            "processName": "Advance Payment Workflow",
            "sequenceNumber": 48,
            "description": "Advance Payment Workflow"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
