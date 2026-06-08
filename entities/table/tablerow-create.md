# Create a table row

## Create table row

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/table`

This endpoint allows you to create a new table row.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                               |
| ------------------- | ------ | --------------------------------------------------------- |
| title               | string | The title of the new table row.                           |
| template            | object | The template of the new table row.                        |
| template.templateId | string | The unique ID of the template to assign to the table row. |
| characteristics     | object | The field values to assign to the table row.              |
| parentRelationship  | array  | Create this table as a child of a deal or catalog item.   |

{% tabs %}
{% tab title="200 Table row successfully created.  Returns the ID of the newly created table row." %}
```
450
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
