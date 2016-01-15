# GET `/surveys/:id`

### Get a single survey

## attributes

attribute          | description
------------- | -------------
__created_at__<br>_datetime_  | survey creation date
__updated_at__<br>_datetime_  | survey last modification date
__name__<br>_string_  | survey name
__hash__<br>_string_  | survey public hash, used with companies custom mailing systems

## relationships

relationship          |description
------------------------------ | -------------
__company__  | company owning the survey
__survey_languages__  | survey localized texts (at least 1)

## Examples

### ruby

```ruby
require 'rest-client'

survey_id = 'PUT-YOUR-SURVEY-ID-HERE'

RestClient::Request.execute method: :get,
  url: "http://api.diduenjoy.com/api/v1/surveys/#{survey_id}",
  user: 'PUT-YOUR-API-KEY-HERE'

# => {
#   data: {
#     type: "surveys",
#     id: "YOUR-SURVEY-ID",
#     attributes: {
#       created_at: "2016-01-12 17:14:53 UTC",
#       updated_at: "2016-01-12 17:14:59 UTC",
#       name: "Satisfaction Survey 1",
#       hash: "dd2d2ddd2d"
#     },
#     relationships: {
#       company: {
#         data: {
#         type: "companies",
#         id: "YOUR-COMPANY-ID",
#         links: {
#           self: "http://localhost:3000/api/v1/companies/YOUR-COMPANY-ID"
#         }
#       }
#     },
#     survey_languages: {
#       data: [
#         {
#           type: "survey_languages",
#           id: "FIRST-SURVEY_LANGUAGE-ID",
#           links: {
#             self: "http://localhost:3000/api/v1/survey_languages/FIRST-SURVEY_LANGUAGE-ID"
#           }
#         },
#         {
#           type: "survey_languages",
#           id: "SECOND-SURVEY_LANGUAGE-ID",
#           links: {
#             self: "http://localhost:3000/api/v1/survey_languages/SECOND-SURVEY_LANGUAGE-ID"
#           }
#         }
#       ]
#     }
#   },
#     links: {
#       self: "http://localhost:3000/api/v1/surveys/YOUR-SURVEY-ID"
#     }
#   }
# }
```