## Upsert a department

```http
PATCH /api/public/v2/departments HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "department",
    "attributes": {
      "name": "IT Dept.",
      "location_id": 222,
      "external_id": "ITD-002"
    }
  }
}
```

```shell
curl -X PATCH \
  https://app.makeshift.ca/api/public/v2/departments \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "department",
    "attributes": {
      "name": "IT Dept.",
      "location_id": 222,
      "external_id": "ITD-002"
    }
  }
}'
```

This endpoint will update a department with a given external id, or create one if it doesn't exist.

### HTTP Request

`PATCH /api/public/v2/departments`

### Request Body

Parameter          |  Create   | Update       | Description
---------          | --------- | ----------   |-----------
external_id        |  ✓        | ✓            | A unique idenfier for a Department
name               |  ✓        | ○            | Department's name
location_id        |  ✓        | ✗            | Location's ID

✓ = Required &nbsp; ○ = Optional &nbsp; ✗ = Ignored

