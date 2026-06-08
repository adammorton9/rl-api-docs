# Search fields

### Entity fields

| Search field | Description                               | Corresponding API field |
| ------------ | ----------------------------------------- | ----------------------- |
| `recordid`   | Record ID                                 | id                      |
| `chartypeid` | [Char Type ID](../entities/char-types.md) | N/A                     |
| `title`      | Entity title                              | title                   |
| `recrevid`   | Revision ID                               | revisionId              |

### Template and status fields

| Search field | Description   | Corresponding API field |
| ------------ | ------------- | ----------------------- |
| `template`   | Template name | template.templateName   |
| `templateid` | Template ID   | template.templateId     |
| `status`     | Status name   | status.statusName       |
| `statusid`   | Status ID     | status.statusId         |

### Audit fields

| Search field        | Description                          | Corresponding API field |
| ------------------- | ------------------------------------ | ----------------------- |
| `created`           | Record created date                  | createdDate             |
| `created_by`        | User ID that created record          | createdById             |
| `last_updated`      | Record last updated date             | lastUpdatedDate         |
| `last_updated_by`   | User ID that last updated record     | lastUpdatedById         |
| `status_updated`    | Record last status updated date      | statusUpdatedDate       |
| `status_updated_by` | User ID that last updated the status | statusUpdatedById       |

### Relationship fields

| Search field       | Description          | Corresponding API field             |
| ------------------ | -------------------- | ----------------------------------- |
| `relrecid`         | Relationship ID      | id                                  |
| `relind`           | Relationship Type ID | relationshipType.relationshipTypeId |
| `parentchartypeid` | Parent Char Type ID  | parentCharTypeId                    |
| `parentrecordid`   | Parent Record ID     | parentRecordId                      |
| `childchartypeid`  | Child Char Type ID   | childCharTypeId                     |
| `childrecordid`    | Child Record ID      | childRecordId                       |
| `sequencenumber`   | Sequence Number      | sequenceNumber                      |

### Characteristic fields

All fields configured as characteristics in Rightsline are also searchable by their tag label. This tag label can be found in the configuration UI or by examining the templates response found [here](../config/templates.md#get-template-details) (deal template as an example).&#x20;

### Hierarchy fields

For the primary rights dimensions where the data is typically a selection of values from a larger hierarchy of possible values (e.g. Media, Territory), there are search fields available to make use of the structure of that hierarchy when performing the search. A common use case for this would be searching for all rights involving any of the countries of a specific continent (e.g. find all rights where the territory is a country, or countries, in Europe). A search like that would make use of a `territory_leafids` search field in which the all of the leaf IDs of the selected territory are stored. So the search from the example above would look something like:

```
{
    "query": {
     "$eq_any":["territory_leafids","45"] //where 45 is the ID of Europe
    }
}
```

Each of the rights dimensions would have a corresponding `_leafids` field where they prefix is the tag label for that characteristic.

Similarly, if the search needed to return all rights where a particular branch value is selected or covered by selections higher up the hierarchy (e.g. find all rights where Europe is selected, or Worldwide), the same `_leafids` field would be used, with the operator switched to `$eq_all`.

### Case-insensitive search

Sometimes it is necessary to search for records where you are unsure of the casing of a particular value. To do a case-insensitive search against a given string characteristic, append the `_istr` suffix to the characteristic tag label, add `* *` around the search term, and include the `"$quoted":[false]` field in the search request. For example, to find all catalog items where the notes characteristic contains `new`, do the following search:

```json
{
   "query": {
       "$and": [
           {
               "$contains": [
                   "notes_istr",
                   "*new*"
               ],
               "$quoted":[false]
           }
       ]
   }
}
```
