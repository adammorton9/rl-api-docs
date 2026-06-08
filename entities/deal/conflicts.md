# Retrieve deal conflicts

## Get deal conflicts

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/deal/:id/conflicts`

This endpoint allows you to retrieve conflicts for a specific deal by ID.

#### Path Parameters

| Name                                 | Type   | Description                           |
| ------------------------------------ | ------ | ------------------------------------- |
| id<mark style="color:red;">\*</mark> | string | ID of the deal to retrieve conflicts. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK Conflicts exist." %}
```javascript
{
    "hasConflicts": true,
    "message": "Conflicts exist.",
    "conflicts": [
        {
            "id": "eb751a1c-4491-441d-a7d3-f17b7f7f8a9b",
            "status": "Blocker",
            "conflictType": "NO RIGHTS IN",
            "properties": {
                "Catalog RL Catalog Property ID": 200,
                "Catalog Name": "My Test Catalog",
                "Catalog Template": "Feature",
                "Term Start": "2021-12-01T00:00:00Z",
                "Term End": "2021-12-31T00:00:00Z",
                "Media": "All Media",
                "Territory": "Worldwide",
                "Language": "All Languages",
                "Channel": "Amazon, Apple TV, Google Play",
                "Right ID": 130301,
                "Right Template": "Rights Out",
                "Conflicting Right ID": null,
                "Conflicting Right Template": null,
                "Deal ID": 100,
                "Deal Name": "My Test Deal",
                "Deal Template": "Acquisition Deal",
                "Conflicting Deal ID": null,
                "Conflicting Deal Name": null,
                "Conflicting Deal Template": null,
                "Reason For Change": null,
                "Updated By": 0,
                "Last Updated": "2023-05-31T16:27:44.953Z",
                "Status Updated": null
            }
        }
    ]
}
```
{% endtab %}

{% tab title="404: Not Found Could not find an deal with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}

{% tab title="200: OK No conflicts exist." %}
```javascript
{
    "hasConflicts": false,
    "message": "No conflicts exist.",
    "conflicts": []
}
```
{% endtab %}
{% endtabs %}

## Get deal conflict by ID

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/deal/:id/conflicts/:conflictid`

This endpoint allows you to retrieve a conflict by ID for a specific deal by ID.

#### Path Parameters

| Name                                         | Type   | Description                          |
| -------------------------------------------- | ------ | ------------------------------------ |
| id<mark style="color:red;">\*</mark>         | number | ID of the deal to retrieve conflict. |
| conflictid<mark style="color:red;">\*</mark> | guid   | ID of the conflict.                  |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK Conflict exists." %}
```javascript
{
    "conflictType": "NO RIGHTS IN",
    "id": "eb751a1c-4491-441d-a7d3-f17b7f7f8a9b",
    "properties": {
        "Catalog Name": "My Test Catalog",
        "Catalog RL Catalog Property ID": 200,
        "Catalog Template": "Feature",
        "Channel": "Amazon, Apple TV, Google Play",
        "Conflicting Deal ID": null,
        "Conflicting Deal Name": null,
        "Conflicting Deal Template": null,
        "Conflicting Right ID": null,
        "Conflicting Right Template": null,
        "Deal ID": 100,
        "Deal Name": "My Test Deal",
        "Deal Template": "Acquisition Deal",
        "Language": "All Languages",
        "Last Updated": "2023-05-31T16:27:44.953Z",
        "Media": "All Media",
        "Reason For Change": null,
        "Right ID": 130301,
        "Right Template": "Rights Out",
        "Status Updated": null,
        "Term End": "2021-12-31T00:00:00Z",
        "Term Start": "2021-12-01T00:00:00Z",
        "Territory": "Worldwide",
        "Updated By": 0
    },
    "status": "Blocker"
}
```
{% endtab %}

{% tab title="404: Not Found Could not find an deal with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}

{% tab title="404: Not Found Conflict not found." %}
```javascript
{
    "message": "Conflict not found."
}
```
{% endtab %}
{% endtabs %}
