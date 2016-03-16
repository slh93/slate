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

Currently, all endpoints can be accessed without any type of authorization header. 


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
  {"incidents":
    [
      {
        "id":1,
        "created_at":"2016-03-16T04:19:16.330Z",
        "detail":"Example details listed here",
        "location":"Halligan Hall, Medford, MA, United States",
        "title":"Broken Glass",
        "priority":"High",
        "img_url":null
      },
      {
        "id":2,
        "created_at":"2016-03-16T04:19:53.519Z",
        "detail":"More information",
        "location":"Latin Way Medford MA",
        "title":"Weird Smell",
        "priority":"Medium",
        "img_url":null
      }
    ]
  }
```

This endpoint retrieves all incidents.

### HTTP Request

`GET https://shielded-ravine-63777.herokuapp.com/api/v1/incidents`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
limit | False | 500 | Limits the number of incidents that are returned. Max:1000.
order_by | False | id | Options: id, created_by, date.

<aside class="success">
Remember — Try to limit the number of incidents you request to avoid slowing your page load time!
</aside>



## Get a Specific Incident

```shell
curl "https://shielded-ravine-63777.herokuapp.com/api/v1/incidents/[id]"
```

```javascript
$.ajax({
  method: "GET",
  url: "https://shielded-ravine-63777.herokuapp.com/api/v1/incidents/[id]",
})
  .done(function( data ) {
  });
```

> The above command returns JSON structured like this:

```json
{
  "id":2,
  "created_at":"2016-03-16T04:19:53.519Z",
  "detail":"More information",
  "location":"Latin Way Medford MA",
  "title":"Weird Smell",
  "priority":"Medium",
  "img_url":null
}
```

This endpoint retrieves a specific incident.


### HTTP Request

`GET https://shielded-ravine-63777.herokuapp.com/api/v1/incidents/[id]`

### URL Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
id | True | - | The ID for the incident to be retrieved



## Create a New Incident

```shell
curl --data "title=value1&detail=value2&location=value3&priority=value4"
      "https://shielded-ravine-63777.herokuapp.com/api/v1/incidents/new"
```

```javascript
$.ajax({
  method: "POST",
  url: "https://shielded-ravine-63777.herokuapp.com/api/v1/incidents/new",
  data: data_object,
  dataType: dataType
})
  .done(function( data ) {
  });


<aside class="success">
You should fill the data_object with the content to be posted to the endpoint
</aside>  
```

> The above command returns JSON structured like this:

```json
{
  "status":"success", 
  "id":[assigned ID]
}
```

This endpoint creates a new incident.


### HTTP Request

`POST https://shielded-ravine-63777.herokuapp.com/api/v1/incidents/new`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
title | True | - | The title for the new incident
detail | True | - | The detail for a new incident
location | True | - | The string value of a location
priority | True | - | Low, Medium, High
img_url | False | - | The url for an image to be associated with the incident


# Users

## Get All Users

```shell
curl "https://shielded-ravine-63777.herokuapp.com/api/v1/users"
```

```javascript
$.ajax({
  method: "GET",
  url: "https://shielded-ravine-63777.herokuapp.com/api/v1/users",
})
  .done(function( data ) {
  });
```

> The above command returns JSON structured like this:

```json
  {"incidents":
    [
      {
        "id":1,
        "created_at":"2016-03-16T04:19:16.330Z",
        "detail":"Example details listed here",
        "location":"Halligan Hall, Medford, MA, United States",
        "title":"Broken Glass",
        "priority":"High",
        "img_url":null
      },
      {
        "id":2,
        "created_at":"2016-03-16T04:19:53.519Z",
        "detail":"More information",
        "location":"Latin Way Medford MA",
        "title":"Weird Smell",
        "priority":"Medium",
        "img_url":null
      }
    ]
  }
```

This endpoint retrieves all users.

### HTTP Request

`GET https://shielded-ravine-63777.herokuapp.com/api/v1/users`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
limit | False | 500 | Limits the number of incidents that are returned. Max:1000.
order_by | False | id | Options: id, created_by, date.

<aside class="success">
Remember — Try to limit the number of incidents you request to avoid slowing your page load time!
</aside>

