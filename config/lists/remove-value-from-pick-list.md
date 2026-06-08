---
description: Remove a value from a pick list.
---

# Remove value from pick list

This endpoint allows you to remove a value from a pick list.  A value may only be removed from a pick list if there are no records that have the value you are attempting to remove.  If a record has a characteristic with this value, you must first update the value on the record before removing the value from the pick list.

## Remove value from pick list

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/pick-list/:listID/value/:valueID`

#### Path Parameters

| Name                                      | Type | Description       |
| ----------------------------------------- | ---- | ----------------- |
| listID<mark style="color:red;">\*</mark>  | guid | The pick list ID. |
| valueID<mark style="color:red;">\*</mark> | int  | The value ID.     |

#### Headers

| Name                                            | Type   | Description             |
| ----------------------------------------------- | ------ | ----------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | Authorization token.    |
| x-api-key<mark style="color:red;">\*</mark>     | String | Your company's API key. |

{% tabs %}
{% tab title="404: Not Found Pick list not found." %}
```javascript
{
    "message": "No pick list found with ID {pick-list-id}"
}
```
{% endtab %}

{% tab title="404: Not Found Value not found in pick list." %}
```javascript
{
    "message": "Pick list {pick-list-id} does not contain a value with ID {value-id}"
}
```
{% endtab %}

{% tab title="409: Conflict Pick list is not flat." %}
```javascript
{
    "message": "Pick list {pick-list-id} contains hierarchical values. Values may only be removed from flat pick lists."
}
```
{% endtab %}

{% tab title="403: Forbidden Permission denied." %}
```javascript
{
    "message": "Acls don't provide permission to remove values from pick lists."
}
```
{% endtab %}

{% tab title="200: OK Value removed from pick list." %}
```javascript
{
    "id": "28352549-f014-4c71-b85f-2c49778bf9ed",
    "name": "Letters",
    "values": [
        {
            "id": 1,
            "label": "A",
            "description": "The letter A",
            "xref": "A",
            "status": "Active"
        },
        {
            "id": 2,
            "label": "B",
            "description": "The letter B",
            "xref": "B",
            "status": "Active"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
