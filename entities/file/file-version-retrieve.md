# Retrieve File Version

## Get File entity for a specific file version

<mark style="color:blue;">`GET`</mark> `http://ris.rightsline.com/v4/file/:id-:revisionId/url`

This endpoint allows you to retrieve a version of a file.

#### Path Parameters

| Name       | Type   | Description                                                                    |
| ---------- | ------ | ------------------------------------------------------------------------------ |
| id         | number | ID of the file.                                                                |
| revisionId | number | Revision Id of the file. Get from [.../revisions](file-revisions-retrieve.md). |

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

{% tab title="404: Not Found No version found for the record." %}
```javascript
{
    "message": "Revision 0 not found on record: 3534"
}
```
{% endtab %}
{% endtabs %}

