# $join\_child\_rel

The $join\_child\_rel function allows you to search for an entity based on its field values as well as its relationship to a child entity.  This is especially helpful when you want to find all parents of a particular entity that meet certain criteria.

#### Example: Find all deals (char type ID = 4) for catalog-item (record ID = 1234) with an agreement date greater than 08-06-2020.

{% code title="POST: https://ris.rightsline.com/v3/deal/search" %}
```javascript
{  
   "query":{  
      "$join_child_rel":[  
         {  
            "$and":[  
               {  
                  "$eq":[  
                     "childchartypeid",
                     1
                  ]
               },
               {  
                  "$eq":[  
                     "childrecordid",
                     1234
                  ]
               },
               {  
                  "$eq":[  
                     "parentchartypeid",
                     4
                  ]
               },
               {
                  "$gt":[
                     "agreement_date",
                     "2019-08-06"
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

