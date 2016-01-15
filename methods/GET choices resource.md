# GET `/choices/:id`

### Get a single choice

## attributes

attribute          | description
------------- | -------------
__note__<br>_integer_ | choice note

## relationships

relationship          | description
------------------------------ | -------------
__answer_set__  | choice answer_set
__question__  | choice question

## Examples

### ruby

```ruby
require 'rest-client'

choice_id = 'PUT-YOUR-CHOICE-ID-HERE'

RestClient::Request.execute method: :get,
  url: "http://api.diduenjoy.com/api/v1/choices/#{choice_id}",
  user: 'PUT-YOUR-API-KEY-HERE'
```