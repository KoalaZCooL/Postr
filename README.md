# Postr
This project is a RESTful API to demonstrate an application that can post a text information to the internet anonymously and let the community engage that post.

## Table of contents
* [General info](#general-info)
* [Scope](#scope)
* [Endpoints](#endpoints)
* [Tech](#technologies)
* [Setup](#setup)

## General info
The app will have 3 screens:
* Timeline or newsfeed screen
* Create a new post screen
* Reply to a post screen
  
The app will have following abilities:
* Every user will have unique and random handler (username)
* Create post a text with maximum character length: 100
* Reply users’ posts with maximum character length: 100
* List all users’ newest posts with infinite scroll capabilities

## Scope
* no screens implementd as this is a RESTful API, not a REST Client
* random unique handler would be generated, assuming the REST Client stores it for further requests
* limit depth of replies to just 1 deep
* no user mentioning/hyperlinking/autocomplete
* limit infinite scroll to 40 results for each request (paginate)
* can show reply count in timeline feeds
* no search

## Endpoints
| Method | URL                                       | Request payload | Description                                             |
| ------ | ----------------------------------------- | --------------- | ------------------------------------------------------- |
|   GET  | /api/v1/handler                           |         -       | create a new random handler                             |
|   GET  | /api/v1/news/feed?next={timestamp_micro}  |         -       | returns top-level posts in timeline order, paginated    |
|  POST  | /api/v1/news/create                       | news, handler   | create a text information (news)                        |
|   GET  | /api/v1/news/{newsId}                     |         -       | shows a news and its replies                            |
|  POST  | /api/v1/news/{newsId}/reply               | reply, handler  | reply to a news, max 100 chars                          |

## Technologies
Project is created with:
* NodeJS: 20.5
* mongodb: 6.0.8
* 
	
## Setup
To run this project, install it locally using npm:

```
$ npm install
$ npm start
```
