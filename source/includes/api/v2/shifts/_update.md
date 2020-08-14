## Update a Shift

```http
PUT /api/public/v2/shifts/135009 HTTP/1.1
Host: localhost:3000
Authorization: Bearer 70c204730bc448a9166ede1738396d5ed9cffb9a97eb68b2d929c2f612e90f15
```

> A minimal payload example:

```json
{
  "data": {
    "type": "shift",
    "attributes": {
      "starts_at": "2019-01-01T09:00-08",
      "ends_at": "2019-01-01T19:00-08"
    }
  }
}
```

```shell
curl -X PUT 'http://localhost:3000/api/public/v2/shifts/135009' \
  -H 'Authorization: Bearer 70c204730bc448a9166ede1738396d5ed9cffb9a97eb68b2d929c2f612e90f15' \
  -d '{
  "data": {
    "type": "shift",
    "attributes": {
      "starts_at": "2019-01-01T09:00-08",
      "ends_at": "2019-01-01T19:00-08"
    }
  }
}'
```

This endpoint updates an existing new Shift. 

### HTTP Request

`POST /api/public/v2/shifts/<id>`

### Request Body

Parameter          | Required | Default     | Description
---------          | -------- | -------     | -----------
starts_at          | ✗        |             | The start date/time of the Shift
ends_at            | ✗        |             | The end date/time of the Shift
