# Retrieve right workflow processes

## Get right workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/right-processes`

This endpoint allows you to retrieve workflow processes for rights.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Right processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 17,
            "processName": "Rights Workflow",
            "sequenceNumber": 1,
            "description": "Rights Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

