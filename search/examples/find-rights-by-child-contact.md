# Find rights by child contact

{% code title="POST - https://ris.rightsline.com/v4/right/search" %}
```json
{
    "query": {
        "$and": [
            {
                "$eq": [
                    "templateid",
                    1 // filter by a specfic rights template ID
                ]
            },
            {
                "$join": [
                    0,
                    "childrecordid",
                    "recordid",
                    {
                        "$and": [
                            {
                                "$eq": [
                                    "childchartypeid",
                                    3
                                ]
                            },
                            {
                                "$join": [
                                    0,
                                    "parentrecordid",
                                    "relrecid",
                                    {
                                        "$and": [
                                            {
                                                "$eq": [
                                                    "childchartypeid",
                                                    2
                                                ]
                                            },
                                            {
                                                "$eq": [
                                                    "parentchartypeid",
                                                    0
                                                ]
                                            },
                                            {
                                                "$eq": [
                                                    "childrecordid",
                                                    {CONTACT_ID}  // replace with the contact record ID
                                                ]
                                            }
                                        ]
                                    }
                                ]
                            }
                        ]
                    }
                ]
            }
        ]
    },
    "start": 0,
    "rows": 100
}
```
{% endcode %}
