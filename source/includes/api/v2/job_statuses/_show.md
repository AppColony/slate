## Get a Job Status by ID

```http
GET /api/public/v2/job_statuses/<id> HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  https://app.makeshit.ca/api/public/v2/job_statuses/<id> \
  -H 'Authorization: Bearer <token>' \
```

Get a single job status by it's ID. The ID can be found either in the return body of any *asynchronous API* operation or from the job status listings endpoint.

### HTTP Request

`GET /api/public/v2/job_statuses/<id>`
