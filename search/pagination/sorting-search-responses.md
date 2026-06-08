# Sorting search responses

Objects are sorted by their ID value by default.  You can use the `sortOrders` array in a search request to order the objects in the result set. The below example sorts the results by their last updated date in ascending order (use **desc** for descending)

```javascript
{
  "keywords": "string",
  "query": {},
  "start": 0,
  "rows": 10,
  "cursorToken": "string",
  "sortOrders": [
    "last_updated asc"
  ],
  "parentQuery": {},
  "childQuery": {}
}
```



