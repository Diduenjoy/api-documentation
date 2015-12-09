# Dispatches

To send a survey, you create a dispatch object. You can retrieve all individual dispatches as well as list all dispatches.

## The dispatch object


```javascript
"data": {
  /**
    * Resource type
    * @type String
    * @value "dispatches"
    */
  "type": "dispatches",
  /**
    * Resource id
    * @type String
    */
  "id": null,
  "attributes": {
    /**
      * The email address to send the survey to.
      * @type String
      */
    "email_address": null,
    /**
      * The datatime which the dispatch is delayed. Sould be formated following the ISO 8601 standard (https://en.wikipedia.org/wiki/ISO_8601).
      * @type String
      */
    "scheduled_at": null,
    /**
      * AnswerSet segments
      * @type Object
      */
    "segments": {
      /**
        * AnswerSet segment value.
        * @type String or Array
        */
      "segment 0 key": null,
      "segment 1 key": [null, null, null]
    }
  },
  "relationships": {
    "survey": {
      "data": {
        /**
          * Related resource type
          * @type String
          * @value "surveys"
          */
        "type": "surveys",
        /**
          * Related resource id
          * @type String
          */
        "id": null
      }
    },
    "language": {
      "data": {
        /**
          * Related resource type
          * @type String
          * @value "languages"
          */
        "type": "languages",
        /**
          * Related resource id
          * @type String
          */
        "id": null,
      }
    }
  }
}
```

## Available actions

- POST '/api/v1/dispatches'
- GET '/api/v1/dispatches'
- GET '/api/v1/dispatches/:id'

## Examples

### Dispatch a survey

```javascript
// POST http://api.diduenjoy.com/api/v1/dispatches
{
  "data": {
    "type": "dispatches",
    "attributes": {
      "email": "john@example.com"
      "scheduled_at": "2042-07-01T16:42:42Z",
      "segments": {
        "gender": "male",
        "age": "40",
        "city": "Liverpool"
        "songs": [
          "Stand By Me",
          "Imagine"
        ]
      }
    },
    {
      "relationships": {
        "survey": {
          "data": {
            "type": "surveys",
            "id": "60771e62-5925-4b8e-95f5-7ad431554dfb"
          }
        },
        "language": {
          "data": {
            "type": "languages",
            "id": "11b3afa1-2c1f-45be-8467-ed94f00fe9a9"
          }
        }
      }
    }
  }
}
```

