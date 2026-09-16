# Schedule

Char Type ID: **19**

### Endpoints

| Method | Endpoint                           | Description                           |
| ------ | ---------------------------------- | ------------------------------------- |
| POST   | /v4/schedule                       | Create a schedule.                    |
| GET    | /v4/schedule/:id                   | Retrieve a schedule.                  |
| PUT    | /v4/schedule/:id                   | Update a schedule.                    |
| DELETE | /v4/schedule/:id                   | Delete a schedule.                    |
| GET    | /v4/schedule-templates             | Retrieve schedule templates.          |
| GET    | /v4/schedule-statuses/:templateId  | Retrieve schedule statuses.           |
| GET    | /v4/schedule-processes             | Retrieve schedule workflow processes. |
| GET    | /v4/schedule/:id/draft-templates   | Retrieve schedule draft templates.    |
| GET    | /v4/schedule/:id/audit-history     | Retrieve schedule audit history.      |
| POST   | /v4/schedule/:id/switch-template   | Switch schedule template.             |
| GET    | /v4/schedule/:id/validation-errors | Retrieve schedule validation errors.  |
