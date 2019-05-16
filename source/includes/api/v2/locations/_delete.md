## Delete a Location

```http
DELETE /api/public/v2/locations/339 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```


```shell
curl -X DELETE \
  https://app.makeshift.ca/api/public/v2/locations/339 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```

This endpoint deletes an existing Location.

### HTTP Request

`DELETE /api/public/v2/locations/<id>`

### HTTP Response Codes

Status | Meaning
---------- | -------
202 | Accepted. The request is successful yet deferred. A job has been queued.
404 | Cannot find location to delete. This could mean an incorrect ID or that it's already been deleted.

### Asynchronous Operation
  
Please note this is an async operation, a successful call will return a 202 with a JSON body containing async job info.  Read more about [Asynchronous Operations](#asynchronous-endpoints).
