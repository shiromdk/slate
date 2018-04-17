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

> The above command returns JSON structured like this:

```json
[
  {
    "status": "WIP"
  }
]
```

The operation to create a new user.

### HTTP Request

`POST http://localhost:9090/api/user`

### Request Body

Name | Required | Type | Description
--------- | ----------- | --------- | -----------
user_id | true | String | The id associated with the user
first_name | true | String | The users first name
last_name | true | String | The users last name
email | true | String | The users email address

## Get a Specific User
```shell
curl "http://localhost:9090/api/user/1"
```

> The above command returns JSON structured like this:

```json
[
  {
    "status": "WIP"
  }
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
curl "http://example.com/api/user/1/objectives"

```
> The above command returns JSON structured like this:

```json
[
  {
    "status": "WIP"
  }
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
> The above command returns JSON structured like this:

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
    "status": "WIP"
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
    "status": "WIP"
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
