# NFL API

## Introduction

**FREE NFL API** This API will provide instant access to all NFL leagues and cups with latest game scores, odds, bookmakers, stats, standings and historical data.

## Authentication

The URL you need to use is the following: `[https://nfl-api1.p.rapidapi.com](https://nfl-api1.p.rapidapi.com)`
The API requires the headers listed below:

- **`x-rapidapi-host`**: `https://nfl-api1.p.rapidapi.com`
- **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here]([https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/financial-calculators/pricing](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/nfl-api1/pricing)).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

## Endpoints

The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

### Get Player IDs

Retrieves player IDs and basic information for a specific NFL team.

- **URL:** `/players/id`
- **Method:** GET
- **Query Parameters:**
  - `teamId` (required): The ID of the NFL team

#### Success Response

- **Code:** 200
- **Content:** JSON object containing an array of player data with the following structure:
  ```json
  {
    "data": [
      {
        "playerId": "string",
        "firstName": "string",
        "lastName": "string",
        "fullName": "string",
        "displayName": "string",
        "shortName": "string",
        "link": "string"
      },
      ...
    ]
  }

### Get Team IDs

Retrieves team IDs and basic information for NFL teams.

- **URL:** `/team/id`
- **Method:** GET
- **Query Parameters:**
  - `limit` (optional): The maximum number of teams to retrieve - default is 40

#### Success Response

- **Code:** 200
- **Content:** JSON array containing team data with the following structure:
  ```json
  [
    {
      "teamId": "string",
      "displayName": "string",
      "shortDisplayName": "string",
      "abbreviation": "string",
      "slug": "string",
      "link": "string"
    },
    ...
  ]

### Get NFL Game Play-by-Play

Retrieves the play-by-play data for a specified NFL game.

- **URL:** `/nflplay`
- **Method:** GET
- **Query Parameters:**
  - `id` (required): The ID of the NFL game

#### Success Response

- **Code:** 200
- **Content:** JSON object containing play-by-play data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Internal Server Error" }`

---

### Get NFL Game Box Score

Retrieves the box score data for a specified NFL game.

- **URL:** `/nflboxscore`
- **Method:** GET
- **Query Parameters:**
  - `id` (required): The ID of the NFL game

#### Success Response

- **Code:** 200
- **Content:** JSON object containing box score data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Internal Server Error" }`

---

### Get NFL Game Summary

Retrieves the summary data for a specified NFL game.

- **URL:** `/nflsummary`
- **Method:** GET
- **Query Parameters:**
  - `id` (required): The ID of the NFL game

#### Success Response

- **Code:** 200
- **Content:** JSON object containing game summary data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL PickCenter Data

Retrieves the PickCenter data for a specified NFL game.

- **URL:** `/nflpicks`
- **Method:** GET
- **Query Parameters:**
  - `id` (required): The ID of the NFL game

#### Success Response

- **Code:** 200
- **Content:** JSON object containing PickCenter data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Game Predictions

Retrieves predictions for a specified NFL game.

- **URL:** `/game/predictions`
- **Method:** GET
- **Query Parameters:**
  - `eventId` (required): The ID of the NFL game event

#### Success Response

- **Code:** 200
- **Content:** JSON object containing game prediction data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`


### Get Game Scoring Plays

Retrieves scoring plays for a specific game.

- **URL:** `/game/soringplays`
- **Method:** GET
- **Query Parameters:**
  - `eventId` (required): The ID of the game event

#### Success Response

- **Code:** 200
- **Content:** JSON object containing scoring plays data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get Game Videos

Retrieves videos associated with a specific game.

- **URL:** `/game/videos`
- **Method:** GET
- **Query Parameters:**
  - `eventId` (required): The ID of the game event

#### Success Response

- **Code:** 200
- **Content:** JSON object containing game videos data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get Game Articles

Retrieves news articles related to a specific game.

- **URL:** `/game/news`
- **Method:** GET
- **Query Parameters:**
  - `eventId` (required): The ID of the game event

#### Success Response

- **Code:** 200
- **Content:** JSON object containing game articles data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the id" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`


### Get NFL Schedule

Retrieves the NFL schedule data for a specified date.

- **URL:** `/nflschedule`
- **Method:** GET
- **Query Parameters:**
  - `year` (optional): Year (YYYY) - default is '2022'
  - `month` (optional): Month (MM) - default is '03'
  - `day` (optional): Day (DD)
  - `week` (optional): Week number - default is 1
  - `seasontype` (optional): Season type - default is 1
  - `current` (optional): Boolean to get current schedule - default is false

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL schedule data

