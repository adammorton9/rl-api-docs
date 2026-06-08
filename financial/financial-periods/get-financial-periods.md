# Get financial periods

## Retrieve financial periods list.

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/financial-periods`

This endpoint retrieves an array of all financial periods

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial Periods successfully retrieved." %}
```javascript
[
    {
        "id": 309,
        "year": 2022,
        "period": 5,
        "startDate": "2022-05-01T00:00:00.0000000",
        "endDate": "2022-05-31T00:00:00.0000000",
        "status": "Closed"
    },
    {
        "id": 310,
        "year": 2022,
        "period": 6,
        "startDate": "2022-06-01T07:00:00.0000000",
        "endDate": "2022-06-30T07:00:00.0000000",
        "status": "Current"
    },
    {
        "id": 311,
        "year": 2022,
        "period": 7,
        "startDate": "2022-07-01T07:00:00.0000000",
        "endDate": "2022-07-31T07:00:00.0000000",
        "status": "Future"
    },
    ...
]
```
{% endtab %}
{% endtabs %}
