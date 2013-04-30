Matches
=======

The `matches` resource is a combination of a `person` and a `survey`.
The resource is intended to detail how a `person` in our system answered questions in a `survey`.

GET /matches
------------

This endpoint returns the list of 100 matches, ordered by internal ID.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `:offset`: The last ID you want the next 100 matches to be after.

**Statuses**:

  - `200`: Everything went OK and record was successfully updated.
  - `401`: Client's API key was either missing or incorrect.
  - `500`: The server is having problems.

**Response**:

``` json
{
  "_prev": "https://api.makindo.io/matches?offset=300",
  "_link": "https://api.makindo.io/matches?offset=400",
  "_next": "https://api.makindo.io/matches?offset=500",
  "matches": [
    {
      “_link”: “https://api.makindo.io/matches/400”,
      "id" : "112",
      "status" : "new",
      "person" : {
        "name" : "John Smith", 
        "location" : {
          “city”: “Seattle”,
          “state”: “WA”,
          “country”: “US”
        },
        "age": { 
          "minimum": 40, 
          "maximum": 50
        } 
      },
      "survey" : {
        "name" : "tiguan",
        “questions”: [
          4,
          nil,
          2,
          4
        ]
      }
    }
  ]
}
```

PATCH /matches/:id 
------------------

This endpoint is for the client to update our record based on their result.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `:id`: The specific Makindo ID for the match record you're attempting to update.
  - `:status`: The state of the match in the client's system.

**Statuses**:

  - `200`: Everything went OK and record was successfully updated.
  - `401`: Client's API key was either missing or incorrect.
  - `409`: The body of the request was malformed.
  - `422`: There was something wrong with the record. **NOTE:** Response body contains errors
  - `500`: The server is having problems.
