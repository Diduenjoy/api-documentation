# GET `/answer_sets`

### List all your answer_sets

## attributes

attribute          | description
------------- | -------------
__created_at__<br>_datetime_  | answer_set creation date
__updated_at__<br>_datetime_  | answer_set last modification date
__comment__<br>_string_ | responder comment
__completed__<br>_boolean_ | equal "true" if the responder completed all your survey pages else "false"
__would_recommend__<br>_integer_ | responder recommendation note

## relationships

relationship          | description
------------------------------ | -------------
__client__  | answer_set responder
__survey_language__  | answer_set survey_language
__choices__  | responder choices

## Examples

### ruby

```ruby
require 'rest-client'

RestClient::Request.execute method: :get,
  url: 'http://api.diduenjoy.com/api/v1/answer_sets',
  user: 'PUT-YOUR-API-KEY-HERE'
```