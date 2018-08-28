# Authentication

> To authorize using a username and password, use this code:

```shell
curl --request POST \
  --url https://app.makeshift.ca/oauth/token \
  --header 'Cache-Control: no-cache' \
  --header 'Content-Type: application/json' \
  --data '{ "grant_type": "password", "username": "admin@appcolony.ca", "password": "appcolony" }'
```

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

> Make sure to replace your username and password information.

A MakeShift API token can be retrieved for any company admin using a username/password.

`Authorization: Bearer defaaddbb673c8afeef85666f07aa4a11f3e0a2f487bf9c714ab00ba2b11c614`
