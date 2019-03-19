## Associate a User with a Department

```http
POST /api/public/v2/department_users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "department_user",
    "attributes": {
      "user_id": 7442,
      "department_id": 12,
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca/api/public/v2/department_users \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "department_user",
    "attributes": {
      "user_id": 7442,
      "department_id": 12,
    }
  }
}'
```

This endpoint creates an association between a User and a Department.

### HTTP Request

`POST /api/public/v2/department_users`

### Request Body

Parameter     | Required | Default | Description
---------     | -------- | ------- | -----------
user_id       | ✓        |         | User ID to associate to a department
department_id | ✓        |         | Department ID to associate user with
