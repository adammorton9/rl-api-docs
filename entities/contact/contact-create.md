# Create a contact

## Create contact

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/contact`

This endpoint allows you to create a new contact.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                             |
| ------------------- | ------ | ------------------------------------------------------- |
| title               | string | The title of the new contact.                           |
| template            | object | The template of the new contact.                        |
| template.templateId | string | The unique ID of the template to assign to the contact. |
| characteristics     | object | The field values to assign to the contact.              |
| parentRelationship  | array  | Create this contact as a child of other entities.       |

{% tabs %}
{% tab title="200 Contact created successfully.  Returns the ID of the newly created contact." %}
```
100
```
{% endtab %}

{% tab title="400 Request is missing required information, or the information is invalid." %}
```
{
  "message": "TemplateId is required"
}
```
{% endtab %}
{% endtabs %}
