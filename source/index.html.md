---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Skedgit API! You can use our API to access certain API endpoints, which will return different information based on your needs.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Skedgit uses API keys to allow access to the API. Skedgit expects for the API keys to be included in all API requests to the server in a header that looks like the following:

`x_access_token: meowmeowmeow`
`company_token: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your API keys.
</aside>

# Company

## Create a company

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "https://login.skedgitnow.com/api/v1/company/create"
  -H "vendor_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "OrgOne",
    "company_token": "SbdFE9M9JqwgEnuU3LtDokZA",
    "number_of_licenses": 0,
    "contract_start_date": "2019-01-01T00:00:00.000Z",
    "contact_end_date": "2019-12-31T00:00:00.000Z"
  }
  
]
```

This endpoint creates a company.

### HTTP Request

`POST https://login.skedgitnow.com/api/v1/company/create`

### Query Parameters

Parameter | Value | Description
--------- | ------- | -----------
name | "OrgOne" | This is the name of the company being created.
number_of_lienses | 0 | This is the number of licenses the company will start with.
contract_start_date | 2019-01-01 | This is the date that their contract with Skedgit will start.
contract_end_date | 2019-12-31 | This is the date that their contract with Skedgit will end.

<aside class="notice">
Remember — All the Parameters must be complete!
</aside>

## Update Company Details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/company/update"
  -H "vendor_token: meowmeowmeow"
  -H "company_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "name": "OrgOneUpdated",
  "number_of_licenses": 2,
  "contract_start_date": "2019-05-01T00:00:00.000Z",
  "contract_end_date": "2019-04-30T00:00:00.000Z",
}
```

This endpoint updates company details.

<aside class="warning">You must input both the vendor and company tokens to update the details</aside>

### HTTP Request

`PUT htts://login.skedgitnow.com/api/v1/company/update`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
name | "OrgOneUpdated" | This will update the name of the company
number_of_licenses | 2 | This will update the number of licenses assigned to the company
contract_start_date | "2019-05-01T00:00:00.000Z" | This will update the start date of the contract
contract_end_date | "2019-04-30T00:00:00.000Z" | This will update the end date of the contract

## Get Company Details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/company/details"
  -H "vendor_token: meowmeowmeow"
  -H "company_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "name": "OrgOneUpdated",
  "company_token": "SbdFE9M9JqwgEnuU3LtDokZA",
  "number_of_licenses": 2,
  "contract_start_date": "2019-05-01T00:00:00.000Z",
  "contract_end_date": "2019-04-30T00:00:00.000Z"  
}
```

This endpoint returns the company details.

### HTTP Request

`GET https://login.skedgitnow.com/api/v1/company/details`

### URL Parameters

Parameter | Description
--------- | -----------
<aside class="notice">
There are no Parameter's for this endpoint.
</aside>

## Get List of Company Users

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/users/get_company_users"
  -H "x_access_token: meowmeowmeow"
  
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 3,
  "name": "Test Users" 
}
```

This endpoint returns the Users associated with their Company.

### HTTP Request

`GET https://login.skedgitnow.com/api/v1/users/get_company_users`

### URL Parameters

Parameter | Description
--------- | -----------
<aside class="notice">
There are no Parameter's for this endpoint.
</aside>


# User

## Create a User

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/users/create"
  -H "vendor_token: meowmeowmeow"
  -H "company_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "message": "Successfully Created",
  "token": "eyJ0eXAi0iJKV1Q...",
  "user_id": 11  
}
```

This endpoint creates a Skedgit User for the company indicated by the company_token.

### HTTP Request

`POST https://login.skedgitnow.com/api/v1/users/create`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
firstname | "User" | This Parameter configures the first name of the Skedgit User.
lastname | "One" | This Parameter configures the last name of the Skedgit User.
email | "userone@test.com" | This Parameter configures the email of the Skedgit User.
password | "Password1!" | This Parameter configures the password of the Skedgit User.
password_confirmation | "Password1!" | This Parameter confirms the password of the Skedgit User and must match the password.

## Update User Details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/users/udpate"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "message": "Successfully Updated" 
}
```

This endpoint updates the Skedgit User details.

<aside class="notice">You only need to input the parameters that you wish to update.</aside>

### HTTP Request

`PUT https://login.skedgitnow.com/api/v1/users/udpate`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
firstname | "UserUpdated" | This Parameter updates the first name of the Skedgit User with the new value.
lastname | "OneUpdated" | This Parameter updates the last name of the Skedgit User with the new value.
email | "useroneupdated@test.com" | This Parameter updates the email of the Skedgit User with the new value.
password | "Password1!" | This Parameter updates the password of the Skedgit User with the new value.
password_confirmation | "Password1!" | This Parameter confirms the new password value of the Skedgit User and must match the password.

