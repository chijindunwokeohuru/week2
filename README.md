# Week 2 DevOps Node.js & Express API

This repository contains the solution for the Week 2 DevOps assignment. It implements a Node.js Express API with custom logging middleware, JSON body parsing, route parameter parameters, request validation/error handling, and a premium static testing interface served at the root route.

## Features

- **Express App**: Handles requests and serves static assets.
- **GET /**: Serves a beautiful, interactive frontend testing dashboard.
- **POST /user**: Accepts JSON payload `{ name, email }` and responds with `"Hello, [name]!"`.
- **GET /user/:id**: Responds with `"User [id] profile"`.
- **JSON Parsing**: Built-in JSON body parser middleware.
- **Custom Request Logger**: Logs incoming HTTP requests with method, path, and ISO timestamp.
- **Error Handling**: Graceful error handling, including returning `400 Bad Request` for missing parameters in `/user` or malformed JSON payloads.
- **Environment Config**: Uses `.env` configuration (e.g., `PORT`).

---

## Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/chijindunwokeohuru/week2.git
   cd week2
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   Create a `.env` file from the example template:
   ```bash
   cp .env.example .env
   ```
   Modify `PORT` inside `.env` if desired (defaults to `3000`).

---

## Running the Application

- **Production mode**:
  ```bash
  npm start
  ```
- **Development mode** (with hot-reloading via `nodemon`):
  ```bash
  npm run dev
  ```

---

## Testing the API

### 1. Interactive UI Dashboard
Open your browser and navigate to `http://localhost:3000`. You will see a premium, animated glassmorphism web panel where you can test both the `POST` and `GET` routes interactively.

### 2. cURL
- **GET /user/:id**:
  ```bash
  curl -i http://localhost:3000/user/42
  ```
- **POST /user (Valid)**:
  ```bash
  curl -i -X POST -H "Content-Type: application/json" -d '{"name": "Alice", "email": "alice@example.com"}' http://localhost:3000/user
  ```
- **POST /user (Invalid - Missing Email)**:
  ```bash
  curl -i -X POST -H "Content-Type: application/json" -d '{"name": "Bob"}' http://localhost:3000/user
  ```
