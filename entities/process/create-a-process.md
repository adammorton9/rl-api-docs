# Create a process

## Create process

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/process`

This endpoint allows you to create a new process.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                             |
| ------------------- | ------ | ------------------------------------------------------- |
| title               | string | The title of the new process.                           |
| template            | object | The template of the new process.                        |
| template.templateId | string | The unique ID of the template to assign to the process. |
| characteristics     | object | The field values to assign to the process.              |
| parentRelationship  | array  | Create this process as a child of other entities.       |

{% tabs %}
{% tab title="200 Process created successfully. Returns the ID of the newly created process." %}
```
302
```
{% endtab %}

{% tab title="400 Request is missing required information." %}
```json
{
  "message": "TemplateId is required"
}
```
{% endtab %}
{% endtabs %}

### Sample Request

```json
{
    "title": "My New Process",
    "template": {
        "templateId": 1
    },
    "characteristics": {
        "notes": "Process record notes"
    },
    "parentRelationship": [
        {
            "parentCharTypeId": 4,
            "parentRecordId": 100
        }
    ]
}
```
