# Create a party relationship

To add a party to a module record, you can use the create relationship endpoint and specify the party ID as the relationshipTypeId.  For example, to associate contact record 200 to deal record 100 as party ID 1, you can use the following request:

{% code title="POST /v4/relationship" %}
```json
{
    "parentRecordId": 100,
    "parentCharTypeId": 4,
    "childRecordId": 200,
    "childCharTypeId": 2,
    "relationshipType":{
        "relationshipTypeId": 1
    }
}
```
{% endcode %}

Party IDs can be found via the UI under Configuration > Parties.



{% tabs %}
{% tab title="200 Relationship created successfully." %}
```json
1368592963 //Relationship ID
```
{% endtab %}

{% tab title="400 Invalid relationship type " %}
```
{
    "message": "Unable to create relationship. Relationship Type ID must be a valid Party ID."
}
```
{% endtab %}
{% endtabs %}
