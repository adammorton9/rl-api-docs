# Get dimension data

## Get dimension data

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/avails/dimension-data`

This endpoint returns availability dimension data.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Returns availability dimension data." %}
```javascript
{
	"dim1":[
		{
			"id":75,
			"label":"All Media",
			"xref":null,
			"childListItems":[
				{
					"id":16,
					"label":"Linear",
					"xref":null,
					"childListItems":[
						...
					]
				},
				...
			]
		}
	],
	"dim2":[
		{
			"id":1,
			"label":"World",
			"xref":null,
			"childListItems":[
				{
					"id":45,
					"label":"Europe",
					"xref":null,
					"childListItems":[
						...
					]
				},
				...
			]
		}
	],
	"dim3":[
		{
			"id":1,
			"label":"All Languages",
			"xref":null,
			"childListItems":[
				{
					"id":4,
					"label":"Afghan/Pashtu",
					"xref":null
				},
				{
					"id":2,
					"label":"Afrikaans",
					"xref":null
				},
				...
			]
		}
	],
	"dim4":[
		...
	]
}
```
{% endtab %}
{% endtabs %}

