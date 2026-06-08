# Create a currency conversion

## Create currency conversion

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/currency/conversion`

This endpoint allows you to create a currency conversion.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                                   |
| ------------------- | ------ | ----------------------------------------------------------------------------- |
| companyCurrency     | string | The base company currency.                                                    |
| transactionCurrency | string | The new currency.                                                             |
| rate                | number | The conversion rate between the companyCurrency and the transactionCurrency.  |
| effectiveDate       | string | The date the conversion takes effect.                                         |

{% tabs %}
{% tab title="200 Currency conversion successfully created." %}
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

### Sample Request

```javascript
{
    "companyCurrency": "USD",
    "transactionCurrency": "AUD",
    "rate": 1.000000000,
    "effectiveDate": "2020-09-01T00:00:00.000Z"
}
```
