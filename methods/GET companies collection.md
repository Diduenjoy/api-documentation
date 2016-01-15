# GET `/companies`

### Get all your companies

## attributes

attribute          | description
------------- | -------------
__created_at__<br>_datetime_  | company creation date
__updated_at__<br>_datetime_  | company last modification date
__name__<br>_string_ | company name

## relationships

relationship          | description
------------------------------ | -------------
__surveys__ | company surveys

## Example

### ruby

```ruby
require 'rest-client'

RestClient::Request.execute method: :get,
  url: 'http://api.diduenjoy.com/api/v1/companies',
  user: 'PUT-YOUR-API-KEY-HERE'
```