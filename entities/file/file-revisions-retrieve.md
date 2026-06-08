---
description: Retrieve a list of the existing revisions of a specific file.
---

# Retrieve File Revisions

## Get file revisions

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/file/:id/revisions`

This endpoint allows you to retrieve a list of all the existing revisions of a file.

#### Path Parameters

| Name                                 | Type   | Description                 |
| ------------------------------------ | ------ | --------------------------- |
| id<mark style="color:red;">\*</mark> | string | ID of the file to retrieve. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 File successfully retrieved." %}
```javascript
[
    {
        "id": "3534-0",
        "revision": 0
    }
    {
        "id": "3534-1",
        "revision": 1
    },
    {
        "id": "3534-2",
        "revision": 2
    },
    ...
]
```
{% endtab %}

{% tab title="404 Could not find a file with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}

