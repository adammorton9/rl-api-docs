# Close financial period

## Close a single open financial period

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/financial-periods/:id/close`

This endpoint updates a single financial period. The Financial Period must be in the 'Open' Status, their should only be one financial period available to close at a time.

#### Query Parameters

| Name                               | Type   | Description                |
| ---------------------------------- | ------ | -------------------------- |
| <mark style="color:red;">\*</mark> | number | Id of the financial period |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial period successfully closed." %}
```javascript
{
    "id": 1934,
    "year": 2026,
    "period": 1,
    "startDate": "2026-12-01T08:00:00.000Z",
    "endDate": "2026-12-31T08:00:00.000Z",
    "status": "Closed" <-- This should always say closed when successful
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

{% tab title="400: Bad Request A 'Future' financial period is provided." %}
```json
{
    "message": "Financial period is in the Future."
}
```
{% endtab %}

{% tab title="400: Bad Request A 'Closed' financial period is provided." %}
```json
{
    "message": "Financial period is already Closed."
}
```
{% endtab %}
{% endtabs %}
