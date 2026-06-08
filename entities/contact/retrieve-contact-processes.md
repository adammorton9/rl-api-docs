# Retrieve contact workflow processes

## Get contact workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/contact-processes`

This endpoint allows you to retrieve workflow processes for contacts.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Contacts processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 2,
            "processName": "Contact Workflow",
            "sequenceNumber": 1,
            "description": "Contact Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
