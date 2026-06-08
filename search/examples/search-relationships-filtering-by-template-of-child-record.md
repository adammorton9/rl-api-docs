# Search relationships, filtering by template of child record

This join query will filter the relationships returned by the template of the child records in the relationships. The example below is getting all rights (chartypeid 3) for a deal (chartypeid 4, record id 444) where those child rights are of a specific template (templateid 1).

```
POST - https://ris.rightsline.com/v4/relationship/search
{
    "query": {
        "$and": [
            {
                "$eq": [
                    "parentchartypeid",
                    4
                ]
            },
            {
                "$eq": [
                    "parentrecordid",
                    444
                ]
            },
            {
                "$eq": [
                    "childchartypeid",
                    3
                ]
            },
            {
                "$join": [
                    3,
                    "recordid",
                    "childrecordid",
                    {
                        "$eq": [
                            "templateid",
                            1
                        ]
                    }
                ]
            }
        ]
    }
}

```
