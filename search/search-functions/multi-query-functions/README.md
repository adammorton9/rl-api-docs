# Multi-query functions



Multi-query functions allow you to group one or more queries together and evaluate them as a collection based on the function operator.  The available multi-query function operators are:

| [$and](and.md) | Satisfies all conditions.         |
| -------------- | --------------------------------- |
| [$or](or.md)   | Satisfies one or more conditions. |
| [$not](not.md) | Does not satisfy a condition.     |

To use multi-query functions, set one of the operators above as a key in the JSON request body, and set the value to an array of subqueries.  The subqueries will then be evaluated based on the logic above.

These multi-query functions can be nested inside other queries as well.  In this case, the inner-most function is evaluated first, and then evaluated outwards. &#x20;

For instance, in the following contact search query, we would return results where the contact has a template ID equal to 10, and either the title has a value of `test` **or** the email address has a value of `email@gmail.com`.

<pre class="language-json" data-title="POST /v4/contact/search"><code class="lang-json"><strong>{
</strong>    "query": {
        "$and": [
            {
                "$eq": [
                    "templateid",
                    10
                ]
            },
            {
                "$or": [
                    {
                        "$eq": [
                            "email",
                            "email@gmail.com"
                        ]
                    },
                    {
                        "$eq": [
                            "title",
                            "test"
                        ]
                    }
                ]
            }
        ]
    },
    "rows": 100,
    "start": 0
}
</code></pre>
