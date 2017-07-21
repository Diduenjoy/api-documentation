# Diduenjoy - API Documentation

[![GitHub version](https://badge.fury.io/gh/Diduenjoy%2Fapi-documentation.svg)](README.md)
[![MIT license](http://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## API Reference

The Diduenjoy API is organized around [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) and [JSON API](http://jsonapi.org/).
Our API is designed to have predictable, resource-oriented URLs and to use HTTP response codes to indicate API errors. We use built-in HTTP features, like HTTP authentication and HTTP verbs, which can be understood by off-the-shelf HTTP clients, and we support cross-origin resource sharing to allow you to interact securely with our API from a client-side web application (though you should remember that you should never expose your secret API key in any public website's client-side code). JSON will be returned in all responses from the API, including errors.

> ### API Endpoint
> 
> ``` https://api.diduenjoy.com/api/v1 ```

## Authentication

You authenticate to the Diduenjoy API by providing your secret API key in the request.
Your API keys carry many privileges, so be sure to keep them secret!

> ### API keys
> 
> You can find and generate your API keys in the API tab in your Diduenjoy dashboard settings.
> ![api keys in diduenjoy dahsboard settings](https://f.diduenjoy.com/api-key-screenshot.png)

Authentication to the API occurs via HTTP Basic Auth. Provide your API key as the basic auth username. You do not need to provide a password.

> ### Example
> 
> ```bash
> curl 'https://api.diduenjoy.com/api/v1/surveys' \
>  -u 'PUT-YOUR-API-KEY-HERE:'
>  ```
> 
> curl uses the -u flag to pass basic auth credentials (adding a colon after your API key will prevent it from asking you for a password).

## Methods

method | endpoint | description
------ | -------- | -----------
GET  | [`/api/v1/answer_sets`](methods/GET%20answer_sets%20collection.md) | List all your answer_sets
GET  | [`/api/v1/answer_sets/:id`](methods/GET%20answer_sets%20resource.md) | Get a single answer_set
GET | [`/api/v1/choices/:id`](methods/GET%20choices%20resource.md) | Get a single choice
GET | [`/api/v1/clients`](methods/GET%20clients%20collection.md) | List all your responders
GET | [`/api/v1/clients/:id`](methods/GET%20clients%20resource.md) | Get a single responder
GET | [`/api/v1/companies`](methods/GET%20companies%20collection.md) | Get all your companies
GET | [`/api/v1/companies/:id`](methods/GET%20companies%20resource.md) | Get a single company
POST | [`/api/v1/dispatches`](methods/POST%20dispatches%20resource.md) | Send a survey to a specified email address
GET | [`/api/v1/languages`](methods/GET%20languages%20collection.md) | List all languages available for survey responders
GET | [`/api/v1/languages/:id`](methods/GET%20languages%20resource.md) | Get a language available for survey responders
GET | [`/api/v1/questions/:id`](methods/GET%20questions%20resource.md) | Get a single question
GET | [`/api/v1/survey_languages/:id`](methods/GET%20survey_languages%20resource.md) | Get a single survey_language
GET | [`/api/v1/surveys`](methods/GET%20surveys%20collection.md) | List all your surveys
GET | [`/api/v1/surveys/:id`](methods/GET%20surveys%20resource.md) | Get a single survey

## Resources URIs

Each resource has its own addresses or URIs mapped as follows:
- `GET https://api.diduenjoy.com/api/v1/:resource_type` - Retrieves as collection of resources
- `GET https://api.diduenjoy.com/api/v1/:resource_type/:id` - Retrieves a specific resource


> ### Examples
> 
> #### Retrieve all your responders
> 
> ```javascript
> // GET https://api.diduenjoy.com/api/v1/clients
> {
>   "data": [
>     {
>       "type": "clients",
>       "id": "CLIENT-ID",
>       "attributes": {
>         "created_at": "2015-07-01T16-06-01.123Z",
>         "updated_at": "2015-07-01T16-06-01.123Z",
>         "email": "test-client@example.com"
>       },
>       ...
>     },
>     ...
>    ]
>  }
>  ```
> 
> #### Retrieve a specific responder
> 
> ```javscript
> // GET https://api.diduenjoy.com/api/v1/clients/CLIENT-ID
> {
>   "data": {
>     "type": "clients",
>     "id": "CLIENT-ID",
>     "attributes": {
>       "created_at": "2015-07-01T16-06-01.123Z",
>       "updated_at": "2015-07-01T16-06-01.123Z",
>       "email": "test-client@example.com"
>     },
>     ...
>   }
>  }
> ```

## Sorting

You can sort your queries with the sort parameter:

```
https://api.diduenjoy.com/api/v1/:resource_type?sort=:attribute,...
```

> ### Examples
> 
> `GET https://api.diduenjoy.com/api/v1/answer_sets?sort=created_at,updated_at`
> 
> `GET https://api.diduenjoy.com/api/v1/clients?sort=-email`

## Filtering

You can filter you queries with the filter parameter:

```
GET https://api.diduenjoy.com/api/v1/:resource_type?filter[:attribute]=:value
```

> ### Example
> 
> `GET https://api.diduenjoy.com/api/v1/clients?filter[email]=test@test.com`

## Including

You can include your resources relationships with the include parameter:

```
GET https://api.diduenjoy.com/api/v1/:resource_type?include=:relationships
```

> ### Example
> 
> `GET https://api.diduenjoy.com/api/v1/answer_sets?include=client,choices`

# New AnswerSet Webhook

You can register a webhook, that will be called for each new answer_set completed.

Diduenjoy will `POST` the same content as `https://api.diduenjoy.com/api/v1/answer_sets/:answer_set_id?include=client,choices` to the given callback.
