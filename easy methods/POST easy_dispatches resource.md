# POST `/easy_dispatches`

### Send a survey to a specified email address

## attributes

attribute          |     | description
------------- | --- | -------------
__email__<br>_string_  | _required_ | email address to which send the survey
__survey_id__<br>_string_  | _required_ | id of the survey
__segments__<br>_hash { string: string\|array[string] }_ | | custom data associated with the survey

## Special Segments

- `language` : if available, force the survey language, should be a ISO 639-1 code (https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
- `scheduled_at` : schedule the dispatch, should be formated as ISO 8601 (https://en.wikipedia.org/wiki/ISO_8601)

## Examples

### ruby

```ruby
require 'rest-client'

RestClient::Request.execute method: :post,
  url: 'https://api.diduenjoy.com/api/v1/easy_dispatches',
  user: 'PUT-YOUR-API-KEY-HERE',
  headers: {
    content_type: 'application/json'
  },
  payload: {
    email: 'client@example.com',
    survey_id: 'YOUR-SURVEY-ID-HERE',
    segments: {
      gender: 'Mister',
      scheduled_at: '2016-04-18 15:07:00',
      name: 'DJ',
      interests: ['music', 'dance']
    }
  }

# => {
#     "id": "DISPATCH-ID",
#     "email": "client@example.com",
#     "survey_id": "YOUR-SURVEY-ID-HERE",
#     "segments": {
#       "gender": ["Mister"],
#       "scheduled_at": ["2016-04-18 15:07:00"],
#       "interests": ["music", "dance"],
#       "name": ["DJ"]
#     }
#   }
```
