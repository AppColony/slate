## Get a position by ID

```http
GET /api/public/v2/positions/123 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/positions/123' \
  -H 'Authorization: Bearer <token>'
```

```json
{
    "data": {
        "id": "123",
        "type": "position",
        "attributes": {
            "department_id": 548,
            "name": "Chef",
            "external_name": null
        }
    }
}
```

This endpoint retrieves the data for a single position.

### HTTP Request

`GET /api/public/v2/positions/<id>`
