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

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "d85a36cce4c7b4964413d056d8da7b39",
    "type": "job_status",
    "attributes": {
      "job_name": "user_archive",
      "state": "running"
    }
  }
}
```

Get a single job status by it's ID. The ID can be found either in the return body of any *asynchronous API* operation or from the job status listings endpoint.

### HTTP Request

`GET /api/public/v2/job_statuses/<id>`
