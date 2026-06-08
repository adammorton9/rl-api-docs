---
description: Retrieve pick lists or a pick list by ID.
---

# Retrieve pick list

These endpoints allow you to retrieve the values of a pick list(s).

## Get all pick lists

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/pick-list`

Retrieve all pick lists.

#### Headers

| Name                                            | Type   | Description             |
| ----------------------------------------------- | ------ | ----------------------- |
| Authorization<mark style="color:red;">\*</mark> | String | Authorization token.    |
| x-api-key<mark style="color:red;">\*</mark>     | String | Your company's API key. |

{% tabs %}
{% tab title="200: OK Returns all pick lists." %}
```javascript
[
    {
        "id": "28352549-f014-4c71-b85f-2c49778bf9ed",
        "name": "Letters"
    },
    {
        "id": "57008a1b-6f50-4cae-9fe9-b31547c31b71",
        "name": "Languages"
    }
]
```
{% endtab %}
{% endtabs %}

## Get pick list by ID

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/pick-list/:listID`

Retrieve a specific pick list by ID.

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
{% tab title="200: OK Return pick list by ID." %}
```javascript
[
    {
        "id": "ed6849bc-ea41-e511-9457-0af1f058195a",
        "name": "Language (Hierarcy)",
        "values": [
            {
                "id": 4,
                "label": "All Languages",
                "description": "All Languages",
                "xref": null,
                "status": "Active",
                "childValues": [
                    {
                        "id": 27,
                        "label": "Dutch",
                        "description": "Dutch",
                        "xref": null,
                        "status": "Active",
                        "childValues": [
                            {
                                "id": 28,
                                "label": "Dutch (Netherlands)",
                                "description": "Dutch (Netherlands)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            }
                        ]
                    },
                    {
                        "id": 29,
                        "label": "English",
                        "description": "English",
                        "xref": null,
                        "status": "Active",
                        "childValues": [
                            {
                                "id": 30,
                                "label": "English (Australian)",
                                "description": "English (Australian)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 31,
                                "label": "English (Scottish)",
                                "description": "English (Scottish)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 32,
                                "label": "English (UK)",
                                "description": "English (UK)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 33,
                                "label": "English (US)",
                                "description": "English (US)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            }
                        ]
                    },
                    {
                        "id": 38,
                        "label": "French",
                        "description": "French",
                        "xref": null,
                        "status": "Active",
                        "childValues": [
                            {
                                "id": 39,
                                "label": "French (Canadian)",
                                "description": "French (Canadian)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 40,
                                "label": "French (Parisian)",
                                "description": "French (Parisian)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            }
                        ]
                    },
                    {
                        "id": 114,
                        "label": "Gaelic",
                        "description": "Gaelic",
                        "xref": null,
                        "status": "Active",
                        "childValues": []
                    },
                    {
                        "id": 91,
                        "label": "Spanish",
                        "description": "Spanish",
                        "xref": null,
                        "status": "Active",
                        "childValues": [
                            {
                                "id": 92,
                                "label": "Spanish (Argentinean)",
                                "description": "Spanish (Argentinean)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 14,
                                "label": "Spanish (Castilian)",
                                "description": "Castilian Spanish",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 93,
                                "label": "Spanish (Chilean)",
                                "description": "Spanish (Chilean)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 94,
                                "label": "Spanish (Cuban)",
                                "description": "Spanish (Cuban)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 63,
                                "label": "Spanish (Latin American)",
                                "description": "Latin American Spanish",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 95,
                                "label": "Spanish (Mexican)",
                                "description": "Spanish (Mexican)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            },
                            {
                                "id": 96,
                                "label": "Spanish (Puerto Rican)",
                                "description": "Spanish (Puerto Rican)",
                                "xref": null,
                                "status": "Active",
                                "childValues": []
                            }
                        ]
                    }
                ]
            }
        ]
    }
]
```
{% endtab %}

{% tab title="404: Not Found List not found." %}
```javascript
{
    "message": "Pick list with list ID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx not found."
}
```
{% endtab %}
{% endtabs %}