#### Error Response

- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Scoreboard

Retrieves the NFL scoreboard data for a specified date.

- **URL:** `/nflscoreboard`
- **Method:** GET
- **Query Parameters:**
  - `year` (required): Year (YYYY)
  - `month` (required): Month (MM)
  - `day` (required): Day (DD)
  - `limit` (optional): Result limit - default is 200

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL scoreboard data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the year, month and day" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Standings

Retrieves the team standings for the NFL.

- **URL:** `/nflstandings`
- **Method:** GET
- **Query Parameters:**
  - `year` (required): Year (YYYY)
  - `group` (optional): Group type ('league', 'conference', or 'division') - default is 'league'

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL standings data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the year" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Team List

Retrieves the list of all NFL teams and their identification info for ESPN.

- **URL:** `/nflteamlist`
- **Method:** GET

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL team list data

#### Error Response

- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Internal Server Error" }`

---

### Get NFL Team Info

Retrieves the team info for a specific NFL team.

- **URL:** `/nflteaminfo`
- **Method:** GET
- **Query Parameters:**
  - `teamid` (required): The ID of the NFL team

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL team info data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the teamid" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Team Players

Retrieves the players for a specific NFL team.

- **URL:** `/nflteamplayers`
- **Method:** GET
- **Query Parameters:**
  - `teamid` (required): The ID of the NFL team

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL team players data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the teamid" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`


### Get NFL News

Retrieves the latest NFL news.

- **URL:** `/nfl-news`
- **Method:** GET

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL news data

#### Error Response

- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Player Statistics

Retrieves statistics for a specific NFL player.

- **URL:** `/nfl-player-statistic`
- **Method:** GET
- **Query Parameters:**
  - `playerId` (required): The ID of the NFL player

#### Success Response

- **Code:** 200
- **Content:** JSON object containing player statistics

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the playerId" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Team Statistics

Retrieves statistics for a specific NFL team.

- **URL:** `/nfl-team-statistic`
- **Method:** GET
- **Query Parameters:**
  - `teamId` (required): The ID of the NFL team

#### Success Response

- **Code:** 200
- **Content:** JSON object containing team statistics

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the teamId" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Injuries

Retrieves NFL injuries for the current season.

- **URL:** `/nfl-injuries`
- **Method:** GET

#### Success Response

- **Code:** 200
- **Content:** JSON object containing NFL injuries data

#### Error Response

- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Schedule by Team

Retrieves the NFL schedule for a specific team.

- **URL:** `/nfl-schedule-team`
- **Method:** GET
- **Query Parameters:**
  - `season` (optional): Season year - default is '2023'
  - `teamId` (required): The ID of the NFL team

#### Success Response

- **Code:** 200
- **Content:** JSON object containing team schedule data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the teamId" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Get NFL Weekly Schedule

Retrieves the NFL weekly schedule.

- **URL:** `/nfl-schedule-weekly`
- **Method:** GET
- **Query Parameters:**
  - `year` (optional): Year - default is '2023'
  - `week` (optional): Week number - default is 1
  - `seasonType` (optional): Season type - default is 2

#### Success Response

- **Code:** 200
- **Content:** JSON object containing weekly schedule data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "message": "Please provide the year" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something wrong: [error message]", "code": [error code] }`

---

### Search NFL Players

Searches for NFL players based on a query.

- **URL:** `/search`
- **Method:** GET
- **Query Parameters:**
  - `query` (required): Search query
  - `limit` (optional): Result limit - default is '50'
  - `page` (optional): Page number - default is '1'

#### Success Response

- **Code:** 200
- **Content:** JSON object containing search results

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "error": "Please provide the query" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "Something went wrong: Please Try again later or change the parameters!" }`

---

### Get NFL Player Splits

Retrieves splits data for a specific NFL player.

- **URL:** `/player-splits`
- **Method:** GET
- **Query Parameters:**
  - `playerId` (required): The ID of the NFL player
  - `season` (optional): Season year - default is '2023'
  - `type` (optional): League type ('nfl' or 'college-football') - default is 'nfl'

#### Success Response

- **Code:** 200
- **Content:** JSON object containing player splits data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "error": "Please enter the playerId" }` or `{ "error": "Invalid Type. Please choose from college-football or nfl." }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "[error message]" }`

---

### Get NFL Player Game Log

Retrieves game log data for a specific NFL player.

