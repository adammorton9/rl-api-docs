# Create an amount

## Create amount

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/amount`

This endpoint allows you to create a new amount.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                            |
| ------------------- | ------ | ------------------------------------------------------ |
| title               | string | The title of the new amount.                           |
| template            | object | The template of the new amount.                        |
| template.templateId | string | The unique ID of the template to assign to the amount. |
| characteristics     | object | The field values to assign to the amount.              |
| parentRelationship  | array  | Create this amount as a child of another entity.       |

{% tabs %}
{% tab title="200 Amount created successfully.  Returns the ID of the new entity." %}
```
123456
```
{% endtab %}

{% tab title="400 Request is missing required information, or the information is invalid." %}
```javascript
{
  "message": "TemplateId is required"
}
```
{% endtab %}
{% endtabs %}
