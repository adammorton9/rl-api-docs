# Create a royalty set

## Create royalty set

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/royalty`

This endpoint allows you to create a new royalty set.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                                 |
| ------------------- | ------ | ----------------------------------------------------------- |
| title               | string | The title of the new royalty set.                           |
| template            | object | The template of the new royalty set.                        |
| template.templateId | string | The unique ID of the template to assign to the royalty set. |
| characteristics     | object | The field values to assign to the royalty set.              |

{% tabs %}
{% tab title="200 Royalty set created successfully.  Returns the ID of the newly created royalty set." %}
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
    "title": "sample royalty set",
    "template": {
        "templateId": 1
    },
    "characteristics": {
        "royalty_income_group": [
            {
                "id": "2"
            }
        ],
        "territory": [
            {
                "id": "1"
            }
        ],
        "term_start": "2020-01-01",
        "term_end": "2020-12-31",
        "cross_collateralize": {
            "value": "Yes"
        },
        "cross_collateralization_note": "always cross collateralize this one",
        "royalty_basis": {
            "value": "Gross Receipts"
        }
    }
}
```
