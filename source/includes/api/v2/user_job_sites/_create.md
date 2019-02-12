## Associate a user with a job site

```http
POST /api/public/v2/user_job_sites HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "user_job_site",
    "attributes": {
      "user_id": 7442,
      "job_site_id": 22
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca/api/public/v2/user_job_sites \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "user_job_site",
    "attributes": {
      "user_id": 7442,
      "job_site_id": 55
    }
  }
}'
```

This endpoint creates an association between a user and a job site.

### HTTP Request

`POST /api/public/v2/user_job_sites`

### Request Body

Parameter   | Required | Default | Description
---------   | -------- | ------- | -----------
user_id     | ✓        |         | User ID to associate with a job site
job_site_id | ✓        |         | Job Site ID to associate user with
