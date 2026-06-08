# Create a deal

## Create deal

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/deal`

This endpoint allows you to create a new deal.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                          |
| ------------------- | ------ | ---------------------------------------------------- |
| title               | string | The title of the new deal.                           |
| template            | object | The template of the new deal.                        |
| template.templateId | string | The unique ID of the template to assign to the deal. |
| characteristics     | object | The field values to assign to the deal.              |
| parentRelationship  | array  | Create this deal as a child of other deals.          |

{% tabs %}
{% tab title="200 Deal created successfully.  Returns the ID of the newly created deal." %}
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

### Sample Request

```javascript
{
    "title": "My New Deal",
    "template": {
        "templateId": 1
    },
    "characteristics": {
        "notes": "This is a great new deal!"
    },
    "parentRelationship": [
        {
            "parentCharTypeId": 4,
            "parentRecordId": 100
        }
    ]
}
```

