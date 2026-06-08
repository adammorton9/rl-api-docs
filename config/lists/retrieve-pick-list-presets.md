---
description: Retrieve all presets for a pick list by ID.
---

# Retrieve pick list presets

These endpoints allow you to retrieve the values of a pick list(s).

## Get all presets for a pick list by ID

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/pick-list-preset/:listID`

Retrieve list of presets pick list by ID.

#### Path Parameters

| Name                                     | Type | Description       |
| ---------------------------------------- | ---- | ----------------- |
| listID<mark style="color:red;">\*</mark> | guid | The pick list ID. |

#### Headers

| Name                                            | Type   | Description             |
| ----------------------------------------------- | ------ | ----------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | Authorization token.    |
| x-api-key<mark style="color:red;">\*</mark>     | String | Your company's API key. |

{% tabs %}
{% tab title="200: OK Returns all pick list presets." %}
```javascript
[
    {
        "id": "44452549-f014-4c71-b85f-2c49778bfall",
        "name": "My Favorite Values"
    },
    {
        "id": "99908a1b-6f50-4cae-9fe9-b31547c31234",
        "name": "Another Picklist Preset"
    }
]
```
{% endtab %}
{% endtabs %}

## Get preset details by pick list ID and preset ID

<mark style="color:blue;">`GET`</mark>`https://ris.rightsline.com/v4/pick-list-preset/:listID/:presetID`

`Retrieve all details of a preset, including the values it contains.`

### `Path Parameters`

| Name     | Type | Description       |
| -------- | ---- | ----------------- |
| listID   | guid | The pick list ID. |
| presetID | guid | The preset ID.    |

{% tabs %}
{% tab title="200: OK Returns picklist details" %}
```
{
    "id": "44452549-f014-4c71-b85f-2c49778bfall",
    "name": "My Favorite Values",
    "values":
    [
        {
            "id": 44,
            "label": "United States of America",
            "description": "United States of America",
            "xref": "US",
            "status": "Active"
        },
        {
            "id": 55,
            "label": "Canada",
            "xref": "CAN",
            "status": "Active"
        },
    ]
}
```
{% endtab %}
{% endtabs %}
