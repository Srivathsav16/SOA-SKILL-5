SOA Skill 5 – Securing APIs with CORS

Technologies Used
- Java 17
- Spring Boot
- Spring Web
- Maven
- HTML
- JavaScript
- Python HTTP Server
- Google Chrome Developer Tools
- Git & GitHub

Project Architecture:
Frontend
http://localhost:5500
        |
        | GET /profile
        ↓
Spring Boot REST API
http://localhost:8080
        |
        ↓
CORS Configuration

Project Structure:
SOA-SKILL-5/
│
├── cors-api/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── com/example/corsapi/
│   │       │       ├── CorsApiApplication.java
│   │       │       ├── controller/
│   │       │       │   └── ProfileController.java
│   │       │       └── config/
│   │       │           └── CorsConfig.java
│   │       │
│   │       └── resources/
│   │           └── application.properties
│   │
│   └── pom.xml
│
└── cors-frontend/
    └── index.html
Backend Configuration
The backend runs on port 8080.

application.properties:
server.port=8080
spring.application.name=cors-api

REST API

The project provides the following endpoint:

GET http://localhost:8080/profile

Response:
Profile API accessed successfully

CORS Configuration

CORS is configured to allow requests from:

http://localhost:5500

Allowed HTTP methods:

GET
POST
PUT
DELETE

Frontend

The frontend uses HTML and JavaScript to call the backend API.

fetch('http://localhost:8080/profile')
    .then(response => response.text())
    .then(data => {
        document.getElementById('result').innerText = data;
    });

The frontend is hosted on:

http://localhost:5500

How to Run the Project:

1. Start the Backend

Open the cors-api project in Spring Tool Suite.

Run:

Run As → Spring Boot App

The backend will start on:
http://localhost:8080

Test the API:
http://localhost:8080/profile

2. Start the Frontend

Open a terminal in the cors-frontend directory.

Run:
python -m http.server 5500


Open:
http://localhost:5500

Open index.html and click Get Profile.

Result:
The REST API was successfully developed and tested from a frontend hosted on a different origin. CORS was configured to allow a specific origin and required HTTP methods, enabling successful cross-origin communication.
