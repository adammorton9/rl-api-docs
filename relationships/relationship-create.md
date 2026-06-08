---
description: >-
  A relationship between two entities can be created by populating the
  parentRelationship array when creating an entity, or by using the create
  relationship endpoint.
---

# Create a relationship

## Create relationship

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/relationship`

This endpoint allows you to create a new relationship between entities.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                               | Type   | Description                                                         |
| -------------------------------------------------- | ------ | ------------------------------------------------------------------- |
| parentRecordId<mark style="color:red;">\*</mark>   | number | The ID of the parent record.                                        |
| parentCharTypeId<mark style="color:red;">\*</mark> | number | The [char type ID](../entities/char-types.md) of the parent record. |
| childRecordId<mark style="color:red;">\*</mark>    | number | The ID of the child record.                                         |
| childCharTypeId<mark style="color:red;">\*</mark>  | number | The [char type ID](../entities/char-types.md) of the child record.  |

{% tabs %}
{% tab title="200 Relationship created successfully." %}
```
5545562  // relationship ID
```
{% endtab %}

{% tab title="400 Invalid relationship " %}
```json
{
    "message": "Invalid Relationship"
}
```
{% endtab %}

{% tab title="404 Parent or Child Record does not exist /missing parent or child record parameters" %}
```json
{
    "message": "Parent deal 104689890 does not exist". //or 'Child deal'
}
```
{% endtab %}

{% tab title="403 User doesn’t have adequate permissions" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "message": "Acls don't provide create relationship rights for 4/2."
}
</code></pre>
{% endtab %}
{% endtabs %}

### Examples

#### 1. Create catalog to rights relationship

{% code title="POST /v4/relationship" %}
```javascript
{
    "parentRecordId": 100,
    "parentCharTypeId": 1,
    "childRecordId": 23,
    "childCharTypeId": 3
}
```
{% endcode %}

#### 2. Create catalog to catalog relationship

{% code title="POST /v4/relationship" %}
```json
{
    "parentRecordId": 100,
    "parentCharTypeId": 1,
    "childRecordId": 1245,
    "childCharTypeId": 1
}
```
{% endcode %}
