# Override deal conflict

## Override deal conflict

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/deal/:id/conflicts/:conflictid`

This endpoint allows you to override a conflict for a specific deal by ID.

#### Path Parameters

| Name                                         | Type   | Description         |
| -------------------------------------------- | ------ | ------------------- |
| id<mark style="color:red;">\*</mark>         | number | ID of the deal.     |
| conflictid<mark style="color:red;">\*</mark> | guid   | ID of the conflict. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name                                              | Type    | Description                                                         |
| ------------------------------------------------- | ------- | ------------------------------------------------------------------- |
| isBlocker<mark style="color:red;">\*</mark>       | boolean | Sets the conflicts as a Blocker (true) or as a Non-Blocker (false). |
| reasonForChange<mark style="color:red;">\*</mark> | string  | A note attached to the blocking status change.                      |

{% tabs %}
{% tab title="204: No Content Conflict updated." %}

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

{% tab title="400: Bad Request Could not update conflict." %}
```json

{
    "message": "Invalid action on conflict eb751a1c-4491-441d-a7d3-f17b7f7f8a9b."
}
```
{% endtab %}
{% endtabs %}
