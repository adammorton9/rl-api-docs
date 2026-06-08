---
description: This will grant a user or users access to the file in Partner Portal.
---

# Grant Access To File

This endpoint does not require access to partner portal to use but in order to see the modifications you will need access to partner portal.

## Grant access to file

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/file/:id/grant-access-to`

This endpoint allows you to grant a user or users access to a specified file.

#### Path Parameters

| Name | Type   | Description     |
| ---- | ------ | --------------- |
| id   | string | ID of the file. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name       | Type   | Description                                                   |
| ---------- | ------ | ------------------------------------------------------------- |
| contactIds | number | The array of contacts that will be granted access to the file |

{% tabs %}
{% tab title="200 Partner Portal file access has been granted." %}
```javascript
"Successfully granted file access."
```
{% endtab %}

{% tab title="403: Forbidden ACLs don't provide permission to write either contacts or files. " %}
```javascript
{
    "message": "Acls don't provide Write rights for {entityid}"
}
```
{% endtab %}

{% tab title="404: Not Found Either contact or file does not exist" %}
```javascript
{
    "message": "Entity d29c2r12435 not found."
}
```
{% endtab %}
{% endtabs %}
