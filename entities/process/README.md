# Process

Char Type ID: **22**

### Endpoints

| Method | Endpoint                          | Description                          |
| ------ | --------------------------------- | ------------------------------------ |
| POST   | /v4/process                       | Create a process.                    |
| GET    | /v4/process/:id                   | Retrieve a process.                  |
| PUT    | /v4/process/:id                   | Update a process.                    |
| DELETE | /v4/process/:id                   | Delete a process.                    |
| GET    | /v4/process-templates             | Retrieve process templates.          |
| GET    | /v4/process-statuses/:templateId  | Retrieve process statuses.           |
| GET    | /v4/process-processes             | Retrieve process workflow processes. |
| GET    | /v4/process/:id/draft-templates   | Retrieve process draft templates.    |
| GET    | /v4/process/:id/audit-history     | Retrieve process audit history.      |
| POST   | /v4/process/:id/switch-template   | Switch process template.             |
| GET    | /v4/process/:id/validation-errors | Retrieve process validation errors.  |
