## Upsert a Job Site

```http
PATCH /api/public/v2/job_sites HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "job_sites",
    "attributes": {
      "external_id": "J02-Cafe",
      "name": "Coffee Plaza",
      "department_id": 1
    }
  }
}
```

```shell
curl -X PATCH \
  https://app.makeshift.ca/api/public/v2/users \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "job_sites",
    "attributes": {
      "external_id": "J02-Cafe",
      "name": "Coffee Plaza",
      "department_id": 1
    }
  }
}'
```

This endpoint will update a job site with a given external id, or create one if it doesn't exist.

### HTTP Request

`PATCH /api/public/v2/job_sites`

### Request Body

Parameter          |  Create   | Update       | Description
---------          | --------- | ----------   |-----------
external_id        |  ✓        | ✓            | A unique identifier for a Job Site
name               |  ✓        | ○            | Job Site's name
department_id      |  ✓        | ✗            | Department to which the Job Site belongs

✓ = Required &nbsp; ○ = Optional &nbsp; ✗ = Ignored

