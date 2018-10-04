## Upsert a user

```http
PATCH /api/public/v1/users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer 3142fa748e2efb1b6e78e3a11a797cd1aafa76924d43ec5dc165c9591a2a8a52

{
  "data": {
    "type": "user",
    "attributes": {
      "external_id": "lawyer1",
      "first_name": "Atticus",
      "last_name": "Finch"
    }
  }
}
```

```shell
curl -X PATCH \
  https://app.makeshift.ca/api/public/v1/users \
  -H 'Authorization: Bearer 3142fa748e2efb1b6e78e3a11a797cd1aafa76924d43ec5dc165c9591a2a8a52' \
  -d '{
  "data": {
    "type": "user",
    "attributes": {
      "external_id": "lawyer1",
      "first_name": "Atticus",
      "last_name": "Finch"
    }
  }
}'
```

This endpoint will update a user with a given external ID, or create them if they don't exist.

### HTTP Request

`PATCH /api/public/v1/users`

### Request Body

Parameter          | Required | Description
---------          | -------- | -----------
external_id        | ✓        | An ID by which an API wishes to identify a User
first_name         | ✗        | User's first name
last_name          | ✗        | User's last name
middle_name        | ✗        | User's middle name
email              | ✗        | User's email address
employee_id        | ✗        | Used for clocking in and out
phone_number       | ✗        | User's phone number
phone_country_code | ✗        | User's phone country code
hire_date          | ✗        | Date the user was hired
employment_type    | ✗        | "Full Time", "Part Time", or "Casual"
role               | ✗        | "employee", "department_admin", "location_admin", or "company_admin"
