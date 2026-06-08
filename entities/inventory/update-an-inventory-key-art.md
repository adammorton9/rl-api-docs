# Update an inventory key art

## Update an inventory key art

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/inventory/:id/keyart`

This endpoint allows you to update the key art for an inventory.

#### Path Parameters

| Name | Type    | Description               |
| ---- | ------- | ------------------------- |
| id   | integer | ID of the inventory item. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name     | Type   | Description              |
| -------- | ------ | ------------------------ |
| fileName | string | The key art file name.   |
| label    | string | The key art description. |

{% tabs %}
{% tab title="200 Key art updated. Upload key art image to URL." %}
```javascript
{
    "id": 2687,
    "link": {
        "url": "https://de324y6j768fq1.cloudfront.net/************",
        "expiration": "2021-04-20T22:44:58.314Z"
    }
}
```
{% endtab %}
{% endtabs %}

