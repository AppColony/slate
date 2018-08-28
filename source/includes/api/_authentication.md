# Authentication

> To authorize using a username and password, use this code:

```http
POST /oauth/token HTTP/1.1
Host: app.makeshift.ca
Content-Type: application/json
Cache-Control: no-cache

{
  "grant_type"  : "password",
  "username"    : "admin@appcolony.ca",
  "password"    : "appcolony"
}
```

```shell
curl --request POST \
  --url https://id.makeshift.ca/oauth/token \
  --header 'Cache-Control: no-cache' \
  --header 'Content-Type: application/json' \
  --data '{ "grant_type": "password", "username": "admin@appcolony.ca", "password": "appcolony" }'
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

`Authorization: Bearer defaaddbb673c8afeef85666f07aa4a11f3e0a2f487bf9c714ab00ba2b11c614`
