# Retrieve catalog item worksheets

## Get catalog item worksheets

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/worksheet`

This endpoint allows you to get the catalog-item worksheets.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Worksheets successfully retrieved." %}
```javascript
[
    {
        "id": "0c6fe0be-a1fe-ef11-835d-065151be1e5f",
        "name": "Worksheet 1"
    },
    {
        "id": "47ac3f2a-9cfe-ef11-835d-065151be1e5f",
        "name": "Worksheet 2"
    }
]
```
{% endtab %}
{% endtabs %}

## Get catalog item worksheet by ID

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/worksheet/:id`

This endpoint allows you to get a catalog-item worksheet by worksheet ID.

#### Path Parameters

| Name | Type   | Description          |
| ---- | ------ | -------------------- |
| id   | string | ID of the worksheet. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Draft templates successfully retrieved." %}
```javascript
{
    "records": {
        "1": [
            {
                "id": 38086,
                "title": "Catalog Item 1"
            },
            {
                "id": 38085,
                "title": "Catalog Item 2"
            },
            {
                "id": 38454,
                "title": "Catalog Item 3"
            }
        ]
    },
    "createdDate": "2025-03-11T17:53:32.733Z",
    "lastUpdatedDate": "2025-03-11T17:53:32.733Z",
    "id": "0c6fe0be-a1fe-ef11-835d-065151be1e5f",
    "name": "Worksheet 1"
}
```
{% endtab %}
{% endtabs %}
