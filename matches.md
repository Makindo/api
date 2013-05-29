Matches
=======

The `matches` resource is a combination of a `person` and a `survey`.
The resource is intended to detail how a `person` in our system answered questions in a `survey`.

GET /matches
------------

This endpoint returns the list of 10 matches, ordered by internal ID.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `:offset`: The last ID you want the next 10 matches to be after.

**Statuses**:

  - `200`: Everything went OK and records were returned.
  - `401`: Client's API key was either missing or incorrect.
  - `500`: The server is having problems.

**Response**:

``` json
{
  "meta" : {
    "next" : "http://api.makindo.io/matches?offset=10",
    "link" : "http://api.makindo.io/matches?offset=0",
    "prev" : null
  },
  "matches" : [
    {
      "match" : {
        "status" : "new",
        "person" : {
          "location" : {
            "city" : "Columbus",
            "country" : "United States",
            "state" : "OH"
          },
          "locations": [
            {
              "country": "United States",
              "state": "OH"
            }
          ]
          "age" : {
            "maximum" : 25,
            "minimum" : 20
          },
          "name" : "James Kirk",
          "names": [
            {
              "family": "Kirk",
              "personal": "James"
            }
          ],
          "aliases": [
            "Jim",
            "Jimbo"
          ]
        },
        "survey" : {
          "questions" : [
            {
              "answer" : "Yes.",
              "name" : "Q1"
            },
            {
              "answer" : "Somewhat likely.",
              "name" : "Q2"
            }
          ],
          "name" : "Joint script (#3)"
        },
        "id" : 1,
        "meta" : {
          "link" : "http://api.makindo.io/matches/1"
        }
      }
    }
  ]
}
```

PUT /matches/{id}
------------------

This endpoint is for the client to update our record based on their result.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `status` (string): The state of the match in the client's system. Possible values:
    * `found`
    * `ambiguous`
    * `missing`
    * `failed`

**Example**:

    PUT http://api.makindo.io/matches/5989 
    {"status":"found"}


**Statuses**:

  - `200`: Everything went OK and record was successfully updated and returned.
  - `401`: Client's API key was either missing or incorrect.
  - `409`: The body of the request was malformed.
  - `422`: There was something wrong with the record. **NOTE:** Response body contains errors
  - `500`: The server is having problems.