## Get User Details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/users/details"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "firstname": "UserUpdated",
  "lastname": "OneUpdated",
  "email": "useroneupdated@test.com"
}
```

This endpoint displays the Skedgit User details.



### HTTP Request

`GET https://login.skedgitnow.com/api/v1/users/details`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters for this endpoint.</aside>

## Delete User

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/users/delete/:user_id"
  -H "vendor_token: meowmeowmeow"
  -H "company_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "message": "Successfully Deleted"
}
```

This endpoint deletes a User.

<aside class="warning">Make sure to input the user_id in the URL and not the parameter.</aside>

### HTTP Request

`DELETE https://login.skedgitnow.com/api/v1/users/delete/:user_id`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
user_id (in the URL) | 2 | This is the user_id that will be deleted



## Get User Calendar List

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/users/get_calendars"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
[
{
  "id": 3,
  "calendar_name": "test.user@google.com"
}
]
```

This endpoint returns a list of the Calendars associated with the User.



### HTTP Request

`GET https://login.skedgitnow.com/api/v1/users/get_calendars`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>

# Login/Logout

## User Login

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/auth/login"
  
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "token": "meowmeowmeow"
}

```

This endpoint returns the x_access_token of the Skedgit User.



### HTTP Request

`POST https://login.skedgitnow.com/api/v1/auth/login`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
email | test@googleuser.com | This is the email that is associated with the User login
password | Password1! | This is the password that is associated with the User login
vendor_token | meowmeowmeow | This value is the API Access Token assigned to Partner


## User Logout

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/auth/logout"
  
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "successful logout"
}

```

This endpoint logs out the Skedgit User



### HTTP Request

`POST https://login.skedgitnow.com/api/v1/auth/logout`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
email | test@googleuser.com | This is the email that is associated with the User login
password | Password1! | This is the password that is associated with the User login
vendor_token | meowmeowmeow | This value is the API Access Token assigned to Partner



# Calendar Authorization

## Google

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
This endpoint is executed through your web browser since we have to direct you to Google Authorization Page. Please make sure there is a redirect URI value inside the Partner Portal before executing this endpoint.
  
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> Entering the information in your web browser will return a success message in browser like this:

```json

https://login.skegitnow.com/?message=success

```

This endpoint authorizes Google Calendars for the Skedgit User and only needs to be executed once for each Calendar for the connection to be established.



### HTTP Request

`GET https://login.skedgitnow.com/api/v1/calendars/authorize_google_calendar?token&redirect_uri`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
token | meowmeowmeow | This is the x_access_token of the Skedgit User and will be the value of 'token' in the URL
redirect_uri | https://skedgitnow.com | This value is configured in the Redirect URI tab in the Partner Portal and will be the value of 'redirect_uri' in the URL

## Microsoft Office 365/Outlook

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
This endpoint is executed through your web browser since we have to direct you to the Microsoft Authorization Page. Please make sure there is a redirect URI value inside the Partner Portal before executing this endpoint.
  
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> Entering the information in your web browser will return a success message in browser like this:

```json

https://login.skegitnow.com/?message=success

```

This endpoint authorizes Microsoft Calendars for the Skedgit User and only needs to be executed once for each Calendar for the connection to be established.



### HTTP Request

`GET https://login.skedgitnow.com/api/v1/calendars/authorize_outlook_calendar?token&redirect_uri`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
token | meowmeowmeow | This is the x_access_token of the Skedgit User and will be the value of 'token' in the URL
redirect_uri | https://skedgitnow.com | This value is configured in the Redirect URI tab in the Partner Portal and will be the value of 'redirect_uri' in the URL



#Personal Link

## Get Personal Link Details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/personal_link_details"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "personal_link": "http://www.skedgit.me/testpersonallink",
  "enabled": true
}

```

This endpoint returns the Personal Link URL and status (enabled/disbaled)



### HTTP Request

`GET https://login.skedgitnow.com/api/v1/personal_link_details`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>

