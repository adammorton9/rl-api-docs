# Add values to pick list

This endpoint allows you to add values from a master value list to a specific pick list.  Values may only be added to flat pick lists.  You may not add values to a pick list if the pick list contains any hierarchical values.

## Add values to a pick list

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/pick-list/:listID/value`

#### Path Parameters

| Name                                     | Type | Description       |
| ---------------------------------------- | ---- | ----------------- |
| listID<mark style="color:red;">\*</mark> | guid | The pick list ID. |

#### Headers

| Name                                            | Type   | Description             |
| ----------------------------------------------- | ------ | ----------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | Authorization token.    |
| x-api-key<mark style="color:red;">\*</mark>     | String | Your company's API key. |
| Content-Type<mark style="color:red;">\*</mark>  | String | application/json        |

#### Request Body

| Name                                       | Type  | Description               |
| ------------------------------------------ | ----- | ------------------------- |
| valueIds<mark style="color:red;">\*</mark> | Array | List of value IDs to add. |

{% tabs %}
{% tab title="404: Not Found Pick list not found." %}
```javascript
{
    "message": "No pick list found with ID {pick-list-id}"
}
```
{% endtab %}

{% tab title="404: Not Found Value IDs not found in master list." %}
```javascript
{
    "message": "No values found in master list {master-value-list-id} with IDs {value-ids}"
}
```
{% endtab %}

{% tab title="409: Conflict Pick list is not flat." %}
```javascript
{
    "message": "Pick list {pick-list-id} contains hierarchical values. Values may only be added to flat pick lists."
}
```
{% endtab %}

{% tab title="200: OK Value added to pick list." %}
```javascript
[
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
]
```
{% endtab %}
{% endtabs %}
