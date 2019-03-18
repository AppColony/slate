## Update a Position by ID

```http
PUT /api/public/v2/positions/123 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "position",
    "attributes": {
      "name": "Sous Chef"
    }
  }
}
```

```shell
curl -X PUT \
  https://app.makeshift.ca/api/public/v2/positions/123 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "position",
    "attributes": {
      "name": "Sous Chef"
    }
  }
}'
```

This endpoint updates a Position with a given ID.

### HTTP Request

`POST /api/public/v2/positions/<id>`

### Request Body

Parameter     | Description
---------     | -----------
name          | Position's name
api_id        | A unique ID for identifying a Position
external_name | An identifier for a Position
