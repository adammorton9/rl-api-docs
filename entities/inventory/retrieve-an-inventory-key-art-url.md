---
description: Used to retrieve key art for an inventory item.
---

# Retrieve an inventory key art URL

## Get inventory key art URL

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/inventory/:id/keyart/url`

This endpoint allows you to retrieve the URL for an inventory key art.

#### Path Parameters

| Name | Type    | Description          |
| ---- | ------- | -------------------- |
| id   | integer | ID of the inventory. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Key art URL successfully retrieved.  Use URL to retrieve the key art." %}
```javascript
{
    "id": 2687,
    "link": {
        "url": "https://************.cloudfront.net/*****************",
        "expiration": "2021-04-20T22:45:26.296Z"
    }
}
```
{% endtab %}

{% tab title="404 Key art not found for this inventory item." %}
```javascript
{    
    "message": "No keyart found."
}
```
{% endtab %}
{% endtabs %}

