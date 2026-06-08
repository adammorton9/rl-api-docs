# Find catalog items on a deal

{% code title="POST - https://ris.rightsline.com/v4/catalog-item/search" %}
```json
{
  "query": {},
  "start": 0,
  "rows": 100,
  "parentQuery": {
      "4":{
          "$eq":["recordid", 9999]
      }
  }
}
```
{% endcode %}
