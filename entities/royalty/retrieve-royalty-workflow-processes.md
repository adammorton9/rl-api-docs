# Retrieve royalty workflow processes

## Get royalty workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/royalty-processes`

This endpoint allows you to retrieve workflow processes for royalties.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Royalty processes retrieved successfully." %}
```json
{
    "processes": [
        {
            "processId": 1,
            "processName": "Royalty Workflow",
            "sequenceNumber": 1,
            "description": "Royalty Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
