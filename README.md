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