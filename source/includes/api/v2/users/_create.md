## Create a user

```http
POST /api/public/v2/users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "user",
    "attributes": {
      "first_name": "Old",
      "last_name": "Gregg"
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca /api/public/v2/users \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "user",
    "attributes": {
      "first_name": "Old",
      "last_name": "Gregg"
    }
  }
}'
```

This endpoint creates a new user.

### HTTP Request

`POST /api/public/v2/users`

### Request Body

Parameter          | Required | Default     | Description
---------          | -------- | -------     | -----------
first_name         | ✓        |             | User's first name
last_name          | ✓        |             | User's last name
middle_name        | ✗        |             | User's middle name
email              | ✗        |             | User's email address
employee_id        | ✗        | random      | Used for clocking in and out
phone_number       | ✗        |             | User's phone number
phone_country_code | ✗        | "1"         | User's phone country code
hire_date          | ✗        |             | Date the user was hired
employment_type    | ✗        | "Full Time" | "Full Time", "Part Time", or "Casual"
role               | ✗        | "employee"  | "employee", "department_admin", "location_admin", or "company_admin"
external_id        | ✗        |             | An ID by which an API wishes to identify a User
