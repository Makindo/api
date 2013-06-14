Makindo API
===========


Resources
---------

  - [Matches](/matches.md)
  - [Persons](/persons.md)


Request Headers
----------------

In order to authenticate the client with the Makindo servers each client needs to send the following headers over:

  - `Authorization: Token token="api_secret"`
  - `Accept: application/json` or for previous versions of the API `Accept: application/vnd.makindo-v2+json`
  - `Content-Type: application/json`


Changelog
---------

**2.0.0**

  - The `/persons` endpoint is now available.
  - Match objects no longer have a `status` field. It has been moved, and all of it's behavior and logic to Person object.
  - Instead of updating a match to be "found" or "missing" you'll do this to a Person object.
  - The `/matches` endpoint no longer has a `PUT /matches/{{id}}`.
  - The Match object will no longer contain all Person object data, and instead have a link and external id
  - Person object now contains an external_id field that you can update with your own internal id for later reference.


**1.0.0**

  - Initial release
