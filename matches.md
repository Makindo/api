Matches
=======

The `matches` resource is a combination of a `person` and a `survey`.
The resource is intended to detail how a `person` in our system answered questions in a `survey`.

GET /matches
------------

This endpoint returns the list of 25 matches, ordered by internal ID.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `:offset`: The last ID you want the next 25 matches to be after.

**Statuses**:

  - `200`: Everything went OK and records were returned.
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
            "_link": "https: //api.makindo.io/matches/400",
            "id": "112",
            "status": "new",
            "person": {
                "name": "John Smith",
                "location": {
                    "city": "Seattle",
                    "state": "WA",
                    "country": "US"
                },
                "age": {
                    "minimum": 40,
                    "maximum": 50
                }
            },
            "survey": {
                "name": "tiguan",
                "questions": [
                    {
                        "body": "Do you like vehicles?",
                        "answer": "Yes"
                    },
                    {
                        "body": "Do you like airplanes?",
                        "answer": "No"
                    }
                ]
            }
        }
    ]
}
```

PUTS /matches/{id}
------------------

This endpoint is for the client to update our record based on their result.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `status` (string): The state of the match in the client's system. Possible values:
    * `found`
    * `ambiguous`
    * `missing`

**Example**:

    https://api.makindo.io/matches/5989?status=found

**Statuses**:

  - `200`: Everything went OK and record was successfully updated.
  - `401`: Client's API key was either missing or incorrect.
  - `409`: The body of the request was malformed.
  - `422`: There was something wrong with the record. **NOTE:** Response body contains errors
  - `500`: The server is having problems.
