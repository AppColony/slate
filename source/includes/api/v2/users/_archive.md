## Archive a User

```http
DELETE /api/public/v2/users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X DELETE \
  https://app.makeshift.ca/api/public/v2/users/<id> \
  -H 'Authorization: Bearer <token>' \
```

This endpoint will archive a user. In MakeShift, archiving a user is essentially "deleting" a user. The user is put away and be unarchived in the future. **NOTE:** Archiving a user removes all future scheduled shifts, closed pending exchanges and bis on available shifts. This is a destructive operation.


### HTTP Request

`DELETE /api/public/v2/users/<id>`

### HTTP Response Codes

Status | Meaning
---------- | -------
202 | Accepted. The request is successful yet deferred. A job has been queued to archive this user.
404 | Cannot find user to archive. This could mean an incorrect ID or that this user is already archived. 

### Asynchronous Operation

Please note that archiving a user is an asynchronous operation. A successful call to this endpoint will return an HTTP status code of "202 — Accepted" and a JSON body containing information about the asynchronous job that was queued. Getting a 202 response does not guarantee that this user was successfully archived (although it will very likely succeed). 
