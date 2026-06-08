---
description: Switches the right record to a new template
---

# Switch table template

## Switch table template

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/table/:id/switch-template`

This endpoint allows you to change the template of an table.

#### Path Parameters

| Name                                 | Type   | Description                                |
| ------------------------------------ | ------ | ------------------------------------------ |
| id<mark style="color:red;">\*</mark> | string | ID of the table to switch the template of. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                                  | Type   | Description                                |
| ----------------------------------------------------- | ------ | ------------------------------------------ |
| id<mark style="color:red;">\*</mark>                  | string | ID of the table to switch the template of. |
| newTemplateId<mark style="color:red;">\*</mark>       | string | The ID of the new template.                |
| title<mark style="color:red;">\*</mark>               | string | Title of the record.                       |
| template.templateId<mark style="color:red;">\*</mark> | string | The current template ID.                   |

{% tabs %}
{% tab title="200 Template switched. Returns template switch object." %}
```json
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

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/table/:id/switch-template-check`

This endpoint allows you to check what will happen to a record before switching the template.

#### Path Parameters

| Name | Type   | Description                                |
| ---- | ------ | ------------------------------------------ |
| id   | string | ID of the table to switch the template of. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                                  | Type   | Description                                |
| ----------------------------------------------------- | ------ | ------------------------------------------ |
| id<mark style="color:red;">\*</mark>                  | string | ID of the table to switch the template of. |
| newTemplateId<mark style="color:red;">\*</mark>       | string | The ID of the new template.                |
| title<mark style="color:red;">\*</mark>               | string | Title of the record.                       |
| template.templateId<mark style="color:red;">\*</mark> | string | The current template ID.                   |

{% tabs %}
{% tab title="200 Returns template check object." %}
```json
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
