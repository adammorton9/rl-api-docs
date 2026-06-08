# Relationship types

Every relationship in Rightsline has a distinct type, indicated by a Relationship Type Name and Relationship Type ID.

```json
"relationshipType": {
    "relationshipTypeId": 0,
    "relationshipTypeName": "string"
}
```

The two main relationship types are:

| Relationship Type ID | Relationship Type Name |
| -------------------- | ---------------------- |
| 0                    | Explicit               |
| 1                    | Implicit               |

Explicit relationships describe two records that are directly related. Implicit relationships are relationships that are implied based on the records sharing some common ancestry in their hierarchy.

A special type of relationship type is that of a party relationship. A contact that is related to another record as a party will have a relationship type ID and name equal to the party ID and name.&#x20;

To retrieve the relationship types that are configured in Rightsline, you can use the following endpoint:

## Get relationship types

<mark style="color:blue;">`GET`</mark> `https://api.rightsline.com/v4/relationship-types`

This endpoint allows you to retrieve the possible entity relationship types.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Relationship types successfully retrieved." %}
```javascript
{
  "relationshipTypes": [
    {
      "relationshipTypeId": 0,
      "relationshipTypeName": "Default"
    },
    {
      "relationshipTypeId": 14,
      "relationshipTypeName": "Department"
    },
    {
      "relationshipTypeId": 3,
      "relationshipTypeName": "Responsible Party"
    },
    {
      "relationshipTypeId": 24,
      "relationshipTypeName": "Watcher"
    },
    {
      "relationshipTypeId": 2,
      "relationshipTypeName": "Contracting Party"
    },
    {
      "relationshipTypeId": 1,
      "relationshipTypeName": "Counterparty"
    },
    {
      "relationshipTypeId": 15,
      "relationshipTypeName": "Representative"
    },
    {
      "relationshipTypeId": 17,
      "relationshipTypeName": "As Relates To"
    },
    {
      "relationshipTypeId": 23,
      "relationshipTypeName": "Sales Rep"
    },
    {
      "relationshipTypeId": 6,
      "relationshipTypeName": "Submitted By"
    },
    {
      "relationshipTypeId": 30,
      "relationshipTypeName": "Submitted To"
    },
    {
      "relationshipTypeId": 12,
      "relationshipTypeName": "Reviewer"
    },
    {
      "relationshipTypeId": 29,
      "relationshipTypeName": "Coverage By"
    },
    {
      "relationshipTypeId": 5,
      "relationshipTypeName": "Recipient"
    },
    {
      "relationshipTypeId": 13,
      "relationshipTypeName": "Financier"
    },
    {
      "relationshipTypeId": 20,
      "relationshipTypeName": "Executive Producer"
    },
    {
      "relationshipTypeId": 11,
      "relationshipTypeName": "Producer"
    },
    {
      "relationshipTypeId": 10,
      "relationshipTypeName": "Actor"
    },
    {
      "relationshipTypeId": 8,
      "relationshipTypeName": "Writer"
    },
    {
      "relationshipTypeId": 9,
      "relationshipTypeName": "Director"
    },
    {
      "relationshipTypeId": 26,
      "relationshipTypeName": "Director of Photography"
    },
    {
      "relationshipTypeId": 25,
      "relationshipTypeName": "Editor"
    },
    {
      "relationshipTypeId": 27,
      "relationshipTypeName": "Music Supervisor"
    },
    {
      "relationshipTypeId": 28,
      "relationshipTypeName": "Crew"
    },
    {
      "relationshipTypeId": 16,
      "relationshipTypeName": "Delivery"
    },
    {
      "relationshipTypeId": 21,
      "relationshipTypeName": "Location"
    },
    {
      "relationshipTypeId": 4,
      "relationshipTypeName": "Payment"
    },
    {
      "relationshipTypeId": 22,
      "relationshipTypeName": "MISC/OTHER"
    },
    {
      "relationshipTypeId": 31,
      "relationshipTypeName": "Legal"
    },
    {
      "relationshipTypeId": 32,
      "relationshipTypeName": "Marketing"
    },
    {
      "relationshipTypeId": 33,
      "relationshipTypeName": "Seller"
    },
    {
      "relationshipTypeId": 34,
      "relationshipTypeName": "Buyer"
    },
    {
      "relationshipTypeId": 35,
      "relationshipTypeName": "Viewers v2"
    },
    {
      "relationshipTypeId": 39,
      "relationshipTypeName": "Production Company"
    },
    {
      "relationshipTypeId": 40,
      "relationshipTypeName": "Executive"
    },
    {
      "relationshipTypeId": 41,
      "relationshipTypeName": "Creator"
    },
    {
      "relationshipTypeId": 42,
      "relationshipTypeName": "Host"
    },
    {
      "relationshipTypeId": 43,
      "relationshipTypeName": "Talent"
    }
  ]
}
```
{% endtab %}
{% endtabs %}
