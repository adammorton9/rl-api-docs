---
description: Execute a workflow action that creates a document.
---

# Execute document workflow action

## Execute document workflow action

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/:entityType/:id/execute-document-workflow-action/:actionID`

This endpoint allows you to execute a workflow action on an entity that creates a document.  For available draft templates for an entity, call the draft-templates endpoint for that entity.

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

#### Request Body

| Name       | Type    | Description                            |
| ---------- | ------- | -------------------------------------- |
| templateId | integer | The template ID of the draft template. |

{% tabs %}
{% tab title="200 Workflow executed successfully. Document ID is returned." %}
```
201
```
{% endtab %}
{% endtabs %}
