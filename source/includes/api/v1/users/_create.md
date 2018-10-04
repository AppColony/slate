## Create a user

```http
POST /api/public/v1/users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer 3142fa748e2efb1b6e78e3a11a797cd1aafa76924d43ec5dc165c9591a2a8a52

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
  https://app.makeshift.ca /api/public/v1/users \
  -H 'Authorization: Bearer 3142fa748e2efb1b6e78e3a11a797cd1aafa76924d43ec5dc165c9591a2a8a52' \
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

`POST /api/public/v1/users`

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
