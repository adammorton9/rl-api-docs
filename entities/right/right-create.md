# Create a right

## Create right

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/right`

This endpoint allows you to create a new right.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                             |
| ------------------- | ------ | ------------------------------------------------------- |
| title               | string | The title of the new right.                             |
| template            | object | The template of the new right.                          |
| template.templateId | string | The unique ID of the template to assign to the right.   |
| characteristics     | object | The field values to assign to the right.                |
| parentRelationship  | array  | Create this right as a child of a deal or catalog item. |

{% tabs %}
{% tab title="200 Right successfully created. Returns the ID of the newly created right." %}
```
2200
```
{% endtab %}

{% tab title="400 Request is missing information, or the information is invalid." %}
```javascript
{
  "message": "TemplateId is required"
}
```
{% endtab %}
{% endtabs %}
