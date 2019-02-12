## Update a location by ID

```http
PUT /api/public/v2/locations/222 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "location",
    "attributes": {
      "name": "Makeshift Furniture"
    }
  }
}
```

```shell
curl -X PUT \
  https://app.makeshift.ca/api/public/v2/locations/222 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "location",
    "attributes": {
      "name": "Makeshift Furniture"
    }
  }
}'
```

This endpoint updates a location with a given ID.

### HTTP Request

`POST /api/public/v2/locations/<id>`

### Request Body

Parameter     | Description
---------     | -----------
name          | Location's name
external_name | An ID by which an API wishes to identify a Location
