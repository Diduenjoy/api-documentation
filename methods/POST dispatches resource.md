# POST `/dispatches`

### Send a survey to a specified email address

## attributes

attribute          |     | description
------------- | --- | -------------
__to_email__<br>_string_  | _required_ | email address to which send the survey
__from_email__<br>_string_  | _required_ | survey email sender address
__from_name__<br>_string_  | _required_ |  survey email sender name
__subject__<br>_string_  | _required_ | survey email subject
__text__<br>_string_  | _required_ | survey email text content
__html__<br>_string_  | _required_ | survey email html content
__scheduled_at__<br>_string (datetime ISO 8601)_  |  | datetime when the survey should be sent
__segments__<br>_hash { string: string\|array[string] }_ | | custom data associated with the survey

## relationships

relationship          |     | description
------------------------------ | ---------- | -------------
__survey_language__ | _required_ | survey to send

## Examples

### ruby

```ruby
require 'rest-client'

RestClient::Request.execute method: :post,
  url: 'http://api.diduenjoy.com/api/v1/dispatches',
  user: 'PUT-YOUR-API-KEY-HERE',
  headers: {
    content_type: 'application/vnd.api+json'
  },
  payload: {
    data: {
      type: 'dispatches',
      attributes: {
        to_email: 'client@example.com',
        from_email: 'awesome-company@example.com',
        from_name: 'Awesome Company',
        subject: '{segment:gender} {segment:name} Information about your order - {company_name}',
        text: "Hi {segment:gender} {segment:name},\nYour opinion matters!\nPlease take this survey: {survey_url}. It will only take 10 seconds, or less. We swear!\nThe questions are short and sweet and will help us improve your experience!\n",
        html: '<html><head></head><body>Hi {segment:gender} {segment:name},<br><br>Your opinion matters!<br><br>Please take <a href="{survey_url}">this survey</a>. It will only take 10 seconds, or less. We swear!<br>The questions are short and sweet and will help us improve your experience!<br><br>Thank you!<br></body></html>',
        segments: {
          gender: 'Mister',
          name: 'DJ',
          interests: ['music', 'dance']
        }
      },
      relationships: {
        survey_language: {
          data: {
            type: 'survey_languages',
            id: 'YOUR-SURVEY_LANGUAGE-ID-HERE'
          }
        }
      }
    }
  }.to_json

# => {
#     data: {
#       type: "dispatches",
#       id: "THIS-DISPATCH-ID",
#       attributes: {
#         created_at: "2016-01-15 04:40:47 UTC",
#         updated_at: "2016-01-15 04:40:47 UTC",
#         to_email: "client@example.com",
#         from_email: "awesome-company@example.com",
#         from_name: "Awesome Company",
#         html: "<html><head></head><body>Hi {segment:gender} {segment:name},<br><br>Your opinion matters!<br><br>Please take <a href="{survey_url}#">this survey</a>. It will only take 10 seconds, or less. We swear!<br>The questions are short and sweet and will help us improve your #experience!<br><br>Thank you!<br></body></html>",
#         text: "Hi {segment:gender} {segment:name}, Your opinion matters! Please take this survey: {survey_url}. It will only take 10 seconds, or #less. We swear! The questions are short and sweet and will help us improve your experience! ",
#         segments: {
#         gender: [
#             "Mister"
#           ],
#           name: [
#             "DJ"
#           ],
#           interests: [
#             "music",
#             "dance"
#           ]
#         },
#         subject: "{segment:gender} {segment:name} Information about your order - {company_name}"
#       },
#       relationships: {
#         survey_language: {
#           data: {
#             type: "survey_languages",
#             id: "YOUR-SURVEY_LANGUAGE-ID",
#             links: {
#               self: "http://localhost:3000/api/v1/survey_languages/YOUR-SURVEY_LANGUAGE-ID"
#             }
#           }
#         }
#       },
#       links: {
#         self: "http://localhost:3000/api/v1/dispatches/THIS-DISPATCH-ID"
#       }
#     }
#   }
```