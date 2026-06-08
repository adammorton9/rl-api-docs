# Delete a project

## Delete project

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/project/:id`

This endpoint allows you to delete a project.

#### Path Parameters

| Name | Type    | Description                  |
| ---- | ------- | ---------------------------- |
| id   | integer | ID of the project to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Project item successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

