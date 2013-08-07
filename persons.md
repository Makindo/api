Persons
=======

The `persons` resource is a person in our database.
This resource is intended to be a canonical and possible list of personal details.


GET /persons
------------

This endpoint is used for gathering the persons we have for your account.
This endpoint returns the list of 25 persons, ordered by internal ID.

  - **Authenticated?** Yes
  - **Response?** Yes


**Parameters**:

  - `:offset`: The number of rows you want to skip
  - `:limit`: The amount of results you want to return, maximum 100
  - `:start`: The lowest id you want the results to return
  - `:order`: By what attribute you want users ordered (default: id)


**Statuses**:

  - `200`: Everything went OK and records were returned.
  - `401`: Client's API key was either missing or incorrect.
  - `500`: The server is having problems.


**Example**

    curl -X GET "http://api.makindo.io/persons?limit=10&offset=5" \
      -H 'Authorization: Token token="dde10d87-d68c-466f-8532-98726a737ed7"' \
      -H 'Content-Type: application/json' \
      -H 'Accepts: application/json' | python -mjson.tool


**Response**:

``` json
{
    "meta": {
        "link": "http://api.makindo.io/persons?limit=10&offset=5&order=id&start=1",
        "next": "http://api.makindo.io/persons?limit=10&offset=15&order=id&start=1",
        "prev": "http://api.makindo.io/persons?limit=10&offset=-5&order=id&start=1"
    },
    "persons": [
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 24,
            "location": {
                "city": null,
                "country": "United States",
                "state": "MD"
            },
            "locations": [
                {
                    "city": null,
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "MD",
                    "zip": null
                }
            ],
            "name": "Chris Webb",
            "names": [
                {
                    "family": "Webb",
                    "personal": "Chris"
                },
                {
                    "family": null,
                    "personal": "Christian"
                },
                {
                    "family": null,
                    "personal": "Christopher"
                },
                {
                    "family": null,
                    "personal": "Christiana"
                },
                {
                    "family": null,
                    "personal": "Christina"
                },
                {
                    "family": null,
                    "personal": "Christine"
                },
                {
                    "family": null,
                    "personal": "Kristine"
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 25,
            "location": {
                "city": "Dallas ",
                "country": "United States",
                "state": null
            },
            "locations": [],
            "name": "Morgan Kimmerle",
            "names": [
                {
                    "family": "Kimmerle",
                    "personal": "Morgan"
                },
                {
                    "family": "Kimmerly",
                    "personal": null
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 26,
            "location": {
                "city": null,
                "country": null,
                "state": null
            },
            "locations": [
                {
                    "city": "Atlanta",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "GA",
                    "zip": null
                }
            ],
            "name": null,
            "names": [
                {
                    "family": "Paulson",
                    "personal": "Stratton"
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 29,
            "location": {
                "city": null,
                "country": null,
                "state": null
            },
            "locations": [
                {
                    "city": "Eldridge",
                    "country": "United States",
                    "latitude": -87.671745300293,
                    "longitude": 33.9098625183105,
                    "state": "AL",
                    "zip": null
                },
                {
                    "city": "University",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "MS",
                    "zip": null
                },
                {
                    "city": "Oxford",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "MS",
                    "zip": null
                },
                {
                    "city": "Wilsonville",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "AL",
                    "zip": null
                },
                {
                    "city": "Birmingham",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "AL",
                    "zip": null
                },
                {
                    "city": "Carbon Hill",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "AL",
                    "zip": null
                },
                {
                    "city": "Vaughan",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "MS",
                    "zip": null
                },
                {
                    "city": "Westover",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "AL",
                    "zip": null
                },
                {
                    "city": "Mandeville",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "LA",
                    "zip": null
                },
                {
                    "city": "Batesville",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "MS",
                    "zip": null
                }
            ],
            "name": null,
            "names": [
                {
                    "family": "Thurman",
                    "personal": "Jenn"
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 53,
            "location": {
                "city": null,
                "country": "United States",
                "state": "UT"
            },
            "locations": [],
            "name": "Tori Barkman",
            "names": [
                {
                    "family": "Barkman",
                    "personal": "Tori"
                },
                {
                    "family": "Bergman",
                    "personal": null
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 0,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 54,
            "location": {
                "city": null,
                "country": null,
                "state": null
            },
            "locations": [],
            "name": "Jordann",
            "names": [
                {
                    "family": null,
                    "personal": "Jordann"
                },
                {
                    "family": null,
                    "personal": "Jordan"
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": 17,
                "minimum": 17
            },
            "confidence": 5,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 56,
            "location": {
                "city": null,
                "country": "United States",
                "state": null
            },
            "locations": [
                {
                    "city": "Richtersveld",
                    "country": "South Africa",
                    "latitude": null,
                    "longitude": null,
                    "state": "Northern Cape",
                    "zip": null
                }
            ],
            "name": "Natalie Brady",
            "names": [
                {
                    "family": null,
                    "personal": "Nat"
                },
                {
                    "family": null,
                    "personal": "Nathaniel"
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 57,
            "location": {
                "city": null,
                "country": null,
                "state": null
            },
            "locations": [
                {
                    "city": "Fresno",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "CA",
                    "zip": null
                }
            ],
            "name": null,
            "names": [
                {
                    "family": null,
                    "personal": "Kristine"
                },
                {
                    "family": "Hernandez",
                    "personal": "Chris"
                },
                {
                    "family": null,
                    "personal": "Christian"
                },
                {
                    "family": null,
                    "personal": "Christopher"
                },
                {
                    "family": null,
                    "personal": "Christiana"
                },
                {
                    "family": null,
                    "personal": "Christina"
                },
                {
                    "family": null,
                    "personal": "Christine"
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 59,
            "location": {
                "city": null,
                "country": "United States",
                "state": null
            },
            "locations": [],
            "name": "Rachel Smith",
            "names": [
                {
                    "family": null,
                    "personal": "Rachelsmith"
                }
            ],
            "status": 1
        },
        {
            "age": {
                "maximum": null,
                "minimum": null
            },
            "confidence": 2,
            "external_id": null,
            "gender": null,
            "genders": [],
            "id": 62,
            "location": {
                "city": null,
                "country": null,
                "state": null
            },
            "locations": [
                {
                    "city": "Lakewood",
                    "country": "United States",
                    "latitude": null,
                    "longitude": null,
                    "state": "OH",
                    "zip": null
                }
            ],
            "name": null,
            "names": [
                {
                    "family": "Gilbert",
                    "personal": "Bubba"
                }
            ],
            "status": 1
        }
    ]
}
```


