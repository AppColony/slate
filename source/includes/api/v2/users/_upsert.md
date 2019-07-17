## Upsert a User

```http
PATCH /api/public/v2/users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "user",
    "attributes": {
      "api_id": "lawyer1",
      "first_name": "Atticus",
      "last_name": "Finch"
    }
  }
}
```

```shell
curl -X PATCH \
  https://app.makeshift.ca/api/public/v2/users \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "user",
    "attributes": {
      "api_id": "lawyer1",
      "first_name": "Atticus",
      "last_name": "Finch"
    }
  }
}'
```

This endpoint will update a User with a given API ID, or create them if they don't exist.

### HTTP Request

`PATCH /api/public/v2/users`

### Request Body

Parameter          | Required | Description
---------          | -------- | -----------
api_id             | ✓        | A unique ID for identifying a User
first_name         | Create Only  | User's first name
last_name          | Create Only  | User's last name
middle_name        | ✗        | User's middle name
email              | ✗        | User's email address
employee_id        | ✗        | Used for clocking in and out
phone_number       | ✗        | User's phone number
hire_date          | ✗        | Date the user was hired (ISO8601 ex: '2019-07-17')
employment_type    | ✗        | "full_time", "part_time", or "casual"
role               | ✗        | "employee", "department_admin", "location_admin", or "company_admin"
