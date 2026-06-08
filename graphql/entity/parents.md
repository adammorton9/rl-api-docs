# Parents

{% hint style="info" %}
GraphQL can significantly enhance the power of your API Integration. To onboard, please reach out to your Account Manager for pricing information.
{% endhint %}

**Parents** is a field on the [Entity](./) root type that represents the entity's associated parent records.  Parents is an array of type **Entity,** and is specified by passing a char type ID parameter.

```graphql
{
    entity(id: 10, charTypeId: 3) {
       parents(charTypeId: 4) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       }   
    }
}
```

The Parents field is especially powerful because it allows you to traverse a record's hierarchy. You can include multiple Parents fields for each entity to represent different char types, and each Parent Entity can have its own Parents field. Chaining together the Parents fields allows you to traverse an entire record's hierarchy in a single request.

In the example below, we are retrieving a Rights record, it's parent Catalog records, and those Catalog's parent Deal records.

```graphql
{
    entity(id: 10, charTypeId: 3) {
       parents(charTypeId: 1) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
                 parents(charTypeId: 4) {
                      items {
                           id
                           title
                           template {
                                templateId
                           }
                      }
                 }
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
            "parents": {
                "items": [
                    {
                        "id": 100,
                        "title": "Catalog 1",
                        "template": {
                            "templateId": 1
                        }
                        "parents": {
                            "items": [
                                {
                                    "id": 400,
                                    "title": "Deal 1",
                                    "template": {
                                        "templateId": 1
                                    }
                                },
                                {
                                    "id": 401,
                                    "title": "Deal2",
                                    "template": {
                                        "templateId": 2
                                    }
                                }
                            ]
                        }
                    },
                    {
                        "id": 101,
                        "title": "Catalog 2",
                        "template": {
                            "templateId": 2
                        }
                        "parents": {
                            "items": []
                        }
                    }
                ]
            }
        }
    }
}
```

## Aliasing

When using multiple Parents fields for different char types, it is necessary to keep track of what a certain Parents field represents by using an **Alias**. Adding an alias to a field will rename the response Parents field with the desired alias name.&#x20;

In the below example, `catalog` is added as an alias for parent records with char type ID = 1 and `deals` is added an alias for parent records with a char type ID = 4.

```graphql
{
    entity(id: 10, charTypeId: 3) {
       catalog: parents(charTypeId: 1) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       } 
       deals: parents(charTypeId: 4) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       }    
    }
}
```

Response:

<pre class="language-graphql"><code class="lang-graphql">{
    "data": {
        "entity": {
            "id": 10,
            "title": "Right 1",
            "template": {
                "templateId": 1
            },
            <a data-footnote-ref href="#user-content-fn-1">"catalog"</a>: {
                "items": [
                    {
                        "id": 100,
<strong>                        "template": {
</strong>                            "templateId": 1
                        },
                        "title": "Catalog 1"
                    },
                    {
                        "id": 101,
                        "template": {
                            "templateId": 2
                        },
                        "title": "Catalog 2"
                    }
                ]
            },
            <a data-footnote-ref href="#user-content-fn-2">"deals"</a>: {
                "items": [
                    {
                        "id": 200,
                        "template": {
                            "templateId": 1
                        },
                        "title": "Deal 1"
                    },
                    {
                        "id": 201,
                        "template": {
                            "templateId": 2
                        },
                        "title": "Deal 2"
                    }
                ]
            }
        }
    }
}
</code></pre>

## Paging

To limit response sizes, the Parents field utilizes paging. To page through the children records, use the `skip` and `take` parameters:

<pre class="language-graphql"><code class="lang-graphql">{
    entity(id: 10, charTypeId: 3) {
       deals: parents(charTypeId: 4, <a data-footnote-ref href="#user-content-fn-3">skip</a>: 10, <a data-footnote-ref href="#user-content-fn-4">take</a>: 10) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       }  
    }
}
</code></pre>

{% hint style="info" %}
The default page size is **50**.
{% endhint %}

There are also additional fields in the request that help to identify the total number of Parents records (`totalCount`), if a previous page exists (`hasPreviousPage`), and if a next page exists (`hasNextPage`).  `hasPreviousPage` and `hasNextPage` are nested in a `pageInfo` object on the Parents object:

