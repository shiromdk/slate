---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell


toc_footers:
  - WIP


includes:
  - errors

search: true
---

# Introduction

Vivid 2018 Gamification Backend

# User

## Create New User

```shell
curl "http://localhost:9090/api/user"
```

> The above command returns the user object as JSON structured like this:

```json
[
    {
      "_id":"5adebdbdae55f11a677f24a4",
      "user_id":"test@test.com",
      "email":"test@test.com"
    }
]
```

The operation to create a new user.

### HTTP Request

`POST http://localhost:9090/api/user`

### Request Body

Name | Required | Type | Description
--------- | ----------- | --------- | -----------
email | true | String | The users email address

## Get a Specific User
```shell
curl "http://localhost:8006/api/user/test@test.com"
```

> The above command returns the user object as  JSON structured like this:

```json
[
  [
      {
          "_id": "5adebdbdae55f11a677f24a4",
          "user_id": "test@test.com",
          "email": "test@test.com",
          "__v": 0
      }
  ]
]
```

This endpoint retrieves a specific user

<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->

### HTTP Request

`GET http://localhost:9090/api/user/<user_id>`

### URL Parameters

Parameter | Description
--------- | -----------
user_id | The ID of the user to retrieve

## Get a specific user's completed objectives

```shell
curl "http://localhost:8006/api/user/test@test.com/objectives"

```
> The above command returns as list of all the users completed objectives JSON structured like this:

```json
[
  [
      {
          "_id": "5adebe70ae55f11a677f24a5",
          "user_id": "test@test.com",
          "objective_id": "27166",
          "created_at": "2018-04-24T05:19:44.486Z",
          "__v": 0
      },
      {
          "_id": "5adebe70ae55f11a677f24a6",
          "user_id": "test@test.com",
          "objective_id": "3551",
          "created_at": "2018-04-24T05:19:44.486Z",
          "__v": 0
      }
  ]
]
```

This endpoint retrieves all the objectives/precincts that the user has visited

### HTTP Request

`GET http://example.com/api/user/<ID>/objectives`

### URL Parameters

Parameter | Description
--------- | -----------
user_id | The ID of the user to retrieve

## Get a specific user's completed objectives count

```shell
curl "http://example.com/api/user/1/objectives/count"

```
> The above command returns the count JSON:

```json
[
  {
    "count": "10"
  }
]
```

This endpoint returns the number of objectives/precincts the user has visited

### HTTP Request

`GET http://example.com/api/user/<ID>/objectives/count`

### URL Parameters

Parameter | Description
--------- | -----------
user_id | The ID of the user to retrieve

# Objective

## Create New User Objective Entry

```shell
curl "http://localhost:9090/api/objectives"
```

> The above command returns JSON structured like this:

```json
[
  {
    "_id":"5adebe70ae55f11a677f24a6",
    "user_id":"test@test.com",
    "objective_id":"3551",
    "created_at":"2018-04-24T05:19:44.486Z",
    "__v":0
  }
]
```

The operation to create a new user objective entry.

### HTTP Request

`POST http://localhost:9090/api/objective`

### Request Body

Name | Required | Type | Description
--------- | ----------- | --------- | -----------
user_id | true | String | The id associated with the user
objective_id| true | String | The id associated with the precinct

## Create New User Objective Entries

```shell
curl "http://localhost:9090/api/objectives"
```

> The above command returns JSON structured like this:

```json
[
  {
    "status":201,
    "description":"Objectives being parsed by server"
  }
]
```

The operation to create a batch of new user objective entries.

### HTTP Request

`POST http://localhost:9090/api/objective/batch`

### Request Body

Name | Required | Type | Description
--------- | ----------- | --------- | -----------
user_id | true | String | The id associated with the user
objective_id_list | true | Object | An array containing the objective ids of the locally stored precincts
