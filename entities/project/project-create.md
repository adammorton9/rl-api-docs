# Create a project

## Create project

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/project`

This endpoint allows you to create a project.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type    | Description                                |
| ------------------- | ------- | ------------------------------------------ |
| title               | string  | The title of the new project.              |
| template            | object  | The template to assign the new project.    |
| template.templateId | integer | The template ID to assign the new project. |
| characteristics     | object  | The field values of the new project.       |
| parentRelationship  | array   | The parent entities of the new project.    |

{% tabs %}
{% tab title="200 Project successfully created.  Returns the ID of the newly created record." %}
```
14462
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

