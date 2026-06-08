# Find financial document by parent financial document

If your configuration allows for two accounting documents to be related to each other, the following search would find all child accounting documents given a specific parent (in this case the parent has record ID 999).

Endpoint: /financial-document/search

```javascript
{
  "keywords": "",
  "query": {},
  "start": 0,
  "rows": 10,
  "parentQuery": {
      "7":{
          "$eq":["recordid",999]
      }
  }
}
```
