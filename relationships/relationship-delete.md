# Delete a relationship

## Delete relationship

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/relationship/:id`

This endpoint allows you to delete a relationship.

#### Path Parameters

| Name | Type   | Description                       |
| ---- | ------ | --------------------------------- |
| id   | string | ID of the relationship to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your Company's API Key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Relationship successfully deleted." %}
```
true
```
{% endtab %}

{% tab title="404 Relationship not found " %}
```json
{
    "message": "Provided Entity Relationship does not exist."
}
```
{% endtab %}
{% endtabs %}

