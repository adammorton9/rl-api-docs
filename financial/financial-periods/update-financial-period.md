# Update financial period

## Update a single financial period

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/financial-periods/:id`

This endpoint updates a single financial period.

#### Query Parameters

| Name                               | Type   | Description                |
| ---------------------------------- | ------ | -------------------------- |
| <mark style="color:red;">\*</mark> | number | Id of the financial period |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name      | Type      | Description                               |
| --------- | --------- | ----------------------------------------- |
| year      | number    | Year of the financial period              |
| period    | number    | Ordinal sequence of the financial period. |
| startDate | Date Time | Start of financial period                 |
| endDate   | Date Time | End of financial period                   |

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

{% tab title="404: Not Found Financial Period does not exist" %}
```javascript
{
    "message": "No existing financial period with id: 1931."
}
```
{% endtab %}

{% tab title="400: Bad Request Invalid Financial Period" %}
```javascript
{
    "message": "Please provide a valid end date."
}
{
    "message": "Please provide a valid start date."
}
```
{% endtab %}
{% endtabs %}
