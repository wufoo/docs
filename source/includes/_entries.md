# Entries

## Form Entries

```shell
curl -u "AOI6-LFKL-VM1Q-IEX9":"footastic" "https://fishbowl.wufoo.com/api/v3/forms/wufoo-api-example/entries.json?sort=EntryId&sortDirection=DESC"
```

```python
import urllib2
import json

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

password_manager = urllib2.HTTPPasswordMgrWithDefaultRealm()
password_manager.add_password(None, base_url, username, password)
handler = urllib2.HTTPBasicAuthHandler(password_manager)
opener = urllib2.build_opener(handler)

urllib2.install_opener(opener)

response = urllib2.urlopen(base_url+'forms/s1afea8b1vk0jf7/entries.json?sort=EntryId&sortDirection=DESC')
data = json.load(response)
print json.dumps(data, indent=4, sort_keys=True)
```

```ruby
require "net/http"
require "uri"
require "json"

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

uri = URI.parse(base_url+"forms/s1afea8b1vk0jf7/entries.json?sort=EntryId&sortDirection=DESC")

request = Net::HTTP::Get.new(uri.request_uri)
request.basic_auth(username, password)

response = Net::HTTP.start(uri.hostname, uri.port, :use_ssl => uri.scheme == 'https') {|http|
  http.request(request)
}

puts JSON.pretty_generate(JSON[response.body])
```

```javascript
var request = require("request");

request({
  uri: "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json?sort=EntryId&sortDirection=DESC",
  method: "GET",
  auth: {
    'username': 'AOI6-LFKL-VM1Q-IEX9',
    'password': 'footastic',
    'sendImmediately': false
  }
}, function(error, response, body) {
  console.log(body);
});

```

```php
<?php
$curl = curl_init('https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json?sort=EntryId&sortDirection=DESC');
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERPWD, 'AOI6-LFKL-VM1Q-IEX9:footastic');
curl_setopt($curl, CURLOPT_HTTPAUTH, CURLAUTH_ANY);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, true);                          
curl_setopt($curl, CURLOPT_FOLLOWLOCATION, true);                           
curl_setopt($curl, CURLOPT_USERAGENT, 'Wufoo Sample Code');

$response = curl_exec($curl);
$resultStatus = curl_getinfo($curl);

if($resultStatus['http_code'] == 200) {
    $json = json_decode($response);
    echo json_encode($json, JSON_PRETTY_PRINT);
} else {
    echo 'Call Failed '.print_r($resultStatus);
}
```

> The above request produces output in this format:

