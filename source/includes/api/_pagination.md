# Pagination

> Example of returned meta data

```json
"meta": {
  "shown": 97,
  "total": 97
},
"links": {
  "self": "https://app.makeshift.ca/api/public/v2/users?page[number]=1&page[size]=100",
  "next": "https://app.makeshift.ca/api/public/v2/users?page[number]=2"
}
```

All endpoints that return multiple objects are paginated by default. The maximum number of objects per page is 100 unless otherwise stated. Without specifying any pagination parameters the endpoint will paginate the equivalent of "page 1, page size 100" like so:

`https://app.makeshift.ca/api/public/v2/users?page[number]=1&page[size]=100`

Different pages and smaller page sizes can be specified like so:

`https://app.makeshift.ca/api/public/v2/users?page[number]=3&page[size]=50`

Meta information regarding pagination is found at the bottom of every response.


