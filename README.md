# Forgot Password Implementation

The "Forgot Password Implementation" is a Java Spring Boot application that provides functionality for resetting passwords for users who have forgotten their passwords. It offers two main endpoints: one for initiating the password reset process and another for actually resetting the password.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [API Endpoints](#api-endpoints)
- [Usage](#usage)


## Prerequisites

Before you start, make sure you have the following installed:
- Java Development Kit (JDK)
- Apache Maven
- PostgreSQL (or another database of your choice)
- Git

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/ollyskay/forgot-password-implementation.git
   cd forgot-password-implementation

## Build and Run

To build and run the application, use the following command:

mvn spring-boot:run

## API Endpoints

The application provides the following API endpoints:

### POST /forgot-password

Initiates the password reset process.

**Parameters:**
- `email`: User's email for which the password is being reset.

**Example:**

POST http://localhost:8080/forgot-password
{
  "email": "user@example.com"
}

### PUT /reset-password

Resets the user's password.

**Parameters:**
- `token`: Token received from the `/forgot-password` request.
- `password`: New password to set.

***Example:***

PUT http://localhost:8080/reset-password?token=your-reset-token
{
  "password": "new-password"
}

## Prerequisites
- If the token is valid and not expired, the password will be updated.
- If the token is invalid or expired, an error message will be returned.

## Usage
Once you have obtained the token from the `/forgot-password` request, use it in the `/reset-password` request to set a new password for the user.