## Personalize Personal Link

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/personalize_personal_link"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "sucessfully updated the personal link.", OR
  "message": "The calendar token you entered already exists, please enter a different token."
}

```

This endpoint updates the personal link URL with a value you choose.



### HTTP Request

`PATCH https://login.skedgitnow.com/api/v1/personal_link_details`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
calendar_url_token | 


## Toggle Personal Link URL (Enable/Disable)

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/toggle_personal_link"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Successfully updated the personal link."
  
}

```

This endpoint returns the Personal Link URL and status (enabled/disbaled)



### HTTP Request

`PATCH https://login.skedgitnow.com/api/v1/toggle_personal_link`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>

## Get default meeting location

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/default_meeting_location"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "default meeting location": "This is the default meeting location"
  
}

```

This endpoint returns the default meeting location.


### HTTP Request

`GET https://login.skedgitnow.com/api/v1/default_meeting_location`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>

## Get default meeting details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/default_meeting_details"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "default meeting details": "This is the default meeting details"
  
}

```

This endpoint returns the default meeting details.


### HTTP Request

`GET https://login.skedgitnow.com/api/v1/default_meeting_details`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>


## Update default meeting location

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/update_default_meeting_location"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Successfully updated Default Meeting Location"
}

```

This endpoint updates the default meeting location.


### HTTP Request

`PATCH https://login.skedgitnow.com/api/v1/update_default_meeting_location`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
default_meeting_location | This is the new default meeting location | This will update the default meeting location with the new value inputted.


## Update default meeting details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/update_default_meeting_details"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Successfully updated default meeting details"
  
}

```

This endpoint updates the default meeting details.


### HTTP Request

`PATCH https://login.skedgitnow.com/api/v1/update_default_meeting_details`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
default_meeting_details | This is the new default meeting details | This will update the default meeting details with the new value inputted.


## Toggle Availability Days

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/toggle_availability_day"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Successfully toggled Day availablity"
  
}

```

This endpoint toggles on/off availability for certain days that you select.

<aside class="notice">Each day must be inputted individually and not in a list or array</aside>

### HTTP Request

`PATCH https://login.skedgitnow.com/api/v1/toggle_availability_day`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
day_type | monday | In this example 'Monday' would be toggled on or off depending on the current status of that day.


## Copy Availability Times to all other days

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/user_availability_copy_to_all"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Successfully Updated"
  
}

```

This endpoint copies the availability times to all active days.

<aside class="notice">time_zone corresponds to logged in users time zone timings are an array of the following object {
                          start_time_hour: value,
                          end_time_hour: value
                    }
                    Where value is a number between 0 and 23  (Note: all the disabled days will remain unchanged)  </aside>

### HTTP Request

`PUT https://login.skedgitnow.com/api/v1/user_availability_copy_to_all`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
{"time_zone": | "America/Denver", | This parameter configures the time zone.
"timings": | [{"start_time_hour": 9,"end_time_hour": 12},{"start_time_hour": 14,"end_time_hour": 17}]} | This parameter details out the times Skedgit User is available during the day.


## Update Users Availabilities

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/update_availabilities"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Successfully Updated"
  
}

