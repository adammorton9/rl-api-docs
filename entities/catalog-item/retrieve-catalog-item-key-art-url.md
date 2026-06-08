---
description: Used to retrieve key art for a catalog item.
---

# Retrieve catalog item key art URL

## Get catalog item key art URL

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/catalog-item/:id/keyart/url`

This endpoint allows you to retrieve the URL to download the key art for a catalog item.

#### Path Parameters

| Name | Type   | Description             |
| ---- | ------ | ----------------------- |
| id   | string | ID of the catalog item. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Key art URL successfully retrieved. Use the URL to retrieve the key art." %}
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

{% tab title="404 Could not find key art for the catalog item." %}
```javascript
{    
    "message": "No keyart found."
}
```
{% endtab %}
{% endtabs %}

