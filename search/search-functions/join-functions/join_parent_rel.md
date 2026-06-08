# $join\_parent\_rel

The $join\_parent\_rel function allows you to search for an entity based on its field values as well as its relationship to a parent entity.  This is especially helpful when you want to find all children of a particular entity that meet certain criteria.

#### Example: Find all contacts (char type ID = 2) on a Deal record (record ID = 1234) with a Party ID = 15&#x20;

{% code title="POST: https://ris.rightsline.com/v3/contact/search" %}
```javascript
{  
   "query":{  
      "$join_parent_rel":[  
         {  
            "$and":[  
               {  
                  "$eq":[  
                     "parentchartypeid",
                     4
                  ]
               },
               {  
                  "$eq":[  
                     "parentrecordid",
                     1234
                  ]
               },
               {  
                  "$eq":[  
                     "childchartypeid",
                     2
                  ]
               },
               {
                  "$eq":[
                     "relind",
                     15
                     ]
               }
            ]
         }
      ]
   },
   "start":0,
   "rows":25,
   "sortOrders":[  
      "title_sort asc"
   ]
}
```
{% endcode %}

