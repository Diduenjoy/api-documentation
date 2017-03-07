# POST `/clients`

### Create a responder profile

## attributes

attribute          | description
------------- | -------------
__email__<br>_string (required)_ | client email

## Examples

### json

```javascript
// POST /api/v1/clients
{
  "data": {
      "type": "clients",
      "attributes": {
        "email": "example@example.com"
      }
    }
}
```