# Resources

## Resources URIs

Each resource has its own addresses or URIs mapped as follows :
- `GET http://api.diduenjoy.com/api/v1/:resource_type` - Retrieves as collection of resources
- `GET http://api.diduenjoy.com/api/v1/:resource_type/:id` - Retrieves a specific resource

### Examples
 
#### Retrieve all your responders
 
```javascript
// GET http://api.diduenjoy.com/api/v1/clients
{
  "data": [
    {
      "type": "clients",
      "id": "4085f919-82ba-42c2-8a32-2a854f6bcd28",
      "attributes": {
        "created_at": "2015-07-01T16-06-01.123Z",
        "updated_at": "2015-07-01T16-06-01.123Z",
        "email": "test-client@test-domain.com"
      },
      ...
    },
    ...
   ]
 }
 ```
 
#### Retrieve a specific responder
 
```javascript
// GET http://api.diduenjoy.com/api/v1/clients/4085f919-82ba-42c2-8a32-2a854f6bcd28
{
  "data": {
    "type": "clients",
    "id": "4085f919-82ba-42c2-8a32-2a854f6bcd28",
    "attributes": {
      "created_at": "2015-07-01T16-06-01.123Z",
      "updated_at": "2015-07-01T16-06-01.123Z",
      "email": "test-client@test-domain.com"
    },
    ...
  }
 }
 ```