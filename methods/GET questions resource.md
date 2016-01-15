# GET `/questions/:id`

### Get a single question

## attributes

attribute          | description
------------- | -------------
__position__<br>_integer_ | question position
__text__<br>_string_ | question text

## relationships

relationship          | description
------------------------------ | -------------
__survey_language__ | question survey_language

## Examples

### ruby

```ruby
require 'rest-client'

question_id = 'PUT-YOUR-QUESTION-ID-HERE'

RestClient::Request.execute method: :get,
  url: "http://api.diduenjoy.com/api/v1/questions/#{question_id}",
  user: 'PUT-YOUR-API-KEY-HERE'
```