GET /persons/{{id}}
-------------------

This endpoint is used to query an individual person.

  - **Authenticated?** Yes
  - **Response?** Yes


**Example**

    curl -X GET "http://api.makindo.io/persons/6" \
      -H 'Authorization: Token token="dde10d87-d68c-466f-8532-98726a737ed7"' \
      -H 'Content-Type: application/json' \
      -H 'Accepts: application/json' | python -mjson.tool


**Response**

``` json
{
    "meta": {
        "link": "http://api.makindo.io/persons/6"
    },
    "person": {
        "age": {
            "maximum": null,
            "minimum": null
        },
        "confidence": 3,
        "external_id": null,
        "gender": null,
        "genders": [],
        "id": 6,
        "location": {
            "city": null,
            "country": null,
            "state": null
        },
        "locations": [
            {
                "city": "Columbus",
                "country": "United States",
                "latitude": null,
                "longitude": null,
                "state": "OH",
                "zip": null
            },
            {
                "city": "Decatur",
                "country": "United States",
                "latitude": null,
                "longitude": null,
                "state": "GA",
                "zip": null
            }
        ],
        "name": null,
        "names": [
            {
                "family": "Coleman",
                "personal": "Diane"
            },
            {
                "family": null,
                "personal": "Diana"
            }
        ],
        "status": 1
    }
}
```


**Statuses**:

  - `200`: Everything went OK and record returned
  - `401`: Client's API key was either missing or incorrect.
  - `500`: The server is having problems.


PATCH /persons/{{id}}
---------------------

This endpoint is used for the client to tell us if they've found a person in their personal database.

  - **Authenticated?** Yes
  - **Response?** Yes


**Parameters**:

  - `status` (string): Used to let us know the result of your search for the Person. Possible values:
    * `"found"`
    * `"ambiguous"`
    * `"missing"`
    * `"failed"`
  - `name` (string): The name you believe to be the Person's real name.
  - `gender` (string): The gender you believe to be how the Person identifies. Possible values:
    * `"female"`
    * `"male"`
    * `"other"`
  - `location` (object)
    - `city` (string): A full city name.
    - `state` (string): The abbreviated state/province name.
    - `country` (string): A full country name.
    - `latitude` (string): A float, represented as a string.
    - `longitude` (string): A float, represented as a string.
  - `age` (object)
    - `minimum` (integer): The minimum age of the Person.
    - `maximum` (integer): The maximum age of the Person
  - `external_id` (string): Your internal ID for this Person.


**Example**:

    curl -X PATCH "http://api.makindo.io/persons/6" \
      -H 'Authorization: Token token="dde10d87-d68c-466f-8532-98726a737ed7"' \
      -H 'Content-Type: application/json' \
      -H 'Accepts: application/json' \
      -d '{
            "person": {
                "location": {
                    "city": "Los Angeles",
                    "country": "United States",
                    "zip": "90017",
                    "state": "CA"
                },
                "gender": "male",
                "age": {
                    "maximum": 22,
                    "minimum": 25
                },
                "external_id": "543",
                "name": "Diane Coleman"
            }
        }' \
      | python -mjson.tool


**Response**

``` json
{
    "meta": {
        "link": "http://api.makindo.io/persons/6"
    },
    "person": {
        "age": {
            "maximum": 22,
            "minimum": 25
        },
        "confidence": 3,
        "external_id": "543",
        "gender": 0,
        "genders": [],
        "id": 6,
        "location": {
            "city": "Los Angeles",
            "country": "United States",
            "state": "CA"
        },
        "locations": [
            {
                "city": "Columbus",
                "country": "United States",
                "latitude": null,
                "longitude": null,
                "state": "OH",
                "zip": null
            },
            {
                "city": "Decatur",
                "country": "United States",
                "latitude": null,
                "longitude": null,
                "state": "GA",
                "zip": null
            }
        ],
        "name": "Diane Coleman",
        "names": [
            {
                "family": "Coleman",
                "personal": "Diane"
            },
            {
                "family": null,
                "personal": "Diana"
            }
        ],
        "status": 1
    }
}
```

**Statuses**:

  - `200`: Everything went OK and record was successfully updated and returned.
  - `400`: The request was improperly formed or not understood.
  - `401`: Client's API key was either missing or incorrect.
  - `409`: The body of the request was malformed.
  - `422`: There was something wrong with the record. **NOTE:** Response body contains errors
  - `500`: The server is having problems.
