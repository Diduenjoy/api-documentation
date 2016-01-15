# GET `/clients`

### List all your clients

## attributes

attribute          | description
------------- | -------------
__created_at__<br>_datetime_  | client creation date
__updated_at__<br>_datetime_  | client last modification date
__email__<br>_string_ | client name

## relationships

relationship          | description
------------------------------ | -------------
__answer_sets__ | client answer_sets

## Examples

### ruby

```ruby
require 'rest-client'

RestClient::Request.execute method: :get,
  url: 'http://api.diduenjoy.com/api/v1/clients',
  user: 'PUT-YOUR-API-KEY-HERE'
```