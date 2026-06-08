---
description: Execute a workflow action that requires an E-Signature.
---

# Execute a workflow action with signature

## Execute workflow action

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/:entityType/:id/execute-signature-workflow-action/:actionID`

This endpoint allows you to execute a workflow action on an entity and sends a document for E-Signature.

#### Path Parameters

| Name                                         | Type    | Description                                                                                                       |
| -------------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| entityType<mark style="color:red;">\*</mark> | string  | <p>The type of entity to perform the workflow action on. <br>ex: deal, catalog-item, financial-document, etc.</p> |
| id<mark style="color:red;">\*</mark>         | integer | ID of the entity to perform the action on.                                                                        |
| actionID<mark style="color:red;">\*</mark>   | integer | ID of the action to take.                                                                                         |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name                                         | Type                                                           | Description                                                                                                                                                                        |
| -------------------------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| documentId<mark style="color:red;">\*</mark> | integer                                                        | The record ID of the document to send for E-Signature.  Must be related to parent entity.                                                                                          |
| emails<mark style="color:red;">\*</mark>     | string\[]                                                      | An array of email addresses from whom you require signatures.  . Either `emails` or `recipients` is required.                                                                      |
| recipients<mark style="color:red;">\*</mark> | [Recipient](workflow-execute-signature.md#recipient-object)\[] | An array of Recipients. Either `emails` or `recipients` is required.                                                                                                               |
| cc<mark style="color:red;">\*</mark>         | string\[]                                                      | An array of email addresses that will get a copy of the signed document.                                                                                                           |
| enforceSignOrder                             | boolean                                                        | <p>If true - Signatories must sign in the order they are listed in the request.</p><p>If false (or not included in request) - Document sent to all signatories simultaneously.</p> |
| expireAfterDays                              | integer                                                        | Expire the signature document if it is not signed after a number of days.  (1-999)                                                                                                 |
| warnBeforeExpireDays                         | integer                                                        | If expireAfterDays is set, send reminder email a number of days before document expiration. (must be less than expireAfterDays)                                                    |

### Recipient object

| Name  | Type   | Description                                                                                                                                                                                                                          |
| ----- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| email | string | An email address.                                                                                                                                                                                                                    |
| role  | string | <ul><li><code>AGENT</code> - This recipient will receive the document and can either specify a signer in their place or sign the document themselves.</li><li><code>SIGNER</code> - This recipient must sign the document.</li></ul> |

### Workflow action with signature using emails

```json
{
    "documentId": 2842,
    "emails": [
        "signer1@email.com",
        "signer2@email.com"
    ],
    "cc": [
        "cc1@email.com",
        "cc2@email.com"
    ],
    "enforceSignOrder": true,
    "expireAfterDays": 7,
    "warnBeforeExpireDays": 2
}
```

### Workflow action with signature using recipients

```json
{
    "documentId": 2842,
    "recipients": [
        {
            "email": "agent1@email.com",
            "role": "AGENT"
        },
         {
            "email": "signer1@email.com",
            "role": "SIGNER"
        }
    ],
    "cc": [
        "cc1@email.com",
        "cc2@email.com"
    ],
    "enforceSignOrder": true,
    "expireAfterDays": 7,
    "warnBeforeExpireDays": 2
}
```

{% tabs %}
{% tab title="200 Workflow action executed successfully." %}
```
true
```
{% endtab %}
{% endtabs %}
