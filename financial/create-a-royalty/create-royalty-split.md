# Create royalty split

## Create royalty split

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/table`

This endpoint allows you to create a new royalty split table.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                   |
| ------------------- | ------ | ------------------------------------------------------------- |
| title               | string | The title of the new royalty split.                           |
| template            | object | The template of the new royalty split.                        |
| template.templateId | string | The unique ID of the template to assign to the royalty split. |
| characteristics     | object | The field values to assign to the royalty split.              |

{% tabs %}
{% tab title="200 Royalty split created successfully.  Returns the ID of the newly created royalty split." %}
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
    "title": "royalty split 1: 50% above the line for Licensor",
    "template": {
        "templateId": 6
    },
    "characteristics": {
        "income_group": [
            {
                "id": "2"
            }
        ],
        "table_recoupment_category": {
            "value": "Above the line"
        },
        "split_pct": "50"
    }
}
```
