---
description: Add a new value to a master list of values.
---

# Add value to master list

## Add value to master list

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/master-value-list/:listID/value`

This endpoint allows you to add a value to a master value list.

#### Path Parameters

| Name                                     | Type | Description                |
| ---------------------------------------- | ---- | -------------------------- |
| listID<mark style="color:red;">\*</mark> | guid | The ID of the master list. |

#### Headers

| Name                                            | Type   | Description             |
| ----------------------------------------------- | ------ | ----------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | Authorization token.    |
| x-api-key<mark style="color:red;">\*</mark>     | String | Your company's API key. |
| Content-Type<mark style="color:red;">\*</mark>  | String | application/json        |

#### Request Body

| Name                                          | Type   | Description        |
| --------------------------------------------- | ------ | ------------------ |
| label<mark style="color:red;">\*</mark>       | String | Value label.       |
| description<mark style="color:red;">\*</mark> | String | Value description. |
| xref                                          | String | Value XREF.        |
| status                                        | String | Active/Inactive    |

{% tabs %}
{% tab title="409: Conflict Value already exists." %}
```javascript
{
    "message": "Char value set {master-value-list-id} already contains a value with the label {label}. Please update the label field in your request and try again."
}
```
{% endtab %}

{% tab title="404: Not Found Master value list not found." %}
```javascript
{
    "message": "No char value set found with ID {master-value-list-id}"
}
```
{% endtab %}

{% tab title="200: OK Value created successfully." %}
Value was created successfully.  New master list values are returned.

```javascript
[
    {
        "id": 1,
        "label": "A",
        "description": "the letter A",
        "xref": "A",
        "status": "Active"
    },
    {
        "id": 2,
        "label": "B",
        "description": "the letter B",
        "xref": "B",
        "status": "Active"
    }
]
```
{% endtab %}
{% endtabs %}
