# Characteristics

{% hint style="info" %}
GraphQL can significantly enhance the power of your API Integration. To onboard, please reach out to your Account Manager for pricing information.
{% endhint %}

**Characteristics** is an object field on the Entity root type that defines the characteristics of a given record. Because characteristics can vary based on char type and template, the Characteristics object does not have a predictable set of fields. It is instead a collection of key-value pairs represented by a characteristic's tag label and its value, exactly how it is represented for other REST endpoints.&#x20;

```graphql
{    
    entity (id: 10, charTypeId: 4) {
        characteristics
    }
}
```

The above query would return all characteristic values for a given entity. Each entity object has a characteristics field that can be requested.

```graphql
{    
    entity (id: 10, charTypeId: 4) {
        characteristics
        children (charTypeId: 3) {
            id
            characteristics
        }
    }
}
```

## Filtering

Since **Characteristics** does not have a predictable structure, we are not able to query for specific characteristics the way we normally would through GraphQL. In order to request only specific characteristics for a given entity, you must pass the desired characteristics in a parameter called `tags`:

```graphql
{    
    entity (id: 10, charTypeId: 4) {
        characteristics (tags: ["agreement_date", "term_start"])
    }
}
```

This will return only characteristics with tag labels matching either `agreement_date` or `term_start`. If the characteristic does not exist or does not have a value, it will not be returned.

```json
{
    "data": {
        "entity": {
            "characteristics": {
                "agreement_date": "2023-06-15T16:40:22.060Z",
                "term_start": "2023-07-17T17:32:12.570Z"
            }
        }
    }
}
```

If no tags are passed, all characteristic values will be returned. Characteristics are serialized in the response in the same manner that they are for all other REST endpoints.