- **URL:** `/player-game-log`
- **Method:** GET
- **Query Parameters:**
  - `playerId` (required): The ID of the NFL player
  - `season` (optional): Season year - default is '2023'
  - `type` (optional): League type ('nfl' or 'college-football') - default is 'nfl'

#### Success Response

- **Code:** 200
- **Content:** JSON object containing player game log data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "error": "Please enter the playerId" }` or `{ "error": "Invalid Type. Please choose from college-football or nfl." }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "[error message]" }`

---

### Get NFL Player Overview

Retrieves an overview of a specific NFL player.

- **URL:** `/player-overview`
- **Method:** GET
- **Query Parameters:**
  - `playerId` (required): The ID of the NFL player

#### Success Response

- **Code:** 200
- **Content:** JSON object containing player overview data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "error": "Please enter the playerId" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "[error message]" }`

---

### Get NFL Player Bio

Retrieves biographical information for a specific NFL player.

- **URL:** `/player-bio`
- **Method:** GET
- **Query Parameters:**
- 
- 
  - `playerId` (required): The ID of the NFL player

#### Success Response

- **Code:** 200
- **Content:** JSON object containing player bio data

#### Error Responses

- **Code:** 400 BAD REQUEST
  - **Content:** `{ "error": "Please enter the playerId" }`
- **Code:** 500 INTERNAL SERVER ERROR
  - **Content:** `{ "error": "[error message]" }`


---

### 1. Get Team Leaders
**Endpoint:** `/team/leaders`

- **Method:** `GET`
- **Description:** Retrieves the top players (leaders) of a specified team for a given season.
- **Query Parameters:**
  - `teamId` (string, required): The ID of the team.
  - `limit` (number, optional, default = 5): The maximum number of players to retrieve.
  - `season` (string, optional, default = '2021'): The season year.
- **Response:**
  - `200 OK`: Returns a JSON object containing the team leaders data.
  - `400 Bad Request`: If `teamId`, `limit`, or `season` are missing or invalid.
  - `500 Internal Server Error`: If there is an error processing the request.
  
```json
{
  "data": [
    {
      "playerId": "123",
      "name": "Player Name",
      "position": "Position",
      "stats": {...}
    }
    // Additional players...
  ]
}
```
---
### Endpoint: `GET /team/transactions`

This endpoint retrieves transaction details for a specific sports team based on the provided `teamId` and `year`. The response includes the team's transactions for the specified year.

#### **Query Parameters**
- `teamId` *(required)*: The unique identifier for the team whose transactions you want to retrieve.
- `year` *(optional, default: '2024')*: The year for which the transactions are being requested.

#### **Responses**
- **200 OK**: 
  - Returns the transaction data for the specified team and year.
  - If the data is already cached, the response is served from the cache.
- **400 Bad Request**: 
  - Returned if either `teamId` or `year` is not provided in the request.
- **500 Internal Server Error**: 
  - Returned if there is an error while fetching the transaction data.

#### **Caching**
- If the data is available in the cache, it will be returned immediately to improve performance. 

#### **Example Request**
```http
GET /team/transactions?teamId=14&year=2024
```
---
### Endpoint: `GET /team/injuries`

This endpoint retrieves the injury details for a specific sports team based on the provided `teamId`. The response includes the team's current injury report.

#### **Query Parameters**
- `teamId` *(required)*: The unique identifier for the team whose injury report you want to retrieve.

#### **Responses**
- **200 OK**: 
  - Returns the injury data for the specified team.
  - If the data is already cached, the response is served from the cache.
- **400 Bad Request**: 
  - Returned if the `teamId` is not provided in the request.
- **500 Internal Server Error**: 
  - Returned if there is an error while fetching the injury data.

#### **Caching**
- If the data is available in the cache, it will be returned immediately to improve performance.

#### **Example Request**
```http
GET /team/injuries?teamId=14

```
### Endpoint: `GET /team/depth`

This endpoint retrieves the depth chart for a specific sports team based on the provided `teamId`. The response includes the current depth chart of the team.

#### **Query Parameters**
- `teamId` *(required)*: The unique identifier for the team whose depth chart you want to retrieve.

#### **Responses**
- **200 OK**: 
  - Returns the depth chart data for the specified team.
  - If the data is already cached, the response is served from the cache.
- **400 Bad Request**: 
  - Returned if the `teamId` is not provided in the request.
- **500 Internal Server Error**: 
  - Returned if there is an error while fetching the depth chart data.

#### **Caching**
- The response is cached using a unique key generated from the `teamId` parameter. If the data is available in the cache, it will be returned immediately to improve performance.

#### **Example Request**
```http
GET /team/depth?teamId=14
