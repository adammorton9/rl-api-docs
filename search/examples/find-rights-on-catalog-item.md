# Find rights on catalog item

{% code title="POST - https://ris.rightsline.com/v4/right/search" %}
```json
{
  "query": {},
  "start": 0,
  "rows": 100,
  "parentQuery": {
      "1":{
          "$eq":["recordid", 9999]
      }
  }
}
```
{% endcode %}
