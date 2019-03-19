## Get a Location by ID

This endpoint retrieves the data for a single Location.

### HTTP Request

`GET /api/public/v2/locations/<id>`

```http
GET /api/public/v2/locations/123 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/locations/123' \
  -H 'Authorization: Bearer <token>'
```

```json
{
  "data": {
    "id": "123",
    "type": "location",
    "attributes": {
        "name": "Victoria",
        "time_zone": "America/Los_Angeles",
        "external_name": null,
        "api_id": null,
        "week_starts_on": 0
    },
    "relationships": {
      "departments": {
        "data": [
          {
            "id": "1",
            "type": "department"
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
fields | All | A comma-separated list of fields to select. Example: `?fields[location]=name,id`
