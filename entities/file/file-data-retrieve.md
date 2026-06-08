# Retrieve file data

## Get File URL

<mark style="color:blue;">`GET`</mark> `http://ris.rightsline.com/v4/file/:id/url`

This endpoint allows you to retrieve a download link for a file.

#### Path Parameters

| Name | Type   | Description     |
| ---- | ------ | --------------- |
| id   | number | ID of the file. |

#### Headers

| Name           | Type   | Description           |
| -------------- | ------ | --------------------- |
| Authentication | string | Authentication token. |

{% tabs %}
{% tab title="200 File data retrieved successfully.  Use the URL in the response to retrieve the file." %}
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
{% endtabs %}

