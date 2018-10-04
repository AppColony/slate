## Update a user by ID

```http
PUT /api/public/v1/users/7345 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer 3142fa748e2efb1b6e78e3a11a797cd1aafa76924d43ec5dc165c9591a2a8a52

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
  https://app.makeshift.ca/api/public/v1/users/7345 \
  -H 'Authorization: Bearer 3142fa748e2efb1b6e78e3a11a797cd1aafa76924d43ec5dc165c9591a2a8a52' \
  -d '{
  "data": {
    "type": "user",
    "attributes": {
      "employment_type": "Casual"
    }
  }
}'
```

This endpoint updates a user with a given ID

### HTTP Request

`POST /api/public/v1/users/<id>`

### Request Body

Parameter          | Description
---------          | -----------
first_name         | User's first name
last_name          | User's last name
middle_name        | User's middle name
email              | User's email address
employee_id        | Used for clocking in and out
phone_number       | User's phone number
phone_country_code | User's phone country code
hire_date          | Date the user was hired
employment_type    | "Full Time", "Part Time", or "Casual"
role               | "employee", "department_admin", "location_admin", or "company_admin"
external_id        | An ID by which an API wishes to identify a User
