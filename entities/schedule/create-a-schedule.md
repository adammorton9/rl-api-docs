# Create a schedule

## Create schedule

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/schedule`

This endpoint allows you to create a new schedule.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                              |
| ------------------- | ------ | -------------------------------------------------------- |
| title               | string | The title of the new schedule.                           |
| template            | object | The template of the new schedule.                        |
| template.templateId | string | The unique ID of the template to assign to the schedule. |
| characteristics     | object | The field values to assign to the schedule.              |
| parentRelationship  | array  | Create this schedule as a child of other entities.       |

{% tabs %}
{% tab title="200 Schedule created successfully. Returns the ID of the newly created schedule." %}
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
    "title": "My New Schedule",
    "template": {
        "templateId": 1
    },
    "characteristics": {
        "notes": "Schedule record notes"
    },
    "parentRelationship": [
        {
            "parentCharTypeId": 4,
            "parentRecordId": 100
        }
    ]
}
```
