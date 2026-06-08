# Overview

Requests to the RightsLine API are made to a specific endpoint.  Endpoints are constructed with the following structure:

`https://{base_url}/v{version_no}/{endpoint}`

* **base\_url**: See [table](./#base-url-by-environment) below.
* **version\_no**: 4
* **endpoint**: Specific endpoint depending on entity type.

### Base URL by environment

| Environment    | Base URL                   |
| -------------- | -------------------------- |
| Production US  | ris.rightsline.com         |
| Integration US | ris-int.rightsline.com     |
| Staging US     | ris-staging.rightsline.com |
| Prod Mirror US | ris-pm.rightsline.com      |
| Production EU  | api.rightsline.eu          |
| Staging EU     | api-staging.rightsline.eu  |

