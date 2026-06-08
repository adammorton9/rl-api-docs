# Get user identity role

## Get user identity role

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/user/identity-role/:roleID`

#### Path Parameters

| Name                                     | Type | Description           |
| ---------------------------------------- | ---- | --------------------- |
| roleID<mark style="color:red;">\*</mark> | int  | The identity role ID. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK User identity role retrieved successfully." %}
```json

{
    "activityPolicyId": "431889c1-b6b5-4130-b5d5-b22b01f44937",
    "dataPolicyId": "046282aa-d31b-4215-927d-fe291a6fb64a",
    "id": "8f371bcf-b3ed-4280-b3bd-6ca7241af94c",
    "name": "Identity Role 1",
    "xref": "role-1"
}
```
{% endtab %}
{% endtabs %}
