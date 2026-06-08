# Retrieve inventory draft templates

## Get inventory draft templates

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/inventory/:id/draft-templates`

This endpoint allows you to get the draft templates for an inventory item.

#### Path Parameters

| Name | Type   | Description          |
| ---- | ------ | -------------------- |
| id   | string | ID of the inventory. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Draft templates successfully retrieved." %}
```javascript
{
    "templates": [
        {
            "templateId": 11,
            "templateName": "Testing Draft",
            "templateDescription": null,
            "fileName": "Testing_Draft.docx"
        },
        {
            "templateId": 9,
            "templateName": "Test Draft Template",
            "templateDescription": null,
            "fileName": "Draft_Template.docx"
        }
        {
            "templateId": 24,
            "templateName": "Sample PDF",
            "templateDescription": null,
            "fileName": "Sample_PDF.pdf"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
