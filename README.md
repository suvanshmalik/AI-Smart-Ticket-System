# Suvansh Smart Ticket System

## Overview

This project is a basic support ticket triage system that classifies user queries and assigns a priority level. It is designed to simulate how customer support systems handle incoming tickets.

The system takes user input, analyzes it using simple keyword-based rules, and returns:

* A category (Billing, Security, Account, or General)
* A priority level (P0, P1, P2)

All submitted tickets are stored in a SQLite database and can be viewed in the interface.

---

## Features

* User login (frontend validation)
* Ticket submission and analysis
* Automatic category detection
* Priority assignment based on urgency
* Storage of tickets in SQLite database
* Display of previous tickets
* Dark/light theme toggle in UI
* Basic animations and responsive design
* Backend containerization using Docker

---

## Tech Stack

Frontend:

* HTML
* CSS
* JavaScript

Backend:

* Node.js
* Express.js

Database:

* SQLite

Other Tools:

* Docker

---

## Project Structure

AI-Project/

Backend/

* server.js
* package.json
* tickets.db
* Dockerfile

Frontend/

* index.html
* script.js

README.md

---

## How to Run

### Option 1: Without Docker

1. Open terminal and go to Backend folder:
   cd Backend

2. Install dependencies:
   npm install

3. Start the server:
   node server.js

4. Open the frontend:
   Open Frontend/index.html in browser

---

### Option 2: Using Docker

1. Build the Docker image:
   docker build -t ticket-app .

2. Run the container:
   docker run -p 5000:5000 ticket-app

---

## API Endpoint

POST /tickets/analyze

Request body:
{
"message": "User issue text"
}

Response:
{
"category": "Billing",
"priority": "P0"
}

---

## Example Inputs

* "Refund not received urgent" → Billing, P0
* "My account was hacked" → Security, P0
* "Cannot login to my account" → Account, P1
* "General query" → General, P2

---

## Working Logic

The system uses simple keyword matching:

* Billing: refund, payment
* Security: hacked, breach
* Account: login, password
* Urgency words: urgent, immediately → higher priority

---

## Challenges Faced

* Handling Docker setup and container errors
* Fixing SQLite database schema mismatch
* Connecting frontend with backend correctly
* Debugging API issues

---

## Future Improvements

* Replace rule-based system with machine learning model
* Add proper backend authentication
* Improve UI using frameworks like React
* Deploy the project online

---

## Author

Suvansh Malik
ECE (AI/ML) Student

---

## Conclusion

This project demonstrates a simple full-stack application with frontend, backend, database integration, and deployment using Docker.