<pre class="language-graphql"><code class="lang-graphql">{
    entity(id: 10, charTypeId: 3) {
       deals: parents(charTypeId: 4, skip: 10, take: 2) {
            <a data-footnote-ref href="#user-content-fn-5">totalCount</a>
            pageInfo {
                 hasPreviousPage
                 hasNextPage
            }
            items {
                 id
                 title
                 template {
                      templateId
                 }
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
            "title": "Right 1",
            "template": {
                "templateId": 1
            },
            "deals": {
                "totalCount": 24,
                "pageInfo": {
                    "hasPreviousPage": true,
                    "hasNextPage": true
                },
                "items": [
                    {
                        "id": 100,
                        "template": {
                            "templateId": 1
                        },
                        "title": "Deal 1"
                    },
                    {
                        "id": 101,
                        "template": {
                            "templateId": 2
                        },
                        "title": "Deal 2"
                    }
                ]
            }
        }
    }
}
```

Using these fields and parameters, you can page through the Parents in subsequent requests, using logic similar to:

> if (pageInfo.hasNextPage)&#x20;
>
> skip = skip + take

## Filtering

Parents can be filtered by using a special parameter object called `where`.

```graphql
{
    entity(id: 10, charTypeId: 1) {
       parents(charTypeId: 4, where: {templateId: {eq: 1}}) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       }  
    }
}
```

All of the following Entity fields can be filtered on in the Parents collection:

* `title`
* `templateId`
* `statusId`
* `createdBy`
* `createdDate`
* `lastUpdatedBy`
* `lastUpdatedDate`
* `statusUpdatedBy`
* `statusUpdatedDate`

### String Filtering

String fields (`title`) can be filtered using the following operators:

<table><thead><tr><th width="155">operator</th><th width="134">value type</th><th>description</th><th>usage</th></tr></thead><tbody><tr><td>eq</td><td>String</td><td>exact match</td><td>{title: {eq: "Episode 1"}}</td></tr><tr><td>neq</td><td>String</td><td>doesn't match</td><td>{title: {neq: "Episode 1"}}</td></tr><tr><td>contains</td><td>String</td><td>substring match</td><td>{title: {contains: "Episode"}}</td></tr><tr><td>ncontains</td><td>String</td><td>doesn't contain substring match</td><td>{title: {ncontains: "Episode"}}</td></tr><tr><td>in</td><td>[String]</td><td>exact match one of the following</td><td>{title: {in: ["Episode 1", "Episode 2"]}}</td></tr><tr><td>nin</td><td>[String]</td><td>doesn't match any of the following</td><td>{title: {nin: ["Episode 1", "Episode 2"]}}</td></tr><tr><td>startsWith</td><td>String</td><td>string starts with</td><td>{title: {startsWith: "Episode"}}</td></tr><tr><td>nstartsWith</td><td>String</td><td>string doesn't start with</td><td>{title: {nstartsWith: "Episode"}}</td></tr><tr><td>endsWith</td><td>String</td><td>string ends with</td><td>{title: {endsWith: "Episode"}}</td></tr><tr><td>nendsWith</td><td>String</td><td>string doesn't end with</td><td>{title: {nendsWith: "Episode"}}</td></tr></tbody></table>

### Comparable Filtering

Field types of `bool`, `int`, and `DateTime` such as `templateId`, `statusId`, `createdBy`, `createdDate`, `lastUpdatedBy`, `lastUpdatedDate`, `statusUpdatedBy`, `statusUpdatedDate` can be filtered using the following operators:

<table><thead><tr><th>operator</th><th width="137">value type</th><th>description</th><th>usage</th></tr></thead><tbody><tr><td>eq</td><td>Int, Bool, DateTime</td><td>exact match</td><td>{templateId: {eq: 1}}</td></tr><tr><td>neq</td><td>Int, Bool, DateTime</td><td>doesn't match</td><td>{templateId: {eq: 1}}</td></tr><tr><td>in</td><td>[Int], [Bool], [DateTime]</td><td>matches one of the following</td><td>{templateId: {in: [1,2]}}</td></tr><tr><td>nin</td><td>[Int], [Bool], [DateTime]</td><td>doesn't match any of the following</td><td>{statusId: {nin: [1,2,3]}}</td></tr><tr><td>gt</td><td>Int, Bool, DateTime</td><td>greater than</td><td><p>{createdDate: {gt: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr><tr><td>ngt</td><td>Int, Bool, DateTime</td><td>not greater than</td><td><p>{createdDate: {gt: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr><tr><td>gte</td><td>Int, Bool, DateTime</td><td>greater than or equal</td><td><p>{createdDate: {gte: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr><tr><td>ngte</td><td>Int, Bool, DateTime</td><td>not greater than or equal</td><td><p>{createdDate: {ngte: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr><tr><td>lt</td><td>Int, Bool, DateTime</td><td>less than</td><td><p>{createdDate: {lt: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr><tr><td>nlt</td><td>Int, Bool, DateTime</td><td>not less than</td><td><p>{createdDate: {nlt: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr><tr><td>lte</td><td>Int, Bool, DateTime</td><td>less than or equal</td><td><p>{createdDate: {lte: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr><tr><td>nlte</td><td>Int, Bool, DateTime</td><td>not less than or equal</td><td><p>{createdDate: {nlte: </p><p>"2023-06-27T16:07:08.570Z"}}</p></td></tr></tbody></table>

### and / or Filtering

All of the above operators can be combined using the `and` and `or` operators:

<table><thead><tr><th width="138.33333333333331">operator</th><th width="199">description</th><th>usage</th></tr></thead><tbody><tr><td>and</td><td>all conditions must be true</td><td>{ and: [ {lastUpdatedDate: {gt: "2023-06-27T16:07:08.570Z"}}, {templateId: {in: [1,2]}} ] }</td></tr><tr><td>or</td><td>one condition must be true</td><td>{ or: [ {lastUpdatedDate: {gt: "2023-06-27T16:07:08.570Z"}}, {templateId: {in: [1,2]}} ] }</td></tr></tbody></table>

## Sorting

To sort the records in the response by a specific field, specify an `order` parameter:

```graphql
{
    entity(id: 10, charTypeId: 1) {
       deals: parents(charTypeId: 4, order: [{ lastUpdatedDate: DESC }]) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       }  
    }
}
```

You can sort by the following fields:

* id
* title
* createdBy
* createdDate
* lastUpdatedBy
* lastUpdatedDate
* statusUpdatedBy
* statusUpdatedDate

You can sort each of the fields above either ascending using `ASC` or descending using `DESC`.

You can also sort on a field and then by another field:

```graphql
{
    entity(id: 10, charTypeId: 1) {
       deals: parents(charTypeId: 4, order: [{ lastUpdatedDate: DESC }, { id: ASC }]) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       }  
    }
}
```

[^1]: catalog alias

[^2]: deals alias

[^3]: `skip` parameter specifies how many records to skip before returning results

[^4]: `take` parameter specifies how many records to return

[^5]: returns the total number of parent records for this char type
