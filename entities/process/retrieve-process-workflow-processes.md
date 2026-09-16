# Retrieve process workflow processes

## Get process workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/process-processes`

This endpoint allows you to retrieve workflow processes for the process entity type.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Process workflow processes retrieved successfully." %}
```json
{
    "processes": [
        {
            "processId": 1,
            "processName": "Process Workflow",
            "sequenceNumber": 1,
            "description": "Process Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
