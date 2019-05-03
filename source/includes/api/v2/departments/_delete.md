## Delete a Department

```http
DELETE /api/public/v2/departments/556 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```


```shell
curl -X DELETE \
  https://app.makeshift.ca/api/public/v2/departments/556 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```


This endpoint deletes an existing Department.

### HTTP Request

`DELETE /api/public/v2/departments/<id>`
