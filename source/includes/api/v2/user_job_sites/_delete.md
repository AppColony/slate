## Delete a User Job Site

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