```

This endpoint updates the availability times for all the days indicated.

<aside class="notice">Where user_availabilities is an array object that represent all the days of the week, it has two properties (day, timings) day represents the day namely Sunday to Saturday and timings is an array that represents the timing intervals for that day (Note: If any day is missing in the user_availabilities array, that day will be disabled.)  </aside>

### HTTP Request

`PUT https://login.skedgitnow.com/api/v1/update_availabilities`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
{"time_zone": | "America/Denver", | This parameter configures the time zone.
"user_availabilities": | [{"day": "Monday","timings": [ {"start_time_hour": 9,"end_time_hour": 12}, {"start_time_hour": 13, "end_time_hour": 17}]} | This parameter details out the days and times the Skedgit User is available during the day for each day of the week.



## Get user availability

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/get_user_availability"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
[
{
  "day": "Sunday",
  "start_time": "2019-01-01T03:30:00.000Z",
  "end_time": "2019-01-01T11:30:00.000Z",
  "enabled": false
},
{
  "day": "Monday",
  "start_time": "2019-01-01T03:30:00.000Z",
  "end_time": "2019-01-01T06:30:00.000Z",
  "enabled": true
},
{
  "day": "Monday",
  "start_time": "2019-01-01T08:30:00.000Z",
  "end_time": "2019-01-01T11:30:00.000Z",
  "enabled": true
},
{
  "day": "Tuesday",
  "start_time": "2019-01-01T03:30:00.000Z",
  "end_time": "2019-01-01T06:30:00.000Z",
  "enabled": true
},
{
  "day": "Tuesday",
  "start_time": "2019-01-01T08:30:00.000Z",
  "end_time": "2019-01-01T11:30:00.000Z",
  "enabled": true
},
{
  "day": "Wednesday",
  "start_time": "2019-01-01T03:30:00.000Z",
  "end_time": "2019-01-01T06:30:00.000Z",
  "enabled": true
},{
  "day": "Wednesday",
  "start_time": "2019-01-01T08:30:00.000Z",
  "end_time": "2019-01-01T11:30:00.000Z",
  "enabled": true
},
{
  "day": "Thursday",
  "start_time": "2019-01-01T03:30:00.000Z",
  "end_time": "2019-01-01T06:30:00.000Z",
  "enabled": true
},
{
  "day": "Thursday",
  "start_time": "2019-01-01T08:30:00.000Z",
  "end_time": "2019-01-01T11:30:00.000Z",
  "enabled": true
},
{
  "day": "Friday",
  "start_time": "2019-01-01T03:30:00.000Z",
  "end_time": "2019-01-01T06:30:00.000Z",
  "enabled": true
},
{
  "day": "Friday",
  "start_time": "2019-01-01T08:30:00.000Z",
  "end_time": "2019-01-01T11:30:00.000Z",
  "enabled": true
},
{
  "day": "Saturday",
  "start_time": "2019-01-01T03:30:00.000Z",
  "end_time": "2019-01-01T11:30:00.000Z",
  "enabled": false
}
]

```

This endpoint returns the users current availability for the week.



### HTTP Request

`GET https://login.skedgitnow.com/api/v1/get_user_availability`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>


## Reset Availability to default

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/reset_user_availability"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "message": "Successfully Reset"
}
```

This endpoint resets the Skedgit Users availability back to defaults

<aside class="notice">Note: this will reset your availability to 9 AM - 5 PM from Sunday to Saturday</aside>

### HTTP Request

`PATCH https://login.skedgitnow.com/api/v1/reset_user_availabilty`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
time_zone | America/Denver | This configures the time zone for the default availibility.


# Event Types

## Get Event Type

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/event_type/:id"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 32,
  "title": "This is an Personal Link Event Title",
  "duration": 60,
  "include_default_meeting_description": false,
  "include_default_meeting_location": false,
  "owner_type": "user",
  "owner_id": 10,
  "is_inclusive": false,
  "owner_calendar_id": 17
}

{
  "id": 31,
  "title": "This is a Team Link Event Title",
  "duration": 120,
  "include_default_meeting_description": false,
  "include_default_meeting_location": false,
  "owner_type": "team",
  "owner_id": 5,
  "is_inclusive": false,
  "owner_calendar_id": null
}

```

This endpoint retrieves a specific event type's details that you identify


### HTTP Request

`GET https://login.skedgitnow.com/api/v1/event_type/:id`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
id | 32 | This parameter will be appended to the URL where ':id' is indicated.


## Get all Personal Link event types

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/personal_link_event_types"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
[
{
  "id": 21,
  "title": "Event Title One",
  "duration": 30,
  "include_default_meeting_description": false,
  "include_default_meeting_location": false,
  "owner_type": "user",
  "owner_id": 10,
  "is_inclusive": false,
  "owner_calendar_id": 17
},

{
  "id": 22,
  "title": "Event Title Two",
  "duration": 15,
  "include_default_meeting_description": false,
  "include_default_meeting_location": false,
  "owner_type": "user",
  "owner_id": 10,
  "is_inclusive": false,
  "owner_calendar_id": 17
}
]
```

This endpoint retrieves all Personal Link event types for a specific Skedgit User


### HTTP Request

`GET https://login.skedgitnow.com/api/v1/personal_link_event_types`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>


## Get All Team Link Event Types


```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/team_link_event_types/:team_id"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
[
{
  "id": 31,
  "title": "This is a Team Link Event Title",
  "duration": 120,
  "include_default_meeting_description": false,
  "include_default_meeting_location": false,
  "owner_type": "team",
  "owner_id": 5,
  "is_inclusive": false,
  "owner_calendar_id": null
},
]

```

This endpoint retrieves a specific team event type


### HTTP Request

