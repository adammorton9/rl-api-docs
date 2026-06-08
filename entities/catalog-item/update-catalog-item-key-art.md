---
description: Upload/update the key art for a catalog item.
---

# Upload/update catalog item key art

Uploading key art for a catalog item is done in two steps:

1. Creating the key art reference in Rightsline
2. Uploading the image&#x20;

To create the key art reference in Rightsline, use the following endpoint:

## Update catalog item key art

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/catalog-item/:id/keyart`

This endpoint allows you to update the key art for a catalog item.

#### Path Parameters

| Name | Type    | Description             |
| ---- | ------- | ----------------------- |
| id   | integer | ID of the catalog item. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name     | Type   | Description                     |
| -------- | ------ | ------------------------------- |
| fileName | string | Key art file name.              |
| label    | string | The description of the key art. |

{% tabs %}
{% tab title="200 Key art updated. Upload key art image to the URL." %}
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

Then you can upload the image by sending a PUT request to the URL returned in the previous response.
