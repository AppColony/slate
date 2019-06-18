## Upsert a Department

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
      "external_id": "2",
      "api_id": "ITD-002"
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
      "external_id": "2",
      "api_id": "ITD-002"
    }
  }
}'
```

This endpoint will update a Department with a given API ID, or create one if it doesn't exist.

### HTTP Request

`PATCH /api/public/v2/departments`

### Request Body

Parameter          |  Create   | Update       | Description
---------          | --------- | ----------   |-----------
api_id             |  ✓        | ✓            | A unique ID for identifying a Department
external_id        |  ✓        | ✓            | An idenfier for a Department
name               |  ✓        | ○            | Department's name
location_id        |  ✓        | ✗            | Location's ID

✓ = Required &nbsp; ○ = Optional &nbsp; ✗ = Cannot be changed

Properties such as `location_id` are required for creation but cannot be changed during an update. An UPSERT will allow passing the **same** value for `location_id` but result in an HTTP 422 if the value has changed.
