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