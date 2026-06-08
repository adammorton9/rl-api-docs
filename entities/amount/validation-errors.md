# Retrieve amount validation errors

## Get amount validation errors

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/amount/:id/validation-errors`

This endpoint allows you to retrieve validation errors for a specific amount by ID.

#### Path Parameters

| Name                                 | Type   | Description                                     |
| ------------------------------------ | ------ | ----------------------------------------------- |
| id<mark style="color:red;">\*</mark> | string | ID of the amount to retrieve validation errors. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK Validation errors exist." %}
```javascript
{
  "hasErrors": true,
  "errors": [
    {
      "message": "End Date (term_end_date) is required",
      "type": "Data & Associations",
      "workflowBlocking": true
    }
  ],
  "message": "Workflow blocking errors are present. Workflow Actions are disabled until these validation errors are resolved."
}
```
{% endtab %}

{% tab title="404: Not Found Could not find an amount with this ID." %}
```javascript
{
  "message": "Resource Not Found"
}
```
{% endtab %}

{% tab title="200: OK No validation errors exist." %}
```javascript
{
  "hasErrors": false,
  "errors": [],
  "message": "No validation errors exist."
}
```
{% endtab %}
{% endtabs %}
