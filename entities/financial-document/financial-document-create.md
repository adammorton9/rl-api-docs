# Create a financial document

## Create financial document

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/financial-document`

This endpoint allows you to create a new financial document.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                        |
| ------------------- | ------ | ------------------------------------------------------------------ |
| title               | string | The title of the new financial document.                           |
| template            | object | The template of the new financial document.                        |
| template.templateId | string | The unique ID of the template to assign to the financial document. |
| characteristics     | object | The field values to assign to the financial document.              |
| parentRelationship  | array  | Create this financial document as a child of other entities.       |

{% tabs %}
{% tab title="200 Financial document created successfully.  Returns the ID of the newly created record." %}
```
302
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

###
