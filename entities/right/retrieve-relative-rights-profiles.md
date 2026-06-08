# Retrieve relative rights profiles

## Get relative rights profiles

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/relative-rights-profile`

This endpoint allows you to retrieve the relative rights profiles.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Relative rights profiles retrieved successfully." %}
```json
[
    {
        "id": 12,
        "title": "Relative Rights Profiles Record 12"
    },
    {
        "id": 14,
        "title": "Relative Rights Profiles Record 14"
    },
    {
        "id": 16,
        "title": "Relative Rights Profiles Record 16"
    },
    {
        "id": 4,
        "title": "Relative Rights Profiles Record 4"
    },
    {
        "id": 7,
        "title": "Relative Rights Profiles Record 7"
    },
    {
        "id": 8,
        "title": "Relative Rights Profiles Record 8"
    }
]
```
{% endtab %}
{% endtabs %}
