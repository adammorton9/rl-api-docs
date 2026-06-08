# Retrieve all currency conversions

## Retrieve currency conversion list

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/currency/conversion/list`

This endpoint retrieves an array of all currency conversions.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Currency conversions successfully retrieved." %}
```javascript
[
    {
        "id": "49d04ae0-e15e-42df-93fe-4e29e39bfbb1",
        "companyCurrency": "USD",
        "transactionCurrency": "AUD",
        "rate": 1.000000000,
        "effectiveDate": "2020-09-01T00:00:00.000Z"
    },
    {
        "id": "cbf00fda-0980-49e3-826b-44d8826d162e",
        "companyCurrency": "USD",
        "transactionCurrency": "CAD",
        "rate": 2.000000000,
        "effectiveDate": "2020-05-01T00:00:00.000Z"
    },
    {
        "id": "f04f3c89-7a11-4fcb-bd94-4731fe5e3841",
        "companyCurrency": "USD",
        "transactionCurrency": "EUR",
        "rate": 2.000000000,
        "effectiveDate": "2020-05-01T00:00:00.000Z"
    },
    {
        "id": "a211390d-3e53-4486-9caf-071478e6e7d8",
        "companyCurrency": "USD",
        "transactionCurrency": "GBP",
        "rate": 1.000000000,
        "effectiveDate": "2020-09-01T00:00:00.000Z"
    }
]
```
{% endtab %}
{% endtabs %}