```json
{
  "Entries" : [
    {
      "EntryId" : "9",
      "Field105" : "Some Text",
      "Field106" : "123",
      "Field107" : "Here is a Paragraph field. It can hold more text than a regular Single Line Text field. \r\nThis is a second line of text in the same field.",
      "Field108" : "Check One",
      "Field109" : "Check Two",
      "Field110" : "Check Three",
      "Field208" : "MC Two",
      "Field209" : "Dropdown Three",
      "Field1" : "Wufoo",
      "Field2" : "Test",
      "Field210" : "test.txt (https://fishbowl.wufoo.com/cabinet/s1afea8b1vk0jf7/gTVeAerMQyk%3D/test.txt)",
      "Field211" : "123 Street",
      "Field212" : "",
      "Field213" : "City",
      "Field214" : "CA",
      "Field215" : "12445",
      "Field216" : "United States",
      "Field217" : "2015-04-20",
      "Field218" : "test@wufoo.com",
      "Field219" : "00:34:56",
      "Field220" : "1231231234",
      "Field221" : "http://www.wufoo.com",
      "Field222" : "100.99",
      "Field4" : "Strongly Agree",
      "Field5" : "Agree",
      "Field6" : "Strongly Agree",
      "Field223" : "5",
      "DateCreated" : "2015-04-20 15:50:34",
      "CreatedBy" : "public",
      "DateUpdated" : "",
      "UpdatedBy" : null
    },
...
    {
      "EntryId" : "2",
      "Field105" : "",
      "Field106" : "",
      "Field107" : "",
      "Field108" : "",
      "Field109" : "",
      "Field110" : "",
      "Field208" : "",
      "Field209" : "",
      "Field1" : "Amber",
      "Field2" : "Des",
      "Field210" : "",
      "Field211" : "",
      "Field212" : "",
      "Field213" : "",
      "Field214" : "",
      "Field215" : "",
      "Field216" : "",
      "Field217" : "",
      "Field218" : "",
      "Field219" : "",
      "Field220" : "",
      "Field221" : "",
      "Field222" : null,
      "Field4" : "Agree",
      "Field5" : "Agree",
      "Field6" : "Disagree",
      "Field223" : "",
      "DateCreated" : "2008-11-24 09:46:04",
      "CreatedBy" : "public",
      "DateUpdated" : "",
      "UpdatedBy" : null
    },
    {
      "EntryId" : "1",
      "Field105" : "",
      "Field106" : "",
      "Field107" : "",
      "Field108" : "",
      "Field109" : "",
      "Field110" : "",
      "Field208" : "",
      "Field209" : "",
      "Field1" : "Tim",
      "Field2" : "Sabat",
      "Field210" : "",
      "Field211" : "",
      "Field212" : "",
      "Field213" : "",
      "Field214" : "",
      "Field215" : "",
      "Field216" : "",
      "Field217" : "",
      "Field218" : "",
      "Field219" : "",
      "Field220" : "",
      "Field221" : "",
      "Field222" : null,
      "Field4" : "Strongly Agree",
      "Field5" : "Strongly Agree",
      "Field6" : "Agree",
      "Field223" : "",
      "DateCreated" : "2008-11-24 09:45:28",
      "CreatedBy" : "public",
      "DateUpdated" : "",
      "UpdatedBy" : null
    }
  ]
}
```

This request returns the entries that have been submitted to a specific form. This is the equivalent of viewing your stored entries in the Entry Manager in Wufoo.

<aside class="notice">To identify the desired form, use the form hash or the form title, just like the Form request. </aside>

### HTTP Request

`GET http://{subdomain}.wufoo.com/api/v3/forms/{identifier}/entries.{format}`


### URL Parameters

Parameter | Description
--------- | -----------
subdomain | Your account subdomain/username.
format    | Either 'json' or 'xml' is required. This will determine response format
identifier| The title or hash of the form to retrieve

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
system    | false   | If set to true, includes additional metadata fields
pretty    | false   | If set to true, returns the result in a "pretty print" format
pageStart | 0       | The entry that the request will start from
pageSize  | 25      | The number of entries returned in the request (Maximum of 100)

