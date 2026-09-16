# Delete a schedule

## Delete schedule

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/schedule/:id`

This endpoint allows you to delete a schedule.

#### Path Parameters

| Name | Type    | Description                   |
| ---- | ------- | ----------------------------- |
| id   | integer | ID of the schedule to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Schedule successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}
