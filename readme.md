# Polls Application API

## Description
This is a simple API for a polls application. It allows users to create polls, vote on polls, and view poll results in real time. Project is built using Node.js, Fastify, and Prisma ( Postgres and Redis).

Project idea is made by [Rocketseat 💜](https://rocketseat.com.br/).

## How to run

### Prerequisites
- Node.js
- Docker
- REST Client (like Insomnia or Postman)

### Steps
1. Clone the repository
2. Install the dependencies
   - `npm install` or `yarn install` or `pnpm install`
3. Run the database
   - `docker-compose up -d`
4. Copy the `.env.example` file to `.env` and fill in the environment variables
   - `cp .env.example .env`
5. Run the migrations
   - `npx prisma migrate dev` or `yarn prisma migrate dev` or `pnpm prisma migrate dev`
6. Run the application
   - `npm run dev` or `yarn dev` or `pnpm dev`
7. Access the API with the REST Client
   - `localhost:3333/polls` 
8. Enjoy!

### Extra Step for Insomnia Users
- Import the `Insomnia_2024-02-07.json` file to your Insomnia, it will make all route request spaces.

## Routes
- `POST /polls` - Create a new poll
  - Request body:
    ```json
    {
      "title": "What is your favorite programming language?",
      "options": [
        "JavaScript",
        "TypeScript",
        "Python",
        "Java"
      ]
    }
    ```
  - Response body:
   ```json
   {
      "pollId":"uuid"
   }
   ```

- `GET /polls/:pollId` - Get data from a poll
  - Response body:
    ```json
    {
      "id": "uuid",
      "title": "What is your favorite programming language?",
      "options": [
        {
          "id": "uuid",
          "title": "JavaScript",
          "score": 0
        },
        {
          "id": "uuid",
          "title": "TypeScript",
          "score": 0
        },
        {
          "id": "uuid",
          "title": "Python",
          "score": 0
        },
        {
          "id": "uuid",
          "title": "Java",
          "score": 0
        }
      ]
    }
    ```

- `POST /polls/:pollId/votes` - Vote on a poll
  - Request body:
    ```json
    {
      "poolOptionId": "uuid"
    }
    ```

- `WS /polls/:pollId/results` - Real-time poll results