`GET https://login.skedgitnow.com/api/v1/team_link_event_types/:team_id`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
:team_id | 31 | This parameter will be appended to the URL and retrieve a specific team link


## Create Event Type


```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/event_type"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "id": 32,
  "title": "This is a new Event Title",
  "duration": 60,
  "include_default_meeting_description": false,
  "include_default_meeting_location": false,
  "owner_type": "user",
  "owner_id": 10,
  "is_inclusive": false,
  "owner_calendar_id": 17
},


```

This endpoint creates an event type


### HTTP Request

`POST https://login.skedgitnow.com/api/v1/event_type`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
title | This is a new Event Title | This parameter will configure the title of the event type
duration | 60 | This parameter will configure the duration of the event type
include_default_meeting_description | false | This parameter is optional and will include the default meeting description
include_default_meeting_location | false | This parameter is optional and will include the default meeting location
is_inclusive | false | This parameter is specific to team link and if true will indicate that all team members must be available
owner_calendar_id | 17 | This parameter indicates who is the owner of the event
team_id | 13 | Note: if team_id is provided it will create an event type for Team Link. Also, for creating a Team Link event the user needs to be a part of the team, otherwise you will get "Action restricted, user doesn't belog to the Team" error

## Update Event Type

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/event_type/:id"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "id": 31,
  "title": "Updated Event Title",
  "duration": 120,
  "include_default_meeting_description": false,
  "include_default_meeting_location": false,
  "owner_type": "user",
  "owner_id": 10,
  "is_inclusive": false,
  "owner_calendar_id": 17
},


```

This endpoint updates an event type


### HTTP Request

`PUT https://login.skedgitnow.com/api/v1/event_type/:id`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
title | Updated Event Title | This parameter will configure the title of the event type
duration | 120 | This parameter will configure the duration of the event type
include_default_meeting_description | false | This parameter is optional and will include the default meeting description
include_default_meeting_location | false | This parameter is optional and will include the default meeting location
is_inclusive | false | This parameter is specific to team link and if true will indicate that all team members must be available
owner_calendar_id | 17 | This parameter indicates who is the owner of the event
:id | 13 | This parameter is appended to the URL. Note: If updates are made to a Team Link event type the logged in user should be part of the team, otherwise you will get "Action restricted, user doesn't belong to the Team" error


## Delete Event Type

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/event_type/:id"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Meeting type was sucessfully destroyed."
}


```

This endpoint deletes an event type


### HTTP Request

`DELETE https://login.skedgitnow.com/api/v1/event_type/:id`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
:id | 13 | This parameter is appended to the URL. Note: If deleting a Team Link event type the logged in user should be a part of the team, otherwise you will get "Action restricted, user doesn't belog to the Team" error

# Custom Links

## Create Suggested Event

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/calendar_events/create_suggested_event"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "id": 11503,
  "title": "Custom Link Title",
  "link": "https;//login.skedgit.com/sa/rHkr..."
},


```

This endpoint creates a Custom Link


### HTTP Request

`POST https://login.skedgitnow.com/api/v1/calendar_events/create_suggested_event`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
{title | Title | This parameter will configure the title of the Custom Link
description | Desc | This parameter will configure the description of the Custom Link
location | Loc | This parameter will configure the location of the Custom Link
usage_type | multiple | This parameter will determine if the Custom Link is a one time or multiple time event (See Appendix)
calendar_id | 4 | This parameter specifies the calendar id for owner of events on Custom Link
include_other_users_availability_type | any | This parameter indicates whether all internal attendees need to be availalble or just one internal attendee for the event to be booked
event_times_attributes | { "0": {"start": "2019-05-09T09:00", "end": '2019-05-09T10:00"}, "1": {"start": "2019-05-09T13:00", "end": "2019-05-09T14:00}}, | This parameter determines the availability time slots that will be presented in the Custom Link
time_zone | Mountain Time (US & Canada) | This determines the time zone used for the Custom Link (See Appendix for values)
internal_attendees | [3] | Identifies the internal Skedgit users
external_attendees | ["test1@google.com", "test2@google.com"]}


## Create Send All Availability Link

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/calendar_events/create_send_all_availability_link"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "id": 11503,
  "title": "Custom Link Title",
  "link": "https;//login.skedgit.com/sa/rHkr..."
},


```

This endpoint creates a Custom Link with all availability included between two datess


### HTTP Request

`POST https://login.skedgitnow.com/api/v1/calendar_events/create_send_all_availabilty_link`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
{title | Title | This parameter will configure the title of the Custom Link
description | Desc | This parameter will configure the description of the Custom Link
location | Loc | This parameter will configure the location of the Custom Link
usage_type | multiple | This parameter will determine if the Custom Link is a one time or multiple time event (See Appendix)
calendar_id | 2 | This parameter specifies the calendar id for owner of events on Custom Link
include_other_users_availability_type | any | This parameter indicates whether all internal attendees need to be availalble or just one internal attendee for the event to be booked
start_date | 2019-05-09 | This parameter determines the start date of the availability shared (limited to 2 week span)
end_date | 2019-05-15 | This parameter determines the end date of the availabilty shared (limited to 2 week span)
time_zone | Mountain Time (US & Canada) | This determines the time zone used for the Custom Link (See Appendix for values)
duration | 60 | This parameter will configure the duration of the event
internal_attendees | [3] | Identifies the internal Skedgit users
external_attendees | ["test1@google.com", "test2@google.com"]}


## Get All Custom Links

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/calendar_events/get_all_custom_links"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "custom_links": [
    {
      "id": 9762,
      "title": "Custom Event One",
      "link": "your custom link URL"
    },
    {
      "id": 10434,
      "title": "Test Custom Link",
      "link": "your custom link URL"
    }
  ]
}

