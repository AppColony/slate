## Get a department by ID

This endpoint retrieves the data for a single department.

### HTTP Request

`GET /api/public/v2/departments/<id>`

```http
GET /api/public/v2/departments/123 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/departments/123' \
  -H 'Authorization: Bearer <token>'
```

```json
{
  "data": {
    "id": "123",
    "type": "department",
    "attributes": {
      "name": "Kitchen",
      "location_id": 325,
      "external_id": "001",
      "last_published_at": "2019-01-29 23:51:09 UTC",
      "updated_at": "2019-01-29 23:51:09 UTC"
    },
    "relationships": {
      "users": {
        "data": [
          {
            "id": "7347",
            "type": "user"
          }
        ]
      },
      "positions": {
        "data": [
          {
            "id": "2832",
            "type": "position"
          }
        ]
      },
      "job_sites": {
        "data": [
          {
            "id": "1",
            "type": "job_site"
          }
        ]
      }
    }
  }
}
```

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[department]=name,id`
