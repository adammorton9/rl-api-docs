# Retrieve catalog item template list

## Get catalog item templates

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/catalog-item-templates`

This endpoint allows you to retrieve template data for catalog items.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Templates successfully retrieved." %}
```javascript
{
  "templates": [
    {
      "templateId": 14,
      "templateName": "Collection",
      "processId": 4,
      "processName": "Catalog Workflow"
    },
    {
      "templateId": 1,
      "templateName": "Feature",
      "processId": 4,
      "processName": "Catalog Workflow"
    }
  ]
}
```
{% endtab %}
{% endtabs %}