```

This endpoint returns all Custom Links created by Skedgit User.


### HTTP Request

`GET https://login.skedgitnow.com/api/calendar_events/get_all_custom_links`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
<aside class="notice">There are no Parameters associated with this endpoint.</aside>


## Delete Custom Link

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/calendar_events/:event_id"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Successfully deleted"
}

```

This endpoint deletes a specified Custom Link.


### HTTP Request

`DELETE https://login.skedgitnow.com/api/calendar_events/:event_id`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
:event_id | 9762 | This parameter is appended to the URL


# SkedgiSense

## Create SkedgiSense Link

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/calendar_events/create_skedgi_sense"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "id": "9363",
  "title": "SkedgiSense Title",
  "links": {
    "info_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
    "google_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
    "outlook_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
    "custom_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
  }
}

```

This endpoint creates a SkedgiSense Link.


### HTTP Request

`POST https://login.skedgitnow.com/api/calendar_events/create_skedgi_sense`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
title | SkedgiSense Title | This parameter defines the title of the event
include_default_location | true | This parameter includes the default location in the event if true
include_default_description | true | This parameter includes the default description in the event if true
duration | 60 | This parameter defines the duration of the event
time_zone | Mountain Time (US & Canada) | Defines the time zone
attendees | test1@google.com | lists the attendess included in the SkedgiSense link
calendar_id | 3 | This parameter defines the owner of the event shared in the link
attendees | [test1@google.com, test2@google.com] | This parameter defines the attendees included in the link
start_time | 2019-04-23 (format: YYYY-MM-DD) | Defines the start date that availablity is taken into account
end_time | 2019-04-24 (format: YYYY-MM-DD) | Defines the end date that availability is taken into account 

## Create SkedgiSense One-Click Meeting

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/calendar_events/create_skedgi_sense"
  -H "x_access_token": "meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json

{
  "message": "Meeting successfully scheduled"
}

```

This endpoint creates a SkedgiSense One-Click Meeting.


### HTTP Request

`POST https://login.skedgitnow.com/api/calendar_events/create_skedgi_sense`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
title | SkedgiSense Internal Meeeting Title | This parameter defines the title of the event
include_default_location | true | This parameter includes the default location in the event if true
include_default_description | true | This parameter includes the default description in the event if true
duration | 60 | This parameter defines the duration of the event
time_zone | Mountain Time (US & Canada) | Defines the time zone
internal_only | true | This indicates that it will be a one-click scheduled meeting instead of a link
attendees | [test1@google.com, test2@google.com] | This parameter defines the attendees included in the link
start_time | 2019-04-23 (format: YYYY-MM-DD) | Defines the start date that availablity is taken into account
end_time | 2019-04-24 (format: YYYY-MM-DD) | Defines the end date that availability is taken into account 


## SkedgiSense Event Details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "https://login.skedgitnow.com/api/v1/calendar_events/skedgi_sense_events_details/:id"
  -H "x_access_token: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
