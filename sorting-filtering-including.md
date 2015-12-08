# Sorting

You can sort your queries with the sort parameter :

```
http://api.diduenjoy.com/api/v1/:resource_type?sort=:attribute,...
```

### Examples

`GET http://api.diduenjoy.com/api/v1/answer_sets?sort=created_at,updated_at`

`GET http://api.diduenjoy.com/api/v1/clients?sort=-email`

# Filtering

You can filter you queries with the filter parameter :

```
GET http://api.diduenjoy.com/api/v1/:resource_type?filter[:attribute]=:value
```

### Examples

`GET http://api.diduenjoy.com/api/v1/clients?filter[email]=test@test.com`

# Including

You can include your resources relationships with the include parameter :

```
GET http://api.diduenjoy.com/api/v1/:resource_type?include=:relationships
```

### Examples

`GET http://api.diduenjoy.com/api/v1/answer_sets?include=client,choices`
