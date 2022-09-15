# HTTP Status Codes

Here are the most frequently encountered error status codes, and the common causes:

Error Code | Message | Meaning
---------- | ------- | ------
`400` | `Your request has been rejected`                                              | Usually caused by a request made without HTTPS
`400` | `You must provide both a email and password, and integration key to continue` | Triggered by a missing email, password, API Key or Integration key
`401` | Various                                                             | Your authentication was not correct, usually due to an invalid API Key, email, etc.
`403` | `You have reached the maximum number of integrations allowed for this form`   | Forms can only have a maximum of 10 integrations (Webhook, MailChimp, etc.)
`403` | `You are not permitted to {action} this {resource} ask your administrator for rights to this` | The user tied to your API Key doesn't have view/edit permissions for the form/report you're trying to access
`404` | `Invalid identifier`                                                          | Request made for an invalid form/report identifier
`404` | `Not Found`                                                                   | Normally caused by a malformed request URL
`409` | `Multiple accounts exist for this email address. Please specify a subdomain in a subsequent call`      | No subdomain included in Login request
`420` | `Too many login attempts. You are only allowed 6 failed attempts. Account temporarily frozen`          | Too many failed Login requests
`421` | `You have exceeded your daily API usage`                             | You have exceeded the request limit for your plan in the last 24 hours
`429` | `Slow Down`                                                          | You have exceeded the API Rate Limit. Try again in a few minutes.
`500` | Various                                                           | Server error. Send our support team the request you used, and we can take a closer look