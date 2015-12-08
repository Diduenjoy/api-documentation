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
> 
> A sample test API key has been provided in all the examples on the page, so you can test out any example right away.
