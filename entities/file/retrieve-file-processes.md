# Retrieve file workflow processes

## Get file workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/file-processes`

This endpoint allows you to retrieve workflow processes for files.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 File processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 7,
            "processName": "Document Workflow",
            "sequenceNumber": 1,
            "description": "Document Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

