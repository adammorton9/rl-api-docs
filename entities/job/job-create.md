# Create a job

## Create job

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/job`

This endpoint allows you to create a job.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type    | Description                                |
| ------------------- | ------- | ------------------------------------------ |
| title               | string  | The title of the new job.                  |
| template            | object  | The template to assign to the new job.     |
| template.templateId | integer | The template ID to assign to the new job.  |
| characteristics     | object  | The field values to assign to the new job. |
| parentRelationship  | array   | The parent entities of the new job.        |

{% tabs %}
{% tab title="200 Job successfully created.  Returns the ID of the newly created record." %}
```
6136
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

