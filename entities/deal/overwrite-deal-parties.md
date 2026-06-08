# Overwrite deal parties

## Overwrite deal parties

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/deal/:id/overwrite-parties`

This endpoint allows you to overwrite parties for a specific deal by ID.

#### Path Parameters

| Name                                 | Type   | Description     |
| ------------------------------------ | ------ | --------------- |
| id<mark style="color:red;">\*</mark> | number | ID of the deal. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name            | Type   | Description                                                                        |
| --------------- | ------ | ---------------------------------------------------------------------------------- |
| selectedParties | int\[] | Array of Party IDs to overwrite. If not included, all parties will be overwritten. |

{% tabs %}
{% tab title="200: OK Parties overwritten successfully." %}
```json
{
    "message": "Overwrite contacts successful."
}
```
{% endtab %}

{% tab title="404: Not Found Could not find a deal with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}

{% tab title="404: Not Found Selected parties not found on deal." %}
```json

{
    "message": "Party ID(s) [2, 3] not found on entity."
}
```
{% endtab %}

{% tab title="404: Not Found No parties exist on deal." %}
```json
{
    "message": "No parties found on entity."
}
```
{% endtab %}

{% tab title="404: Not Found Selected parties do not exist." %}
```json
{
    "message": "Party ID(s) [20, 24] do not exist."
}
```
{% endtab %}
{% endtabs %}
