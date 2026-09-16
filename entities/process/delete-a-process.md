# Delete a process

## Delete process

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/process/:id`

This endpoint allows you to delete a process.

#### Path Parameters

| Name | Type    | Description                  |
| ---- | ------- | ---------------------------- |
| id   | integer | ID of the process to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Process successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}
