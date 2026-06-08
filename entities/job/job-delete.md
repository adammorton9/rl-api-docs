# Delete a job

## Delete job

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/job/:id`

This endpoint allows you to delete a job.

#### Path Parameters

| Name | Type    | Description              |
| ---- | ------- | ------------------------ |
| id   | integer | ID of the job to delete. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Job successfully deleted." %}
```
true
```
{% endtab %}
{% endtabs %}

