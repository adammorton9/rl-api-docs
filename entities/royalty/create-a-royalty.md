# Create a royalty

## Create royalty

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/royalty`

This endpoint allows you to create a new royalty record. For a complete guide on setting up royalties with splits, deal associations, and contact assignments, see [Financial > Create a royalty](../../financial/create-a-royalty/).

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                             |
| ------------------- | ------ | ------------------------------------------------------- |
| title               | string | The title of the new royalty.                           |
| template            | object | The template of the new royalty.                        |
| template.templateId | string | The unique ID of the template to assign to the royalty. |
| characteristics     | object | The field values to assign to the royalty.              |
| parentRelationship  | array  | Create this royalty as a child of other entities.       |

{% tabs %}
{% tab title="200 Royalty created successfully. Returns the ID of the newly created royalty." %}
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
        "royalty_basis": {
            "value": "Gross Receipts"
        }
    }
}
```
