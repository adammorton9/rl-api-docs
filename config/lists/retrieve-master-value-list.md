# Retrieve master value list

These endpoints allow you to retrieve the values of a master value list(s).

## Get master value list

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/master-value-list`

This endpoint allows you to retrieve the master value list.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 List retrieved successfully." %}
```javascript
[
    {
        "id": "196949bc-ea41-e511-9457-0af1f058195a",
        "name": " Audio Bitrate Kbps"
    },
    {
        "id": "1f6949bc-ea41-e511-9457-0af1f058195a",
        "name": " Audio Bits Per Sample"
    },
    {
        "id": "246949bc-ea41-e511-9457-0af1f058195a",
        "name": " Audio Codec"
    },
    {
        "id": "276949bc-ea41-e511-9457-0af1f058195a",
        "name": " Audio Container"
    }
]
```
{% endtab %}
{% endtabs %}

## Get master value list by ID

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/master-value-list/:id`

This endpoint allows you to retrieve a list by ID.

#### Path Parameters

| Name | Type   | Description                         |
| ---- | ------ | ----------------------------------- |
| id   | string | GUID of the master value list item. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 List item retrieved successfully." %}
```javascript
{
        "id": "196949bc-ea41-e511-9457-0af1f058195a",
        "name": " Audio Bitrate Kbps",
        "values": [
            {
                "id": 1,
                "label": "1125",
                "xref": null,
                "status": "Active"
            },
            {
                "id": 2,
                "label": "96",
                "xref": null,
                "status": "Active"
            },
            {
                "id": 3,
                "label": "320",
                "xref": null,
                "status": "Active"
            }
        ]
    }
```
{% endtab %}
{% endtabs %}

