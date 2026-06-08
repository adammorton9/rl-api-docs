# Delete a file

## Delete file

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/file/:id`

This endpoint allows you to delete a file.

#### Path Parameters

| Name | Type    | Description               |
| ---- | ------- | ------------------------- |
| id   | integer | ID of the file to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 File successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

