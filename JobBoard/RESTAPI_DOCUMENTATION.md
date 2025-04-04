## API Documentation

### Public API

All API routes requre the header value `x-api-key` to be set to the user's api key.

#### Getting Applications

`/api/application/get`

Method: `GET`

Params:
- id (optional if not provided fetches all jobs for your company)

```
curl --request GET \
  --url 'https://jbapi.hstoday.us/api/application/get' \
  --header 'x-api-key: <apikey>'
```

#### Getting Job Listings

`/api/job/listings`

Method: `GET`

Params:
- id (optional if not provided fetches all jobs for your company)

Curl Example

```
curl --request GET \
  --url 'https://jbapi.hstoday.us/api/job/listings' \
  --header 'x-api-key: <apikey>'
```

#### Deleting a Job

`/api/job/delete`

Method: `DELETE`

Params:
- id

Curl Example

```
curl --request DELETE \
  --url 'https://jbapi.hstoday.us/api/job/delete?id=<id>' \
  --header 'x-api-key: <apikey>'
```

#### Posting a New Job

`/api/job/post`

Method: `POST`

Body content: XML or JSON

Header:
- Content type for XML or JSON

Curl Example

```
curl --request POST \
  --url 'https://jbapi.hstoday.us/api/job/post' \
  --header 'Content-Type: application/json' \
  --header 'User-Agent: insomnia/10.3.1' \
  --header 'x-api-key: <apikey>' \
  --data '{
    "request": {
        "jobs": {
            "job": {
                "title": "Example Job Title 7-11",
                "description": "An example job title",
                "expires": "2025-03-14",
                "active": "1",
                "filled": "0",
                "location": {
                    "country": "840",
                    "state": "New York",
                    "zip_code": "10001",
                    "city": "New York",
                    "address": "20 W 34th St.L"
                },
                "category": "Business"
            }
        }
    }
}'
```