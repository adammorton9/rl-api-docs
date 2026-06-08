# Get applications

## Get user applications

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/user/app`

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK User applications retrieved successfully." %}
```json
[
    {
        "id": 24,
        "name": "Some Company",
        "url": "https://admin.rightsline.com/",
        "urlTypeId": "3"
    },
    {
        "id": 45,
        "name": "UX2 - Some Company",
        "url": "https://app.rightsline.com/",
        "urlTypeId": "4"
    }
]
```
{% endtab %}
{% endtabs %}
