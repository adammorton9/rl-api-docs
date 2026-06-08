# $join

The $join function allows you to join two or more search queries together.

A $join function has 4 parts:

1. The char type ID of the object.
2. The field to extract from the object.&#x20;
3. The field to transpose the extracted field into.
4. The object (either record or relationship)

```json
{
    "$join":[
        0,  // char type ID of object
        "relrecid", // extracted field
        "parentrecordid", // transposed field
        {
            "$and":[
                {"$eq": ["parentchartypeid", 4]},
                {"$eq": ["parentrecordid", 1234]},
                {"$eq": ["childchartypeid", 3]},
                {"$eq": ["childrecordid", 111]}
            ]
        } // object (record/relationship)
    ]
}
```

The $join query can be added to any other Multi-query functions (such as `$and` or `$or)` where you can now use the transposed field in that query.

In the following example, in the innermost join (line 12), the `0` indicates the object is a relationship. The `relrecid` is the field you want to extract from the object, and the `parentrecordid` is the field you want that previous field to represent in any parent query. So the logic would be, get the following relationship’s (0) relrecid as the parentrecordid.

Similarly with the outermost join (line 3), get the following relationship’s (`0`) `childrecordid` as the `recordid`. Since all of those relationship’s child records are catalog items (denoted by the line `{"$eq": ["childchartypeid", 1]}`), and you are doing a catalog-item search, you will be returned a list of catalog item records.

#### Example: Get catalog items on a right (record ID = 111) on a deal (record ID = 1234)

{% code title="POST: https://ris.rightsline.com/v3/catalog-item/search" %}
```javascript
{
   "query":{
    "$join":[
        0,
        "childrecordid",
        "recordid",
        {
            "$and":[
                {"$eq": ["parentchartypeid", 0]},
                {"$eq": ["childchartypeid", 1]},
                {
                    "$join":[
                        0,
                        "relrecid",
                        "parentrecordid",
                        {
                            "$and":[
                                {"$eq": ["parentchartypeid", 4]},
                                {"$eq": ["parentrecordid", 1234]},
                                {"$eq": ["childchartypeid", 3]},
                                {"$eq": ["childrecordid", 111]}
                            ]
                        }
                    ]
                }
            ]
        }
    ]
   },
   "start":0,
   "rows":25
}
```
{% endcode %}
