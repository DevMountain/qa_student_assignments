# Postman API Scavenger Hunt

#### Target Time +/- 60 minutes

## Summary

You'll be using the API docs for two APIs to answer some questions!

## Setup

1. Open our hosted Star Wars API docs for review.
   - [https://github.com/DevMountain/swapi-json-server/blob/master/API_documentation.md](https://github.com/DevMountain/swapi-json-server/blob/master/API_documentation.md)
1. Open the Marvel API docs for review.
   - General
     [https://developer.marvel.com/documentation/generalinfo](https://developer.marvel.com/documentation/generalinfo)
   - Detailed
     [https://developer.marvel.com/docs](https://developer.marvel.com/docs)

> **Note:** For Marvel authenticate using the query string parameters in the
> table below.
>
> | key    | value                            |
> | ------ | -------------------------------- |
> | ts     | 123456789                        |
> | apikey | 0f1b7f910cd6edd72f2342e4acc21f44 |
> | hash   | b84e2d4eed78b68e4274deebd17c03a0 |

## Activity

Take the quiz! Below are a couple of working URLs to query the Marvel and Star
Wars DBs.

- https://gateway.marvel.com:443/v1/public/characters?ts=123456789&apikey=0f1b7f910cd6edd72f2342e4acc21f44&hash=b84e2d4eed78b68e4274deebd17c03a0&name=Thanos
  - Hits the `characters` endpoint, looks for a characters where `name=Thanos`.
- https://swapi.devmountain.com/planets?terrain_like=tundra
  - Hits the planets endpoint, and looks for matches where the `terrain`
    property contains "tundra".

## Submission

Submit your responses to this quiz direclty.

## Solution

This collection contains all of the correct api queries to get your answers.

- <a href="./Postman_API_Scavenger_Hunt.postman_collection.json" download>
  Postman API Scavenger Hunt Collection </a>
