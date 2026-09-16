# Switch schedule template

## Switch template

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/schedule/:id/switch-template`

Switch a schedule to a different template, migrating compatible data.

#### Path Parameters

| Name | Type    | Description                                    |
| ---- | ------- | ---------------------------------------------- |
| id   | integer | ID of the schedule to switch the template for. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name       | Type    | Description                        |
| ---------- | ------- | ---------------------------------- |
| templateId | integer | The ID of the new target template. |

{% tabs %}
{% tab title="200 Template switched successfully." %}
```json
true
```
{% endtab %}
{% endtabs %}
