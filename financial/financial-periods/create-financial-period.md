# Create financial period

## Create a single financial period

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/financial-periods`

This endpoint creates a single financial period.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                        | Type      | Description                               |
| ------------------------------------------- | --------- | ----------------------------------------- |
| year<mark style="color:red;">\*</mark>      | number    | Year of the financial period              |
| period<mark style="color:red;">\*</mark>    | number    | Ordinal sequence of the financial period. |
| startDate<mark style="color:red;">\*</mark> | Date Time | Start of financial period                 |
| endDate<mark style="color:red;">\*</mark>   | Date Time | End of financial period                   |

{% tabs %}
{% tab title="200 Financial period successfully updated." %}
```javascript
{
    "id": 1934,
    "year": 2026,
    "period": 1,
    "startDate": "2026-12-01T08:00:00.000Z",
    "endDate": "2026-12-31T08:00:00.000Z",
    "status": "Open"
}
```
{% endtab %}

{% tab title="400: Bad Request Invalid financial period" %}
```javascript

{
    "message": "Please provide a valid end date."
}



{
    "message": "Please provide a valid start date."
}

{
    "message": "Please specify a valid period."
}

{
    "message": "Please provide a valid year."
}
```
{% endtab %}
{% endtabs %}
