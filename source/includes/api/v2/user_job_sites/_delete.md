## Disassociate a User from a Job Site

```http
DELETE /api/public/v2/users/7345/job_sites/7 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X DELETE \
  https://app.makeshift.ca/api/public/v2/users/7345/job_sites/7 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```

This endpoint will delete a User Job Site.

### HTTP Request

`DELETE /api/public/v2/users/:user_id/job_sites/:job_site_id`

### HTTP Response Codes

Status | Meaning
---------- | -------
202 | Accepted. The request is successful yet deferred. A job has been queued.
404 | Cannot find User Job Site to disassociate. This could mean an incorrect ID or that it's already been disassociated. 

### Asynchronous Operation
  
Please note this is an async operation, a successful call will return a 202 with a JSON body containing async job info.  Read more about [Asynchronous Operations](#asynchronous-endpoints).