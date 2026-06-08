# Children

{% hint style="info" %}
GraphQL can significantly enhance the power of your API Integration. To onboard, please reach out to your Account Manager for pricing information.
{% endhint %}

**Children** is a field on the [Entity](./) root type that represents the entity's associated child records.  Children is an array of type **Entity,** and is specified by passing a char type ID parameter.

```graphql
{
    entity(id: 10, charTypeId: 4) {
       children(charTypeId: 3) {
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

The Children field is especially powerful because it allows you to traverse a record's hierarchy. You can include multiple Children fields for each entity to represent different char types, and each Children Entity can have its own Children field. These Children fields can be chained together to traverse an entire records hierarchy.

In the below example, we retrieve a Deal record, it's child Table records, and the Catalog records that are associated to each of those Table records.

```graphql
{
    entity(id: 10, charTypeId: 4) {
        children(charTypeId: 5) {
            items {
                id
                title
                template {
                    templateId
                }
                children(charTypeId: 1) {
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
            "children": {
                "items": [
                    {
                        "id": 500,
                        "title": "Table 1",
                        "template": {
                            "templateId": 1
                        }
                        "children": {
                            "items": [
                                {
                                    "id": 100,
                                    "title": "Catalog 1",
                                    "template": {
                                        "templateId": 1
                                    }
                                },
                                {
                                    "id": 101,
                                    "title": "Catalog 2",
                                    "template": {
                                        "templateId": 2
                                    }
                                }
                            ]
                        }
                    },
                    {
                        "id": 501,
                        "title": "Table 2",
                        "template": {
                            "templateId": 2
                        }
                        "children": {
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

When including multiple Children fields, in order to keep track of what a certain Children field represents, you can add an **Alias**. Adding an alias to a field will rename the response Children field with the desire alias name.&#x20;

In the below example, the alias `rights` has been added to the Children field where char type ID = 3, and the alias `tables` has been added to the Children field where char type ID = 5. You can see in the response that these two fields have been replaced with their respective aliases.

```graphql
{
    entity(id: 10, charTypeId: 4) {
       rights: children(charTypeId: 3) {
            items {
                 id
                 title
                 template {
                      templateId
                 }
            }
       } 
       tables: children(charTypeId: 5) {
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
            "title": "Deal 1",
            "template": {
                "templateId": 1
            },
            <a data-footnote-ref href="#user-content-fn-1">"rights"</a>: {
                "items": [
                    {
                        "id": 100,
                        "template": {
                            "templateId": 1
                        },
                        "title": "Rights 1"
                    },
                    {
                        "id": 101,
                        "template": {
                            "templateId": 2
                        },
                        "title": "Rights 2"
                    }
                ]
            },
            <a data-footnote-ref href="#user-content-fn-2">"tables"</a>: {
                "items": [
                    {
                        "id": 200,
                        "template": {
                            "templateId": 1
                        },
                        "title": "Table 1"
                    },
                    {
                        "id": 201,
                        "template": {
                            "templateId": 2
                        },
                        "title": "Table 2"
                    }
                ]
            }
        }
    }
}
</code></pre>

## Paging

To limit response sizes, the Children field utilizes paging. To page through the children records, use the `skip` and `take` parameters:

<pre class="language-graphql"><code class="lang-graphql">{
    entity(id: 10, charTypeId: 4) {
       rights: children(charTypeId: 3, <a data-footnote-ref href="#user-content-fn-3">skip</a>: 10, <a data-footnote-ref href="#user-content-fn-4">take</a>: 10) {
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

There are also additional fields in the request that help to identify the total number of Children records (`totalCount`), if a previous page exists (`hasPreviousPage`), and if a next page exists (`hasNextPage`).  `hasPreviousPage` and `hasNextPage` are nested in a `pageInfo` object on the Children object:

<pre class="language-graphql"><code class="lang-graphql">{
    entity(id: 10, charTypeId: 4) {
       rights: children(charTypeId: 3, skip: 10, take: 2) {
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
            "title": "Deal 1",
            "template": {
                "templateId": 1
            },
            "rights": {
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
                        "title": "Rights 1"
                    },
                    {
                        "id": 101,
                        "template": {
                            "templateId": 2
                        },
                        "title": "Rights 2"
                    }
                ]
            }
        }
    }
}
```

Using these fields and parameters, you can page through the Children in subsequent requests, using logic similar to:

> if (pageInfo.hasNextPage)&#x20;
>
> skip = skip + take

## Filtering

Children can be filtered by using a special parameter object called `where`:

```graphql
{
    entity(id: 10, charTypeId: 4) {
       rights: children(charTypeId: 3, where: {templateId: {eq: 1}}) {
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

All of the following Entity fields can be filtered on in the Children collection:

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

All of the above operators can be combined using the `and` & `or` operators:

<table><thead><tr><th width="138.33333333333331">operator</th><th width="199">description</th><th>usage</th></tr></thead><tbody><tr><td>and</td><td>all conditions must be true</td><td>{ and: [ {lastUpdatedDate: {gt: "2023-06-27T16:07:08.570Z"}}, {templateId: {in: [1,2]}} ] }</td></tr><tr><td>or</td><td>one condition must be true</td><td>{ or: [ {lastUpdatedDate: {gt: "2023-06-27T16:07:08.570Z"}}, {templateId: {in: [1,2]}} ] }</td></tr></tbody></table>

## Sorting

To sort the records in the response by a specific field, specify an `order` parameter:

```graphql
{
    entity(id: 10, charTypeId: 4) {
       rights: children(charTypeId: 3, order: [{ lastUpdatedDate: DESC }]) {
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
    entity(id: 10, charTypeId: 4) {
       rights: children(charTypeId: 3, order: [{ lastUpdatedDate: DESC }, { id: ASC }]) {
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

[^1]: rights alias

[^2]: tables alias

[^3]: `skip` parameter specifies how many records to skip before returning results

[^4]: `take` parameter specifies how many records to return

[^5]: returns the total number of child records for this char type
