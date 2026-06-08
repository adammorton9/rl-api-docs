---
description: Switches the inventory record to a new template
---

# Switch project template

## Switch project template

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/project/:id/switch-template`

This endpoint allows you to change the template of an project.

#### Path Parameters

| Name                                 | Type   | Description                                  |
| ------------------------------------ | ------ | -------------------------------------------- |
| id<mark style="color:red;">\*</mark> | string | ID of the project to switch the template of. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                                  | Type   | Description                                  |
| ----------------------------------------------------- | ------ | -------------------------------------------- |
| id<mark style="color:red;">\*</mark>                  | string | ID of the project to switch the template of. |
| newTemplateId<mark style="color:red;">\*</mark>       | string | The ID of the new template.                  |
| title                                                 | string | Title of the record.                         |
| template.templateId<mark style="color:red;">\*</mark> | string | The current template ID.                     |

{% tabs %}
{% tab title="200 Template switched. Returns template switch object." %}
```javascript
{
    "id": 1,
    "relationshipsNotMigrated": {
        "parties": [],
        "associations": {}
    },
    "characteristicsNotMigrated": [],
    "characteristicsRequiredOnNewTemplate": []
}
```
{% endtab %}
{% endtabs %}



## Check the new template before switching

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/project/:id/switch-template-check`

This endpoint allows you to check what will happen to a record before switching the template.

#### Path Parameters

| Name | Type   | Description                                  |
| ---- | ------ | -------------------------------------------- |
| id   | string | ID of the project to switch the template of. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                  |
| ------------------- | ------ | -------------------------------------------- |
| id                  | string | ID of the project to switch the template of. |
| newTemplateId       | string | The ID of the new template.                  |
| title               | string | Title of the record.                         |
| template.templateId | string | The current template ID.                     |

{% tabs %}
{% tab title="200 Returns template check object." %}
```javascript
{
   "relationshipsNotMigrated": {
        "parties": [],
        "associations": {}
    },
    "characteristicsNotMigrated": [],
    "characteristicsRequiredOnNewTemplate": []
}
```
{% endtab %}
{% endtabs %}
