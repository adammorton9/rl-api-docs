# Delete a currency conversion

## Delete currency conversion

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/currency/conversion/:id`

This endpoint allows you to delete a currency conversion.

#### Path Parameters

| Name | Type   | Description                              |
| ---- | ------ | ---------------------------------------- |
| id   | string | ID of the currency conversion to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authenticat             |

{% tabs %}
{% tab title="200 Currency conversion successfully deleted." %}
```javascript
{
    "message": "Currency conversion deleted."
}
```
{% endtab %}
{% endtabs %}
