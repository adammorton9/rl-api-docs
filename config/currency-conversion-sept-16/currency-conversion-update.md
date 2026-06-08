# Update a currency conversion

## Update currency conversion

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/currency/conversion/:id`

This endpoint allows you to update a currency conversion.

#### Path Parameters

| Name | Type   | Description                              |
| ---- | ------ | ---------------------------------------- |
| id   | string | ID of the currency conversion to update. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                                  |
| ------------------- | ------ | ---------------------------------------------------------------------------- |
| companyCurrency     | string | The base company currency.                                                   |
| transactionCurrency | string | The new currency.                                                            |
| rate                | string | The conversion rate between the companyCurrency and the transactionCurrency. |
| effectiveDate       | string | The date the conversion takes effect.                                        |

{% tabs %}
{% tab title="200 Currency conversion successfully updated." %}
```javascript
{
    "id": "49d04ae0-e15e-42df-93fe-4e29e39bfbb1",
    "companyCurrency": "USD",
    "transactionCurrency": "AUD",
    "rate": 1.000000000,
    "effectiveDate": "2020-09-01T00:00:00.000Z"
}
```
{% endtab %}
{% endtabs %}
