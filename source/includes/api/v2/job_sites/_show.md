## Get a job site by ID

```http
GET /api/public/v2/job_sites/444 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/job_sites/444' \
  -H 'Authorization: Bearer <token>'
```

```json
{
    "data": {
        "id": "444",
        "type": "job_site",
        "attributes": {
            "department_id": 548,
            "name": "East Site 0001",
            "external_id": null
            "api_id": null
        }
    }
}
```

This endpoint retrieves the data for a single job site.

### HTTP Request

`GET /api/public/v2/job_sites/<id>`
