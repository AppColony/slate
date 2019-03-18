# Sorting

> Sort users by "employee_id" (ascending)

```http
GET /public/v2/users?sort=employee_id HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

> Sort users by "employee_id` (descending)

```http
GET /public/v2/users?sort=-employee_id HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

Most endpoints that return multiple objects can be sorted by certain properties listed in that endpoint's documentation.

An example of sorting a list of users by `employee_id`:

`https://app.makeshift.ca/api/public/v2/users?sort=employee_id`

Appending a "-" to a property indicates that it should be sorted in _descending_ order. The default sorting order is otherwise _ascending_.
