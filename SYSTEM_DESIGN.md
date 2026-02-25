# System Design – Task Management Application

## Objective

Build a Task Management application using:

- Ruby on Rails
- MySQL (Docker)
- Docker Compose
- RSpec

The application allows users to:
- Sign up and log in
- Create, view, update, and delete tasks
- Access tasks via RESTful API

---

## Architecture

The application follows MVC architecture.

User (Browser / Postman)
→ Routes
→ Controllers
→ Models (ActiveRecord)
→ MySQL Database

The system runs inside Docker:
- Rails container
- MySQL container

---

## Database Design

### Users Table

- id (bigint)
- name (string)
- email (string)
- password_digest (string)
- created_at (datetime)
- updated_at (datetime)

### Tasks Table

- id (bigint)
- title (string)
- priority (integer)
- status (integer)
- due_date (date)
- user_id (bigint)
- created_at (datetime)
- updated_at (datetime)

---

## Relationships

One User has many Tasks.

A Task belongs to one User.

---

## Features

User:
- Signup
- Login
- Logout

Task:
- Create
- Read
- Update
- Delete

Enums:
- priority: low, medium, high
- status: pending, in_progress, completed

---

## Security

- Strong parameters in controllers
- Passwords secured with bcrypt
- Tasks scoped to logged-in user

---

## Testing

RSpec will be used for:
- Model validation tests
- Controller tests
- API tests

---

## Summary

This application follows Rails best practices,
uses relational database design,
is containerized using Docker,
and implements full CRUD functionality with RESTful principles.