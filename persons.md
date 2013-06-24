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

  - `:offset`: The `id` you want to start with for this page.


**Statuses**:

  - `200`: Everything went OK and records were returned.
  - `401`: Client's API key was either missing or incorrect.
  - `500`: The server is having problems.


**Example**

    curl -X GET http://api.makindo.io/persons


**Response**:

The `names` and `locations` are arrays of possible alternate name and location data.

``` json
{
    "meta": {
        "link": "http://api.makindo.io/persons?offset=200", 
        "next": "http://api.makindo.io/persons?offset=300", 
        "prev": "http://api.makindo.io/persons?offset=100"
    }, 
    "persons": [
        {
            "age": {
                "maximum": 36, 
                "minimum": 55
            }, 
            "id": 3355, 
            "location": {
                "city": "Louisville", 
                "country": "United States", 
                "state": "KY"
            }, 
            "locations": [
                {
                    "city": "Sand Springs", 
                    "country": "United States", 
                    "state": "OK", 
                    "zip": null
                }, 
                {
                    "city": "Tulsa", 
                    "country": "United States", 
                    "state": "OK", 
                    "zip": null
                }, 
            "name": "Diane Coleman", 
            "names": [
                {
                    "family": null, 
                    "personal": "Diana"
                }, 
                {
                    "family": "Coleman", 
                    "personal": "Diane"
                }
            ]


        }, 
        ...            
                    
```


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
    - `state` (string): A full state name.
    - `country` (string): A full country name.
    - `latitude` (string): A float, represented as a string.
    - `longitude` (string): A float, represented as a string.
  - `age` (object)
    - `minimum` (integer): The minimum age of the Person.
    - `maximum` (integer): The maximum age of the Person
  - `external_id` (string): Your internal ID for this Person.


**Example**:

    curl
      -x PATCH http://api.makindo.io/persons/5989
      -b "{'status': 'found'}


**Response**

The updated JSON object for the person is returned.


**Statuses**:

  - `200`: Everything went OK and record was successfully updated and returned.
  - `400`: The request was improperly formed or not understood.
  - `401`: Client's API key was either missing or incorrect.
  - `409`: The body of the request was malformed.
  - `422`: There was something wrong with the record. **NOTE:** Response body contains errors
  - `500`: The server is having problems.
