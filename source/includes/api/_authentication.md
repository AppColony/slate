# Authentication

> To authorize using a username and password, use this code:

```http
POST /oauth/token HTTP/1.1
Host: app.makeshift.ca
Content-Type: application/json
Cache-Control: no-cache

{
  "grant_type"  : "password",
  "username"    : "company_admin@company.com",
  "password"    : "PassWord1243!"
}
```

```shell
curl --request POST \
  --url https://id.makeshift.ca/oauth/token \
  --header 'Cache-Control: no-cache' \
  --header 'Content-Type: application/json' \
  --data '{ "grant_type": "password", "username": "company_admin@company.com", "password": "PassWord1234!" }'
```

> Response example:

```json
{
    "access_token": "c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b",
    "token_type": "bearer",
    "created_at": 1535435882,
    "user": {
        "id": 1,
        "name": "Primary API User",
        "role": "company_admin",
        "email": "company_admin@company.com",
        "employee_id": "12345",
        "company_id": 270
    }
}
```

> To use your token in API requests:

```http
GET /api/public/v1/<endpoint> HTTP/1.1
Host: app.makehshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v1/<endpoint>' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```


A MakeShift API token can be retrieved for any company admin using a username/password.

<aside class="notice">
  Note that authentication should happen against MakeShift's central auth system <a href="https://id.makeshift.ca">https://id.makeshift.ca</a>
</aside>

Use the returned token in API requests using an HTTP `Authorization` header, like so:

`Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b`
