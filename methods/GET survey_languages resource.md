# GET `/survey_languages/:id`

### Get a single survey_language

## attributes

attribute          | description
------------- | -------------
__would_recommend_prefix__<br>_string_ | recommendation question prefix (ex: Would you recommend)
__would_recommend_text__<br>_string_  | recommendation question text
__open_question__<br>_string_  | text written above the comment textarea

## relationships

relationship          |description
------------------------------ | -------------
__survey__  | survey
__language__  | language
__questions__  | localized questions

## Examples

### ruby

```ruby
require 'rest-client'

survey_language_id = 'PUT-YOUR-SURVEY_LANGUAGE-ID-HERE'

RestClient::Request.execute method: :get,
  url: "https://api.diduenjoy.com/api/v1/survey_languages/#{survey_language_id}",
  user: 'PUT-YOUR-API-KEY-HERE'
```