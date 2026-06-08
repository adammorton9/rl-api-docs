# Retrieve deal workflow processes

## Get deal workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/deal-processes`

This endpoint allows you to retrieve workflow processes for deals.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Deals processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 5,
            "processName": "Deal Workflow",
            "sequenceNumber": 1,
            "description": "Deal Workflow Description"
        },
        {
            "processId": 26,
            "processName": "Production Deal Workflow",
            "sequenceNumber": 2,
            "description": "Production Deal Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

