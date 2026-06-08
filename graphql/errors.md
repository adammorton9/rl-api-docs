# Errors

{% hint style="info" %}
GraphQL can significantly enhance the power of your API Integration. To onboard, please reach out to your Account Manager for pricing information.
{% endhint %}

A GraphQL error is handled differently than a typical REST error.  GraphQL will always return a status code of **200 - OK**, but if an error occurs, an `errors` array will be returned in the response:

```json
{
    "errors": [
        {
            "message": "Resource Not Found.",
            "locations": [
                {
                    "line": 2,
                    "column": 5
                }
            ],
            "path": [
                "entity"
            ]
        }
    ],
    "data": {
        "entity": null
    }
}
```

In this `errors` array, you will see a collection of error objects. The error object will define a `message` - what the error was that occurred, a `location` - where in the json structure the error occurred, and a `path` - the node in the json where the error occurred.&#x20;

The response will also include any partial `data` that could be retrieved before the error occurred.
