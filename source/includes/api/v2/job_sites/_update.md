## Update a Job Site by ID

```http
PUT /api/public/v2/job_sites/123 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "job_site",
    "attributes": {
      "name": "West Wing"
    }
  }
}
```

```shell
curl -X PUT \
  https://app.makeshift.ca/api/public/v2/job_sites/123 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "job_site",
    "attributes": {
      "name": "Loft"
    }
  }
}'
```

This endpoint updates a Job Site with a given ID.

### HTTP Request

`POST /api/public/v2/job_sites/<id>`

### Request Body

Parameter   | Description
---------   | -----------
name        | Job Site's name
api_id | A unique ID for identifying a Job Site
external_id | An identifier for a Job Site
