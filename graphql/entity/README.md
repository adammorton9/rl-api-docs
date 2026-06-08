# Entity

{% hint style="info" %}
GraphQL can significantly enhance the power of your API Integration. To onboard, please reach out to your Account Manager for pricing information.
{% endhint %}

The **Entity** is the root type for querying a Rightsline entity record. It is defined by the following schema:&#x20;

```graphql
{    
    entity (id: int, charTypeId: int) {
        id
        revisionId
        title
        template {
            templateId
            templateName
        }
        status {
            statusId
            statusName
        }
        characteristics (tags: string[]) {
        }
        createdBy
        createdDate
        lastUpdatedBy
        lastUpdatedDate
        statusUpdatedBy
        statusUpdatedDate
        children (charTypeId: int, skip: int, take: int) {
            totalCount
            pageInfo {
                hasNextPage
                hasPreviousPage
            }
            items {
                id
                title
                ...
            }
        }
        parents (charTypeId: int, skip: int, take: int) {
            totalCount
            pageInfo {
                hasNextPage
                hasPreviousPage
            }
            items {
                id
                title
                ...
            }
        },
        parties (partyIds: int[], skip: int, take: int) {
            totalCount
            pageInfo {
                hasNextPage
                hasPreviousPage
            }
            items {
                id
                title
                partyId
                partyName
            }
        }
    }
}
```

When querying for an entity, you must pass the record ID in the `id` parameter and the[ char type ID](../../entities/char-types.md) in the `charTypeId` parameter. You can then include any or all of the above fields in your request depending on the information you need. For instance, if you are only interested in the title and its created date, you can use the following query:

```graphql
{    
    entity (id: 10, charTypeId: 4) {
        title
        createdDate
    }
}
```

This will result in a response like:

```json
{
    "data": {
        "entity": {
            "title": "Deal 10",
            "createdDate": "2023-06-15T16:40:22.060Z"
        }
    }
}
```
