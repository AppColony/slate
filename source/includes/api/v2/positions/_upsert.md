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
    "type": "positions",
    "attributes": {
      "external_name": "E01-Cook",
      "name": "Sandwich Artist",
      "department_id": 1
    }
  }
}
```

```shell
curl -X PATCH \
  https://app.makeshift.ca/api/public/v2/users \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "positions",
    "attributes": {
      "external_name": "E01-Cook",
      "name": "Sandwich Artist",
      "department_id": 1
    }
  }
}'
```

This endpoint will update a position with a given external name, or create one if it don't exist.

### HTTP Request

`PATCH /api/public/v2/positions`

### Request Body

Parameter          |  Create   | Update       | Description
---------          | --------- | ----------   |-----------
external_name      |  ✓        | ✓            | An ID by which an API wishes to identify a Position
name               |  ✓        | ○            | Position's name
department_id      |  ✓        | ✗            | Department to which the Position belongs

✓ = Required &nbsp; ○ = Optional &nbsp; ✗ = Ignored

