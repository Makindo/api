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
          "id" : 6,
          "age" : {
            "maximum" : "?",
            "minimum" : "?"
          },
          "name" : "Diane Shaw Coleman"
        },
        "survey" : {
          "id" : 3,
          "questions" : [
            {
              "answer" : "yes",
              "body" : "Q1:\tAre you a licensed driver? Please press one if you are a licensed driver and press two if you are not."
            },
            {
              "answer" : "Somewhat likely",
              "body" : "How likely is it that you will be in the market to purchase or lease a car in the next year?  Press one if it is very likely, press two if it is somewhat likely, press three if it is somewhat unlikely and press four if it is very unlikely.    "
            }
          ],
          "name" : "Joint script  (#3)"
        },
        "id" : 1,
        "meta" : {
          "link" : "http://api.makindo.io/matches/1"
        }
      }
    },
    {
      "match" : {
        "status" : "new",
        "person" : {
          "location" : {
            "city" : "Eastern",
            "country" : "United States",
            "state" : "KY"
          },
          "id" : 38,
          "age" : {
            "maximum" : "?",
            "minimum" : "?"
          },
          "name" : "Priscilla Geer"
        },
        "survey" : {
          "id" : 3,
          "questions" : [
            {
              "answer" : "yes",
              "body" : "Q1:\tAre you a licensed driver? Please press one if you are a licensed driver and press two if you are not."
            },
            {
              "answer" : "01\tVery likely",
              "body" : "How likely is it that you will be in the market to purchase or lease a car in the next year?  Press one if it is very likely, press two if it is somewhat likely, press three if it is somewhat unlikely and press four if it is very unlikely.    "
            },
            {
              "answer" : "4-door sedan",
              "body" : "What kind of vehicle are you considering?  Please press one if it is a 2-door coupe, press two if it is a 2-door sports car, press three if it is a 4-door sedan, press four if it is a 4-door performance sedan, press five if it is a compact SUV, press six if it is a full size SUV, press seven if it is a minivan or van, press 8 if it is a pick-up truck."
            },
            {
              "answer" : "20K-30K",
              "body" : "Thinking about how much would you consider paying for your next new car, press one if it is under $20,000, press two if it is $20,000 up to $30,000, press 3 if it is $30,000 up to $40,000, press four if it is $40,000 up to $70,000, press five if it is $70,000 up to $100,000 and press six if it is more than $100,000."
            }
          ],
          "name" : "Joint script  (#3)"
        },
        "id" : 2,
        "meta" : {
          "link" : "http://api.makindo.io/matches/2"
        }
      }
    },
  
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

**Example**:

    PUT http://api.makindo.io/matches/5989 
    {"status":"found"}


**Statuses**:

  - `200`: Everything went OK and record was successfully updated and returned.
  - `401`: Client's API key was either missing or incorrect.
  - `409`: The body of the request was malformed.
  - `422`: There was something wrong with the record. **NOTE:** Response body contains errors
  - `500`: The server is having problems.
