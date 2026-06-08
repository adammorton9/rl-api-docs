---
description: Workflow actions can be executed on a specific entity of any type.
---

# Execute a workflow action

## Execute workflow action

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/:entityType/:id/execute-workflow-action/:actionID`

This endpoint allows you to execute a workflow action on an entity.

#### Path Parameters

| Name       | Type    | Description                                                                                                       |
| ---------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| entityType | string  | <p>The type of entity to perform the workflow action on. <br>ex: deal, catalog-item, financial-document, etc.</p> |
| id         | integer | ID of the entity to perform the action on.                                                                        |
| actionID   | integer | ID of the action to take.                                                                                         |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Workflow action executed successfully." %}
```
"Workflow Action Executed Successfully"
```
{% endtab %}

{% tab title="500: Internal Server Error Entity validation failed." %}
```json
{
    "message": "Entity Invalid"
}
```
{% endtab %}

{% tab title="404: Not Found Entity not found." %}
```json
{
    "message": "Entity Not Found"
}
```
{% endtab %}

{% tab title="403: Forbidden Action not available from current status." %}
```json
{
    "message": "Action 3 not available to be taken from status 1"
}
```
{% endtab %}
{% endtabs %}

