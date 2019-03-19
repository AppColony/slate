## Update a Department by ID

```http
PUT /api/public/v2/departments/222 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "department",
    "attributes": {
      "name": "IT Dept."
    }
  }
}
```

```shell
curl -X PUT \
  https://app.makeshift.ca/api/public/v2/departments/222 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "department",
    "attributes": {
      "name": "IT Dept."
    }
  }
}'
```

This endpoint updates a Department with a given ID.

### HTTP Request

`POST /api/public/v2/departments/<id>`

### Request Body

Parameter   | Description
---------   | -----------
name        | Department's name
external_id | An identifier for a Department
api_id      | A unique ID for identifying a Department
