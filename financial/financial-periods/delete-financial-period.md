# Delete financial period

## Delete a financial period.

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/financial-periods/:id`

This endpoint deletes a single financial period.

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
{% tab title="200 Financial Period deleted" %}
```javascript
true
```
{% endtab %}

{% tab title="404: Not Found Financial Period does not exist." %}
```javascript
{
    "message": "No existing financial period with id: 1931."
}
```
{% endtab %}
{% endtabs %}
