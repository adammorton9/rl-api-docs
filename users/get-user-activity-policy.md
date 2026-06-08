# Get user activity policy

## Get user activity policy

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/user/activity-policy/:policyID`

#### Path Parameters

| Name                                       | Type | Description             |
| ------------------------------------------ | ---- | ----------------------- |
| policyID<mark style="color:red;">\*</mark> | int  | The activity policy ID. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK User activity policy retrieved successfully." %}
```json
[
    {
        "name": "UX2",
        "description": "",
        "isDisabled": false,
        "permissionValue": 1,
        "childNodes": [
            {
                "name": "Record Access",
                "description": "",
                "isDisabled": false,
                "permissionValue": 1,
                "childNodes": [
                    {
                        "name": "Mine Only",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Projects",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Catalog",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Deals",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Inventory",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Jobs",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 0,
                                "childNodes": []
                            },
                            {
                                "name": "Accounting",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    }
                ]
            },
            {
                "name": "Associations",
                "description": "",
                "isDisabled": false,
                "permissionValue": 1,
                "childNodes": [
                    {
                        "name": "Contacts",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    },
                    {
                        "name": "Projects",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Projects",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Catalog",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Inventory",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Jobs",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    },
                    {
                        "name": "Catalog",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Catalog",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Inventory",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    },
                    {
                        "name": "Deals",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Projects",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Catalog",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Deals",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Inventory",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Jobs",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Accounting",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    },
                    {
                        "name": "Inventory",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Inventory",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    },
                    {
                        "name": "Jobs",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Catalog",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Inventory",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Jobs",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Accounting",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    },
                    {
                        "name": "Accounting",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 1,
                        "childNodes": [
                            {
                                "name": "Contacts",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Projects",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Catalog",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            },
                            {
                                "name": "Inventory",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 1,
                                "childNodes": []
                            }
                        ]
                    }
                ]
            },
            {
                "name": "Administration",
                "description": "",
                "isDisabled": false,
                "permissionValue": 0,
                "childNodes": [
                    {
                        "name": "Company Settings",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 0,
                        "childNodes": [
                            {
                                "name": "Company Overview",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 0,
                                "childNodes": [
                                    {
                                        "name": "Contacts",
                                        "description": "",
                                        "isDisabled": false,
                                        "permissionValue": 0,
                                        "childNodes": []
                                    },
                                    {
                                        "name": "Payment Information",
                                        "description": "",
                                        "isDisabled": false,
                                        "permissionValue": 0,
                                        "childNodes": []
                                    },
                                    {
                                        "name": "Other Settings",
                                        "description": "",
                                        "isDisabled": false,
                                        "permissionValue": 0,
                                        "childNodes": []
                                    }
                                ]
                            },
                            {
                                "name": "Esignature Keys",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 0,
                                "childNodes": []
                            }
                        ]
                    },
                    {
                        "name": "User Administration",
                        "description": "",
                        "isDisabled": false,
                        "permissionValue": 0,
                        "childNodes": [
                            {
                                "name": "Users",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 0,
                                "childNodes": []
                            },
                            {
                                "name": "Roles",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 0,
                                "childNodes": [
                                    {
                                        "name": "Identity Roles",
                                        "description": "",
                                        "isDisabled": false,
                                        "permissionValue": 0,
                                        "childNodes": []
                                    },
                                    {
                                        "name": "Workflow Roles",
                                        "description": "",
                                        "isDisabled": false,
                                        "permissionValue": 0,
                                        "childNodes": []
                                    }
                                ]
                            },
                            {
                                "name": "Policies",
                                "description": "",
                                "isDisabled": false,
                                "permissionValue": 0,
                                "childNodes": [
                                    {
                                        "name": "Activity Policies",
                                        "description": "",
                                        "isDisabled": false,
                                        "permissionValue": 0,
                                        "childNodes": []
                                    },
                                    {
                                        "name": "Data Policies",
                                        "description": "",
                                        "isDisabled": false,
                                        "permissionValue": 0,
                                        "childNodes": []
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
```
{% endtab %}
{% endtabs %}

The response object mimics the Activity Policy grid in the UI. The fields in the response object are:

`name` - The name of the permission node.

`description` - A description of the permission node.

`isDisabled` - If the permission node is disabled (represented by a greyed out toggle in the UI).

`permissionValue` - 0 if the permission is denied, 1 if the permission is allowed.

`childNodes` - Any child permission nodes.
