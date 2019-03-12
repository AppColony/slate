## Update a user by ID

```http
PUT /api/public/v2/users/7345 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "user",
    "attributes": {
      "employment_type": "Casual"
    }
  }
}
```

```shell
curl -X PUT \
  https://app.makeshift.ca/api/public/v2/users/7345 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "user",
    "attributes": {
      "employment_type": "Casual"
    }
  }
}'
```

This endpoint updates a user with a given ID.

**Note:** The ID here is a MakeShift ID (a simple integer). In order to create and update users using an ID from the integrating system please refer to a `upsert` endpoint.

### HTTP Request

`POST /api/public/v2/users/<id>`

### Request Body

Parameter          | Description
---------          | -----------
first_name         | User's first name
last_name          | User's last name
middle_name        | User's middle name
email              | User's email address
employee_id        | Used for clocking in and out
phone_number       | User's phone number
hire_date          | Date the user was hired
employment_type    | "full_time", "part_time", or "casual"
role               | "employee", "department_admin", "location_admin", or "company_admin"
api_id             | A unique ID for identifying a User
