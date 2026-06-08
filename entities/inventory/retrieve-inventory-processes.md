# Retrieve inventory workflow processes

## Get inventory workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/inventory-processes`

This endpoint allows you to retrieve workflow processes for inventory.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Inventory processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 16,
            "processName": "Inventory Workflow",
            "sequenceNumber": 1,
            "description": "Inventory Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

