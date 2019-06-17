## Upsert a Position

```http
PATCH /api/public/v2/positions HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "position",
    "attributes": {
      "api_id": "E01-Cook",
      "name": "Sandwich Artist",
      "department_id": 1
    }
  }
}
```

```shell
curl -X PATCH \
  https://app.makeshift.ca/api/public/v2/positions \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "position",
    "attributes": {
      "api_id": "E01-Cook",
      "name": "Sandwich Artist",
      "department_id": 1
    }
  }
}'
```

This endpoint will update a Position with a given API ID, or create one if it doesn't exist.

### HTTP Request

`PATCH /api/public/v2/positions`

### Request Body

Parameter          |  Create   | Update       | Description
---------          | --------- | ----------   |-----------
api_id             |  ✓        | ✓            | A unique identifier for a Position
name               |  ✓        | ○            | Position's name
department_id      |  ✓        | ✗            | Department to which the Position belongs

✓ = Required &nbsp; ○ = Optional &nbsp; ✗ = Cannot be changed

Properties such as `department_id` are required for creation but cannot be changed during an update. An UPSERT will allow passing the **same** value for `department_id` but result in an HTTP 422 if the value is changed.

