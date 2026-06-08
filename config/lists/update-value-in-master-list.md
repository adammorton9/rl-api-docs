---
description: Update a value in a master list of values.
---

# Update value in master list

## Update value in master list

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/master-value-list/:listID/value/:valueID`

This endpoint allows you to update a value in a master value list.

#### Path Parameters

| Name                                     | Type | Description                    |
| ---------------------------------------- | ---- | ------------------------------ |
| listID<mark style="color:red;">\*</mark> | guid | The ID of the master list.     |
| valueID                                  | int  | The ID of the value to update. |

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
{% tab title="404: Not Found Master value list not found." %}
```javascript
{
    "message": "No char value set found with ID {listID}"
}
```
{% endtab %}

{% tab title="200: OK Value updated successfully." %}
Value was updated successfully.  New master list values are returned.

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

{% tab title="404: Not Found Value not found." %}
```javascript
{
    "message": "Char value set {listID} does not contain a value with ID {valueID}."
}
```
{% endtab %}
{% endtabs %}
