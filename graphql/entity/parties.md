# Parties

{% hint style="info" %}
GraphQL can significantly enhance the power of your API Integration. To onboard, please reach out to your Account Manager for pricing information.
{% endhint %}

**Parties** is a field on the [Entity](./) root type that represents the entity's associated party records.  Parties is an array of type **Party**, which has the following structure:

```graphql
{
    entity(id: 10, charTypeId: 4) {
       parties {
            items {
                 id
                 title
                 partyId
                 partyName
                 createdBy
                 createdDate
                 lastUpdatedBy
                 lastUpdatedDate
                 contact {
                      id
                      title
                      template {
                           templateId
                           templateName
                      }
                      characteristics
                      createdBy
                      createdDate
                      lastUpdatedBy
                      lastUpdatedDate
                 }
            }
       }   
    }
}
```

Parties can also be filtered by specifying one or more party IDs in an array called `partyIds`:

```graphql
{
    entity(id: 10, charTypeId: 4) {
       parties (partyIds: [1,2]) {
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

Response:

```json
{
    "data": {
        "entity": {
            "parties": {
                "items": [
                    {
                        "id": 200,
                        "title": "Bob Smith",
                        "partyId": 1,
                        "partyName": "Licensor"
                    },
                    {
                        "id": 201,
                        "title": "Jan Smith",
                        "partyId": 2,
                        "partyName": "Licensee"
                    }
                ]
            }
        }
    }
}
```

## Paging

To limit response sizes, the Parties field utilizes paging. To page through the party records, use the `skip` and `take` parameters:

<pre class="language-graphql"><code class="lang-graphql">{
    entity(id: 10, charTypeId: 4) {
       parties(<a data-footnote-ref href="#user-content-fn-1">skip</a>: 10, <a data-footnote-ref href="#user-content-fn-2">take</a>: 10) {
            items {
                 id
                 title
                 partyId
                 partyName
            }
       }  
    }
}
</code></pre>

{% hint style="info" %}
The default page size is **50**.
{% endhint %}

There are also additional fields in the request that help to identify the total number of Parties records (`totalCount`), if a previous page exists (`hasPreviousPage`), and if a next page exists (`hasNextPage`).  `hasPreviousPage` and `hasNextPage` are nested in a `pageInfo` object on the Parties object:

<pre class="language-graphql"><code class="lang-graphql">{
    entity(id: 10, charTypeId: 4) {
       parties(skip: 10, take: 2) {
            <a data-footnote-ref href="#user-content-fn-3">totalCount</a>
            pageInfo {
                 hasPreviousPage
                 hasNextPage
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
</code></pre>

Response:

```json
{
    "data": {
        "entity": {
            "id": 10,
            "title": "Deal 1",
            "template": {
                "templateId": 1
            },
            "parties": {
                "totalCount": 24,
                "pageInfo": {
                    "hasPreviousPage": true,
                    "hasNextPage": true
                },
                "items": [
                     {
                        "id": 200,
                        "title": "Bob Smith",
                        "partyId": 1,
                        "partyName": "Licensor"
                    },
                    {
                        "id": 201,
                        "title": "Jan Smith",
                        "partyId": 2,
                        "partyName": "Licensee"
                    }
                ]
            }
        }
    }
}
```

Using these fields and parameters, you can page through the Parties in subsequent requests, using logic similar to:

> if (pageInfo.hasNextPage)&#x20;
>
> skip = skip + take

[^1]: `skip` parameter specifies how many records to skip before returning results

[^2]: `take` parameter specifies how many records to return

[^3]: returns the total number of child records for this char type