The various `Field##` properties correspond to the fields in the [Form Fields](#form-fields)

<aside class="warning">Data in fields that are marked as "Admin Only" are not returned via the API. Data from "hidden" and encrypted fields will be shown</aside>

<b>Every Entry in an Entries request contains five fields. The Default Fields are:</b>

Field | Description
|--------|--------|
EntryId | This value is the unique identifier for your entry.
DateCreated | The date that this entry was submitted. The date/time will be recorded in the timezone of the user making the request
Created By | The person who created the entry. If submitted through a form, the value here will be public. If the submission originated in the Entry Manager this value will be the user name of the submitting user.
DateUpdated | The date that this entry was edited through the Entry Manager. If the submission has never been updated, this value will be blank.
UpdatedBy | The user name of the person who updated the entry in the Entry Manager will appear in this element.

<b id='entries-system'>If you add the `system` query parameter, some additional metadata fields will be included. The System Fields are:</b>

Field | Description
|--------|--------|
IP | The IP Address of the user submitting the form.
LastPage | This represents the last page the user submitted.
CompleteSubmission | Represents either a completed (`1`) or incomplete/partial (`0`) entry.
Status | Indicates the payment status. An example is ‘Paid’. More info [here](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Entry-Manager#payment)
PurchaseTotal | The total amount charged for the transaction. This is the final total we send to the payment processor
Currency | The currency used. This is the currency value we send to the payment processor
TransactionId | The confirmation number sent back from the payment processor.
MerchantType | The name of the payment processor used. This is determined by which payment integration is set up. There is a full list [here](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Payment-Settings)

### Filtering

You can filter an Entries API request, similar to how the Wufoo [Entry Manager](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Entry-Manager#filter) works. Here's the format:

`Filter{##}={ID}+{Operator}+{Value}&match={Grouping}`

Parameter   | Description
----------- | -----------
Filter{##}  | {##} should just be a unique number to identify each filter (1, 2, 3, etc.)
{ID}        | The API Field ID for the field you want to use. These values are the same as the "ID" property in a [Fields](#form-fields) request
{Operator}  | The comparison that will be used with the filter. See full list below.
{Value}     | The value to match with your filter
{Grouping}  | Allows you group your filters as 'AND' (all must match) or 'OR' (at least one must match)

<aside class="notice">We do not adjust your input filter date/time, so all dates/times are interpreted as PST/PDT (UTC -8/-7)</aside>

Here's an example:

`https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json?Filter1=EntryId+Is_greater_than+1&Filter2=EntryId+Is_less_than+5&match=AND`

<aside class="notice">Multiple filters can be joined, using the `&` operator</aside>

<b>Valid Operators</b>

- Contains
- Does_not_contain
- Begins_with
- Ends_with
- Is_less_than
- Is_greater_than
- Is_on
- Is_before
- Is_after
- Is_not_equal_to
- Is_equal_to
- Is_not_NULL

To filter by a specific date/time, you can use the [MySQL DateTime format](http://dev.mysql.com/doc/refman/5.0/en/datetime.html). This would be written as "YYYY-MM-DD HH:MM:SS" For example:`2009-08-13 11:43:22`
<aside class="notice">Don't forget to encode things like spaces if you're making a request through the browser</aside>

These times can be entered in PST/PDT (UTC -8/-7)

### Sorting

Sorting can also be applied using additional query parameters in this format:

`sort={ID}&sortDirection={DESC|ASC}`

Parameter     | Default | Description
------------- | ------- | -----------
sort          | N/A     | The API Field ID for the field you want to use. These values are the same as the "ID" property in a [Fields](#form-fields) request
sortDirection | ASC     | The order to sort returned entries: ASC (lowest to highest) or DESC (highest to lowest)

The `sortDirection` parameter will only be applied if it is also used with a `sort` parameter. In other words, the `sortDirection` can only be applied to the sorting used with the `sort` value, not by itself.

Example:

`https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json?sort=EntryId&sortDirection=DESC`

### Paging

As mentioned [above](#form-entries), you can use the `pageStart` and `pageSize` parameters to change the number of entries returned in your request. For example:

`pageStart=5&pageSize=10`

would give you 10 entries, starting after the first 5. In other words, entries 6-15

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
pageStart | 0       | The entry that the request will start from
pageSize  | 25      | The number of entries returned in the request (Maximum of 100)

## Form Entries Count

```shell
curl -u "AOI6-LFKL-VM1Q-IEX9":"footastic" "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries/count.json"
```

```python
import urllib2
import json

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

password_manager = urllib2.HTTPPasswordMgrWithDefaultRealm()
password_manager.add_password(None, base_url, username, password)
handler = urllib2.HTTPBasicAuthHandler(password_manager)
opener = urllib2.build_opener(handler)

urllib2.install_opener(opener)

response = urllib2.urlopen(base_url+'forms/s1afea8b1vk0jf7/entries/count.json')
data = json.load(response)
print json.dumps(data, indent=4, sort_keys=True)
```

```ruby
require "net/http"
require "uri"
require "json"

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

uri = URI.parse(base_url+"forms/s1afea8b1vk0jf7/entries/count.json")

request = Net::HTTP::Get.new(uri.request_uri)
request.basic_auth(username, password)

response = Net::HTTP.start(uri.hostname, uri.port, :use_ssl => uri.scheme == 'https') {|http|
  http.request(request)
}

puts JSON.pretty_generate(JSON[response.body])
```

```javascript
var request = require("request");

request({
  uri: "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries/count.json",
  method: "GET",
  auth: {
    'username': 'AOI6-LFKL-VM1Q-IEX9',
    'password': 'footastic',
    'sendImmediately': false
  }
}, function(error, response, body) {
  console.log(body);
});

```

```php
<?php
$curl = curl_init('https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries/count.json');
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERPWD, 'AOI6-LFKL-VM1Q-IEX9:footastic');
curl_setopt($curl, CURLOPT_HTTPAUTH, CURLAUTH_ANY);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, true);                          
curl_setopt($curl, CURLOPT_FOLLOWLOCATION, true);                           
curl_setopt($curl, CURLOPT_USERAGENT, 'Wufoo Sample Code');

$response = curl_exec($curl);
$resultStatus = curl_getinfo($curl);

if($resultStatus['http_code'] == 200) {
    $json = json_decode($response);
    echo json_encode($json, JSON_PRETTY_PRINT);
} else {
    echo 'Call Failed '.print_r($resultStatus);
}
```

> The above request produces output in this format:

```json
{
  "EntryCount" : "8"
}
```

### HTTP Request

This request returns a count of the entries stored for a specific form. This can help with deciding on a [pageSize](#paging) for your Entries requests, or determining the number of elements you have to display. This request can also be used with [filters](#filtering), in which case the count will be all entries matching the filter.

`GET http://{subdomain}.wufoo.com/api/v3/forms/{identifier}/entries/count.{format}`

### URL Parameters

Parameter | Description
--------- | -----------
subdomain | Your account subdomain/username.
format    | Either 'json' or 'xml' is required. This will determine response format
identifier| The title or hash of the form to retrieve

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
pretty    | false   | If set to true, returns the result in a "pretty print" format

## Submit Entry

```shell
curl -X POST -d "Field1=Wufoo" -d "Field2=Test" -d "Field105=API-Test" -d "Field106=42" -u "AOI6-LFKL-VM1Q-IEX9":"footastic" "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json"
```

```python
import urllib
import urllib2
import json

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

password_manager = urllib2.HTTPPasswordMgrWithDefaultRealm()
password_manager.add_password(None, base_url, username, password)
handler = urllib2.HTTPBasicAuthHandler(password_manager)
opener = urllib2.build_opener(handler)

urllib2.install_opener(opener)

values = {
        'Field1' : 'Wufoo',
        'Field2' : 'Test',
        'Field105' : 'API-Test',
        'Field106' : '42'
}

post_data = urllib.urlencode(values)

response = urllib2.urlopen(base_url+'forms/s1afea8b1vk0jf7/entries.json', post_data)
data = json.load(response)
print json.dumps(data, indent=4, sort_keys=True)
```

```ruby
require "net/http"
require "uri"
require "json"

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

uri = URI.parse(base_url+"forms/s1afea8b1vk0jf7/entries.json")

request = Net::HTTP::Post.new(uri.request_uri)
request.basic_auth(username, password)

request.set_form_data('Field1' => 'Wufoo',
                      'Field2' => 'Test',
                      'Field105' => 'API-Test',
                      'Field106' => '42'
                      )

response = Net::HTTP.start(uri.hostname, uri.port, :use_ssl => uri.scheme == 'https') {|http|
  http.request(request)
}

puts JSON.pretty_generate(JSON[response.body])
```

```javascript
var request = require("request");

request({
    uri: "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json",
    method: "POST",
    auth: {
        'username': 'AOI6-LFKL-VM1Q-IEX9',
        'password': 'footastic',
        'sendImmediately': false
    },
    form: {
        'Field1' : 'Wufoo',
        'Field2' : 'Test',
        'Field105' : 'API-Test',
        'Field106' : '42'
    }
}, function(error, response, body) {
  console.log(body);
});
```

```php
<?php
$curl = curl_init('https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json');
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERPWD, 'AOI6-LFKL-VM1Q-IEX9:footastic');
curl_setopt($curl, CURLOPT_HTTPAUTH, CURLAUTH_ANY);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, true);                          
curl_setopt($curl, CURLOPT_FOLLOWLOCATION, true);                           
curl_setopt($curl, CURLOPT_USERAGENT, 'Wufoo Sample Code');

curl_setopt($curl, CURLOPT_POST, 1);
curl_setopt($curl, CURLOPT_POSTFIELDS, 'Field1=Wufoo&Field2=Test&Field105=API-Test&Field106=42');

$response = curl_exec($curl);
$resultStatus = curl_getinfo($curl);

if($resultStatus['http_code'] == 201) {
    $json = json_decode($response);
    echo json_encode($json, JSON_PRETTY_PRINT);
} else {
    echo 'Call Failed '.print_r($resultStatus);
}
```

> The above request will receive a response in this format:

```json
{
  "Success": 1,
  "EntryId": 10,
  "EntryLink": "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json?Filter1=EntryId+Is_equal_to+10",
  "RedirectUrl":"http://wufoo.com"
}
```

This request allows you to submit a new entry to a specific form.

### HTTP Request

`POST http://{subdomain}.wufoo.com/api/v3/forms/{identifier}/entries.{format}`

### URL Parameters

Parameter | Description
--------- | -----------
subdomain | Your account subdomain/username.
format    | Either 'json' or 'xml' is required. This will determine response format
identifier| The title or hash of the form to retrieve

### POST Parameters

To submit an entry to a form, you'll need to match the API ID values for each field in the form. You can find these values through a [Form Fields](#form-fields) request, or through your form's [API Information](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Templating#api) page.

The POST request should contain the data for the new entry submission in key/value pairs. The key will be the API ID in the format of `Field##`, where `##` is the API ID for the given field. The value will be your desired entry data, which will be recorded as if a user had submitted that value on the form manually.

Here's an example of what the key/value pairs might look like:

`{
    "Field1":   "Wufoo",
    "Field2":   "Test",
    "Field105": "API-Test",
    "Field106": "42"
 }`

<aside class="notice">To submit a date value, make sure to use the format YYYYMMDD</aside>

### Response
When you make the Entries POST, you'll receive a PostResponse object containing the following:

Property    | Description
---------   | -----------
Success     | Will be '1' if the submission was a success. If the submission [failed](#failed-submissions), it will be '0'
EntryId     | If the submission was a success, this value will be the EntryId assigned to this submission
EntryLink   | If the submission was a success, this value will be the URL for an [Entries](#form-entries) request, filtered for this entry
RedirectUrl | If the form has a [Redirect](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Form-Settings#confirmation) set up, that URL will be included in the response

### Failed Submissions

>This example shows the server response when the submit entry rate limit is exceeded

```json
{
    "Text":"Slow Down",
    "HTTPCode":429
}
```

#### Rate Limit

To prevent malicious bot activity and reduce strain on Wufoo services, entries submitted via the Wufoo v3 API are limited to 50 submissions per Wufoo User in a 5 minute sliding window. Entries which exceed this limit will receive a HTTP 429 response. For more information on this and other HTTP Status Codes see [here](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429).

>Note this POST request is missing a value for Field105 (a required Text field) and has a text value submitted for Field106 (a Number field)

```shell
curl -X POST -d "Field1=Wufoo" -d "Field2=Test" -d "Field106=test" -u "AOI6-LFKL-VM1Q-IEX9":"footastic" "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json"
```

```python
import urllib
import urllib2
import json

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

password_manager = urllib2.HTTPPasswordMgrWithDefaultRealm()
password_manager.add_password(None, base_url, username, password)
handler = urllib2.HTTPBasicAuthHandler(password_manager)
opener = urllib2.build_opener(handler)

urllib2.install_opener(opener)

values = {
        'Field1' : 'Wufoo',
        'Field2' : 'Test',
        'Field106' : 'Fail'
}

post_data = urllib.urlencode(values)

response = urllib2.urlopen(base_url+'forms/s1afea8b1vk0jf7/entries.json', post_data)
data = json.load(response)
print json.dumps(data, indent=4, sort_keys=True)
```

```ruby
require "net/http"
require "uri"
require "json"

base_url = 'https://fishbowl.wufoo.com/api/v3/'
username = 'AOI6-LFKL-VM1Q-IEX9'
password = 'footastic'

uri = URI.parse(base_url+"forms/s1afea8b1vk0jf7/entries.json")

request = Net::HTTP::Post.new(uri.request_uri)
request.basic_auth(username, password)

request.set_form_data('Field1' => 'Wufoo',
                      'Field2' => 'Test',
                      'Field106' => 'Fail'
                      )

response = Net::HTTP.start(uri.hostname, uri.port, :use_ssl => uri.scheme == 'https') {|http|
  http.request(request)
}

puts JSON.pretty_generate(JSON[response.body])
```

```javascript
var request = require("request");

request({
    uri: "https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json",
    method: "POST",
    auth: {
        'username': 'AOI6-LFKL-VM1Q-IEX9',
        'password': 'footastic',
        'sendImmediately': false
    },
    form: {
        'Field1' : 'Wufoo',
        'Field2' : 'Test',
        'Field106' : 'Fail'
}
}, function(error, response, body) {
  console.log(body);
});
```

```php
<?php
$curl = curl_init('https://fishbowl.wufoo.com/api/v3/forms/s1afea8b1vk0jf7/entries.json');
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERPWD, 'AOI6-LFKL-VM1Q-IEX9:footastic');
curl_setopt($curl, CURLOPT_HTTPAUTH, CURLAUTH_ANY);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, true);                          
curl_setopt($curl, CURLOPT_FOLLOWLOCATION, true);                           
curl_setopt($curl, CURLOPT_USERAGENT, 'Wufoo Sample Code');

curl_setopt($curl, CURLOPT_POST, 1);
curl_setopt($curl, CURLOPT_POSTFIELDS, 'Field1=Wufoo&Field2=Test&&Field106=Fail');

$response = curl_exec($curl);
$resultStatus = curl_getinfo($curl);

if($resultStatus['http_code'] == 200 || $resultStatus['http_code'] == 201) {
    $json = json_decode($response);
    echo json_encode($json, JSON_PRETTY_PRINT);
} else {
    echo 'Call Failed '.print_r($resultStatus);
}
```

>Here is the corresponding "failed" PostResponse

```json
{
    "RedirectUrl":"http://wufoo.com",
    "Success":0,
    "ErrorText":"Errors have been <b>highlighted<\/b> below.",
    "FieldErrors":[
        {
          "ID":"Field105",
          "ErrorText":"This field is required. Please enter a value."
        },
        {
          "ID":"Field106",
          "ErrorText":"Please enter a numeric value."
        }
    ]
}
```

#### Bad Request

An Entries POST can fail for a few different reasons. A submission through the API must still adhere to any [field validation](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Field-Settings) or [form activity limits](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Form-Settings#limit). If these are not respected, the PostResponse will return with a 'Success' value of '0'. In this case, the PostResponse will contain some alternate properties:

Property    | Description
---------   | -----------
Success     | Will be '0' if the submission failed.
ErrorText   | This is some general text related to the error. Equivalent to what would be shown to the user on the actual form
FieldErrors | This will be an array of ID and ErrorText pairs for each affected field. These would be any error displayed on the field itself
RedirectUrl | If the form has a [Redirect](http://help.wufoo.com/articles/en_US/SurveyMonkeyArticleType/Form-Settings#confirmation) set up, that URL will be included in the response

<aside class="warning">If you get an error about invalid dates, the specified format `MM/DD/YYYY` is incorrect. The correct date format is YYYYMMDD</aside>
