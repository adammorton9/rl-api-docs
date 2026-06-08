---
description: Remove a value from a master list of values.
---

# Remove value from master list

This endpoint allows you to remove a value from a master value list.  Values may only be removed from a master value list of they are not currently in use by any pick list.

## Delete a value from a master value list

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/master-value-list/:listID/value/:valueID`

#### Path Parameters

| Name                                      | Type | Description               |
| ----------------------------------------- | ---- | ------------------------- |
| listID<mark style="color:red;">\*</mark>  | guid | The master value list ID. |
| valueID<mark style="color:red;">\*</mark> | int  | The value ID.             |

#### Headers

| Name                                            | Type   | Description             |
| ----------------------------------------------- | ------ | ----------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | Authorization token.    |
| x-api-key<mark style="color:red;">\*</mark>     | String | Your company's API key. |

{% tabs %}
{% tab title="404: Not Found Master value list not found." %}
```javascript
{
    "message": "No char value set found with ID {master-value-list-id}"
}
```
{% endtab %}

{% tab title="404: Not Found Value not found in master value list." %}
```javascript
{
    "message": "Char value set {master-value-list-id} does not contain a value with ID {value-id}."
}
```
{% endtab %}

{% tab title="403: Forbidden Permission denied." %}
```javascript
{
    "message": "Acls don't provide permission to delete values from master lists."
}
```
{% endtab %}

{% tab title="200: OK Value deleted from master list." %}
Value was deleted from the master list. New master list of values is returned.

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
