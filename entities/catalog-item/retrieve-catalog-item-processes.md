# Retrieve catalog item workflow processes

## Get catalog item workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/catalog-item-processes`

This endpoint allows you to retrieve workflow processes for catalog items.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Catalog item processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 4,
            "processName": "Catalog Workflow",
            "sequenceNumber": 1,
            "description": "Catalog Workflow Description"
        },
        {
            "processId": 13,
            "processName": "Inventory Workflow",
            "sequenceNumber": 2,
            "description": "Inventory Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
