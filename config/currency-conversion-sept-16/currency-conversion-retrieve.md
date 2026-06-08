# Retrieve a currency conversion

## Retrieve currency conversion

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/currency/conversion/:id`

This endpoint retrieves a specific currency conversion.

#### Path Parameters

| Name | Type   | Description                                    |
| ---- | ------ | ---------------------------------------------- |
| id   | string | The ID of the currency conversion to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Currency conversion successfully retrieved." %}
```javascript
{
    "id": "45d01ae0-a14e-41ff-17fe-4e51e39babb1",
    "companyCurrency": "USD",
    "transactionCurrency": "AUD",
    "rate": 1.000000000,
    "effectiveDate": "2020-09-01T00:00:00.000Z"
}
```
{% endtab %}
{% endtabs %}
