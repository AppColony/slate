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
202 | Accepted. The request is successful yet deferred. A job has been queued to delete this location.
404 | Cannot find location to delete. This could mean an incorrect ID or that this location was already deleted. 

### Asynchronous Operation

Please note that deleting a location is an asynchronous operation. A successful call to this endpoint will return an HTTP status code of "202 — Accepted" and a JSON body containing information about the asynchronous job that was queued. Getting a 202 response does not guarantee that this location was successfully deleted (although it will very likely succeed). 
