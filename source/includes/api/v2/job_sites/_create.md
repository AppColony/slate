## Create a job site

```http
POST /api/public/v2/job_sites HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "job_site",
    "attributes": {
      "name": "East Kitchen",
      "department_id": 548
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca/api/public/v2/job_sites \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "job_site",
    "attributes": {
      "name": "East Kitchen",
      "department_id": 548
    }
  }
}'
```

This endpoint creates a new job site.

### HTTP Request

`POST /api/public/v2/job_sites`

### Request Body

Parameter          | Required | Default     | Description
---------          | -------- | -------     | -----------
name               | ✓        |             | Job Site's name
department_id      | ✓        |             | Department to which the Job Site belongs
external_id        | ✗        |             | An ID by which an API wishes to identify a Job Site
