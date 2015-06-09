# HTTP Status Codes

The Wufoo API uses the following status codes:

Error Code | Message | Meaning
---------- | ------- | ------
400 | You must provide both a email and password, and integration key to continue. | Missing email, password, API Key or Integration key
401 | Unauthorized -- Your API key is wrong
403 | Forbidden 
404 | Not Found 
405 | Method Not Allowed 
406 | Not Acceptable 
409 | Multiple accounts exist for this email address. Please specify a subdomain in a subsequent call. | No subdomain included in Login request
420 | Too many login attempts. You are only allowed 6 failed attempts. Account temporarily frozen. | Too many failed Login requests
429 | Too Many Requests 
500 | Internal Server Error 
503 | Service Unavailable 
