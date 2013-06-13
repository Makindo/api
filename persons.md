Persons
=======

The `persons` resource is a person in our database.
This resource is intended to be a canonical and possible list of personal details.

GET /persons
------------

This endpoint is used for gathering the persons we have for your account.
This endpoint returns the list of 10 persons, ordered by internal ID.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `:offset`: The `id` you want to start with for this page.

**Statuses**:

  - `200`: Everything went OK and records were returned.
  - `401`: Client's API key was either missing or incorrect.
  - `500`: The server is having problems.

**Response**:

``` json

```

PATCH /persons/{{id}}
---------------------

This endpoint is used for the client to tell is if they've found a person in their personal database.

  - **Authenticated?** Yes
  - **Response?** Yes

**Parameters**:

  - `status` (string): The state of the match in the client's system. Possible values:
    * `found`
    * `ambiguous`
    * `missing`
    * `failed`

**Example**:

    curl
      -x PATCH http://api.makindo.io/persons/5989
      -b "{'status': 'found'}


**Statuses**:

  - `200`: Everything went OK and record was successfully updated and returned.
  - `401`: Client's API key was either missing or incorrect.
  - `409`: The body of the request was malformed.
  - `422`: There was something wrong with the record. **NOTE:** Response body contains errors
  - `500`: The server is having problems.
