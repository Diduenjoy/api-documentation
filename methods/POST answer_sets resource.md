# POST `/answer_sets`

### Create an answer_set

## attributes

attribute          | description
------------- | -------------
__comment__<br>_string_ | responder comment
__completed__<br>_boolean_ | Set to true to mark the answer_set as completed and trigger the associated scenarii and third party integrations
__would_recommend__<br>_integer_ | responder recommendation note
__segments__<br>_hash { string: string\|array[string] }_ | custom data associated with the answer set

## relationships

relationship          | description
------------------------------ | -------------
__client__<br>required | answer_set responder
__survey_language__<br>required  | answer_set survey_language

## Examples

### json

```javascript
// POST /api/v1/answer_sets
{
  "data": {
    "type": "answer_sets",
    "attributes": {
      "would_recommend": 4,
      "comment": "Perfect !",
      "completed": true,
      "segments": {
        "gender": "male",
        "age": "42"
      }
    },
    "relationships": {
      "client": {
        "data": { "type": "clients", "id": "CLIENT-UUID" }
      },
      "survey_language": {
        "data": {"type": "survey_languages", "id": "SURVEY-LANGUAGE-UUID"}
      }
    }
  }
}
```