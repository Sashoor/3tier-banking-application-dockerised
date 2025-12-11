3-Tier Banking Application (Dockerised)

A fully dockerised three-tier banking application built with Java (Spring Boot), MySQL, and Docker Compose.
The project demonstrates how to containerise an application, orchestrate multiple services, and maintain persistent storage using Docker volumes.
It is designed to be easy to clone and run for learning or experimentation.

1. Overview

This application includes:

User registration and login

Secure password hashing using BCrypt

Account creation and balance display

Persistent MySQL storage

A simple Spring Boot web interface

All components run as Docker containers and are orchestrated using Docker Compose.

2. Architecture

The system is organised into three layers:

Presentation Layer

The front-end served by Spring Boot, providing pages for registration, login, and account viewing.

Application Layer

The Spring Boot back-end that handles authentication, business logic, and database communication.

Data Layer

A MySQL container that stores user and account information.
A Docker volume ensures data persists across container rebuilds and restarts.

A phpMyAdmin container is included to allow easy database inspection via a web UI.

3. Technologies Used

Java 17

Spring Boot

MySQL 8

Docker & Docker Compose

phpMyAdmin

BCrypt password hashing

Multi-stage Dockerfile

Docker volumes for persistence

4. Project Structure
project-root/
│
├── src/                     Spring Boot source code
├── Dockerfile               Multi-stage Docker build definition
├── docker-compose.yml       Service orchestration
├── pom.xml                  Maven configuration
└── README.md                Documentation

5. Running the Application
Step 1: Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

Step 2: Build and start the services
docker-compose up --build

Step 3: Access the services

Application:
http://localhost:8083

phpMyAdmin:
http://localhost:8081

Credentials for phpMyAdmin:

Server: mysql

Username: root

Password: Test@123

Step 4: Stop everything
docker-compose down


The MySQL database data will remain available thanks to the mysql-data Docker volume.

6. Security Notes

Passwords are stored securely using BCrypt hashing.

Database access is internal to the Docker network unless manually exposed.

Environment variables are used for configuration.
