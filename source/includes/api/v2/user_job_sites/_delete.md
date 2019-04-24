## Delete a User Job Site

```http
DELETE /api/public/v2/user_job_sites/:id HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X DELETE \
  https://app.makeshift.ca/api/public/v2/user_job_sites/:id \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
}'
```

This endpoint will delete a User Job Site by its ID.

### HTTP Request

`DELETE /api/public/v2/user_job_sites/:id`