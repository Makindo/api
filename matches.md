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

  - `:offset`: The `id` you want to start with for this page.
    **Note**: If you specify an ID that doesn't exist, or wont be shown, it'll start from the next available ID.


**Statuses**:

  - `200`: Everything went OK and records were returned.
  - `401`: Client's API key was either missing or incorrect.
  - `500`: The server is having problems.


**Example**

    curl -X GET http://api.makindo.io/matches

**Response**:

``` json
{
    "meta": {
        "next": "http://api.makindo.io/matches?offset=100",
        "link": "http://api.makindo.io/matches?offset=90",
        "prev": null
    },
    "matches": [
        {
            "match": {
                "person": {
                    "meta": {
                      "link": "http://api.makindo.io/persons/23123"
                    },
                    "external_id": "12359342394"
                },
                "survey": {
                    "name": "Joint script (#3)",
                    "questions": [
                        {
                            "answer": "Yes.",
                            "name": "Q1"
                        },
                        {
                            "answer": "Somewhat likely.",
                            "name": "Q2"
                        }
                    ]
                },
                "id": 1,
                "meta": {
                    "link": "http://api.makindo.io/matches/1"
                }
            }
        }
    ]
}
```
