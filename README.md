# Diduenjoy - API Documentation (WIP)

## API Reference

The Diduenjoy API is organized around [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) and [JSON API](http://jsonapi.org/).
Our API is designed to have predictable, resource-oriented URLs and to use HTTP response codes to indicate API errors. We use built-in HTTP features, like HTTP authentication and HTTP verbs, which can be understood by off-the-shelf HTTP clients, and we support cross-origin resource sharing to allow you to interact securely with our API from a client-side web application (though you should remember that you should never expose your secret API key in any public website's client-side code). JSON will be returned in all responses from the API, including errors.

> ### API Endpoint
> 
> ``` http://api.diduenjoy.com/api/v1 ```

## Authentication

You authenticate to the Diduenjoy API by providing your secret API key in the request.
Your API keys carry many privileges, so be sure to keep them secret!

Authentication to the API occurs via HTTP Basic Auth. Provide your API key as the basic auth username. You do not need to provide a password.

> ### Example Request
> 
> ```bash
> curl 'http://api.diduenjoy.com/api/v1/surveys' \
>  -u '336e7e08-e7c8-4814-8a82-56e643b72382:'
>  ```
> 
> curl uses the -u flag to pass basic auth credentials (adding a colon after your API key will prevent it from asking you for a password).

## Methods

method | endpoint | description
------ | -------- | -----------
GET  | [`/api/v1/answer_sets`](methods/GET%20answer_sets%20collection) | List all your answer_sets
GET  | [`/api/v1/answer_sets/:id`](methods/GET%20answer_sets%resource) | Get a single answer_set
GET | [`/api/v1/choices/:id`](methods/GET%choices%resource) | Get a single choice
GET | [`/api/v1/clients`](methods/GET%clients%20collection) | List all your responders
GET | [`/api/v1/clients/:id`](methods/GET%clients%resource) | Get a single responder
GET | [`/api/v1/companies`](methods/GET%companies%20collection) | Get all your companies
GET | [`/api/v1/companies/:id`](methods/GET%companies%resource) | Get a single company
POST | [`/api/v1/dispatches`](methods/GET%dispatches%resource) | Send a survey to a specified email address
GET | [`/api/v1/languages`](methods/GET%languages%20collection) | List all languages available for survey responders
GET | [`/api/v1/languages/:id`](methods/GET%languages%resource) | Get a language available for survey responders
GET | [`/api/v1/questions/:id`](methods/GET%questions%resource) | Get a single question
GET | [`/api/v1/survey_languages/:id`](methods/GET%survey_languages%resource) | Get a single survey_language
GET | [`/api/v1/surveys`](methods/GET%surveys%20collection) | List all your surveys
GET | [`/api/v1/surveys/:id`](methods/GET%surveys%resource) | Get a single survey