[
{
  "id": 9363,
  "title": "This is a SkedgiSense Link Event Title",
  "links": {
    "info_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
    "google_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
    "outlook_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
    "custom_link": "https://login.skedgit.me/ez/hdpxBGiXD...",
  }
},
]

```

This endpoint displays all SkediSense event details.


### HTTP Request

`GET https://login.skedgitnow.com/api/v1/calendar_events/skedgi_sense_event_details/:id`

### URL Parameters

Parameter | Value | Description
--------- | ----------- | ------------
:id | 9363 | This parameter will be appended to the URL and retrieve a specific SkedgiSense link


# Appendix

## Meeting Type / Event Type

Add different types of events to Personal Link and Team Link (like a meeting with a different duration)

### Attributes
### 1. title (string):
Represents the title for event type (Required)
### 2. duration (number):
Represents the duration for meetings. Value must be in minutes. Default: 30 (30 minutes) Allowed durations: 10, 15, 30, 45, 60, 75, 90, 120 (Optional Field)
### 3. include_default_meeting_description (boolean):
If true, the users default meeting description will be used for the meeting. Default: false (Optional field)
### 4. include_default_meeting_location (boolean):
If true, the users default meeting location will be used for the meeting. Default: false (Optional field)
### 5. owner_calendar_id (string):
Applicable only for Personal Link. Calendar id of the calendar with which this event type should be associated. Default: logged in user's primary calendar id (Optional field)
### 6. is_inclusive (string):
Special case for team link where availability is shown based on all the team members availability. Default: false. Note: applicable only for team link. (Optional field)
### 7. owner_type (ReadOnly):
Specifies whether the event type belongs to Team Link or Personal Link. Value: 'User' for Personal Link and 'Team' for Team Link
### 8. owner_id (ReadOnly):
Cooresponds to the owner id of event type, for Personal Link it will be the logged in User id and for Team Link it will be the team id.

## Custom Link

### Attributes
### 1. title: (string)
Specifies the title of the custom link
### 2. description: (string)
specifies the description fo the custom link
### 3. location: (string)
specifies the location of the custom link
### 4. include_default_location: (boolean)
default value is false, if specified the location will be the default user location, if location (3rd params in the list) is already provided this attribute will have no effect on the location of the custom link
### 5. include_default_description: (boolean)
default value is false, if specified the description will be the default user description, if description (4th params in the list) is already provided this attribute will have no effect on the description of the custom link
### 6. usage_type: (string)
default value is 'single'. Possible values are 'single' or 'multiple'. Single: create a custom link that can be used for single time (i.e. Once someone books an event this link will become inactive). Multiple: creates a custom link that can be used for multiple time use (Until all the available times are booked or are in the past)
### 7. calendar_id (number)
If a user has multiple calendars then this will determine which calendar the event will be booked. Default value is your primary calendar id
### 8. internal_attendees: (array of numbers)
The users id's in your Organization can be used here
### 9. external_attendees: (array of emails)
Any email that is outside of your organization
### 10. include_other_users_availability_type: (string)
Default value is 'all'. Possible values are 'all' or 'any'. 'all': show availability based on you and internal_attendees availability, show only those events where you and internal_attendees are available. 'any': show availabilty based on you and internal_attendees availability, show only those events when either you or other internal_attendees are available.
### 11. event_times_attributes: (object of start and end time)
See example in sample request where start is the start time and end is the end time. Format for start and end time is 2019-05-09T9:00 (yyyy-mm-ddThh:mm). 
### 12. time_zone:
Time zone of user (See Appendix: Time Zone Values)
### 13. duration:
Specifies the duration of the event
### 14. start_date:
Specifies the start date (format: yyyy-mm-dd)
### 15. end_date:
Specifies the end date (format: yyyy-mm-dd)


## Time Zone Values

"Hawaii",
"Alaska",
"Pacific Time (US & Canada)",
"Mountain Time (US & Canada)",
"Arizona",
"Central Time (US & Canada)",
"Eastern Time (US & Canada)",
"Atlantic Time (Canada)",
"Newfoundland",
"Greenland",
"Mid-Atlantic",
"Azores",
"London",
"Paris",
"Athens",
"Istanbul",
"Tehran",
"Abu Dhabi",
"Kabul",
"Islamabad",
"Mumbai",
"Kathmandu",
"Dhaka",
"Bangkok",
"Hong Kong",
"Tokyo",
"Darwin",
"Brisbane",
"Magadan",
"Fiji",
"Chatham Is.",
"Somoa"