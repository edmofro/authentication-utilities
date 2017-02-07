# authentication-utilities

Exports three utility functions that carry out common authentication tasks

### authenticateAsync(URL, username, password)
Checks whether a username and password authenticate against a given URL. 
Does this by querying the URL endpoint with a Basic auth header attached to the HTTP GET query.
Will return the response from the server interpreted as JSON, or throw an error if anything goes wrong.
Errors can be:
* Generated by the function - missing credentials, invalid URL, connection failure.
* Generated by the server - invalid username/password, permission denied, etc.
Errors generated by the server should be returned as JSON under the 'error' key.

### getAuthHeader(username, password)
Returns a Basic auth header with the given username and password in a Base64 encoded string

### hashPassword(password)
Encodes a given password using sha256, producing a non-reversible hash