---
title: API Reference

language_tabs:
  - shell : Shell
  - javascript : JavaScript


toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>
  - <a href="https://shielded-ravine-63777.herokuapp.com/">Back to Incident Reporter</a>



search: true
---

# Introduction

Welcome to the IncidentReporter API! You can use our API to access IncidentReporter API endpoints.


# Incidents

## Get All Incidents

```shell
curl "https://shielded-ravine-63777.herokuapp.com/api/v1/incidents"
```

```javascript
$.ajax({
  method: "GET",
  url: "https://shielded-ravine-63777.herokuapp.com/api/v1/incidents",
})
  .done(function( data ) {
  });
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all incidents.

### HTTP Request

`GET https://shielded-ravine-63777.herokuapp.com/api/v1/incidents`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
order_by | <aside class="warning">Required</aside> | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — The full incident list will only !
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve
