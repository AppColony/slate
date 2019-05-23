## Restore a User

```http
POST /api/public/v2/users/<id>/restore HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X DELETE \
  https://app.makeshift.ca/api/public/v2/users/<id>/restore \
  -H 'Authorization: Bearer <token>' \
```

This endpoint will restore an archived user to make them active again. Conceptually, it is the opposite of archiving a user. The user will have the same department, position, and job site associations that they had before archiving.

### HTTP Request

`POST /api/public/v2/users/<id>/restore`

> This call returns the corresponding User model:

```json
{
  "data": {
    "id": "7442",
    "type": "user",
    "attributes": {
      "first_name": "Shifty",
      "last_name": "McGee",
      "email": "shifty@makeshift.ca",
      "employee_id": "3030",
      "role": "employee",
      "api_id": null
    }
  }
}
```
