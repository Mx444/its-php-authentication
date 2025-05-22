# PHP Authentication System - ITS Steve Jobs Academy

This repository contains a PHP authentication system developed during the course at ITS Steve Jobs Academy. The system implements secure authentication functionality using JWT (JSON Web Tokens) and bcrypt encryption for password management.

## Repository Structure

The repository is organized into thematic folders:

- **src/auth/**: Authentication components
  - **auth.router.php**: Router to handle authentication requests
  - **config/**: JWT configurations
  - **controllers/**: Controllers for request handling
  - **providers/**: Services for authentication, JWT, and encryption
  - **repositories/**: Database access for authentication operations

- **src/database/**: Database connection management
  - **providers/**: Providers for connection and transactions

- **src/utilis/**: Utility functions
  - **regex.utilis.php**: Email and password validation

- **vendor/**: External dependencies
  - Firebase JWT
  - PHPDotEnv
  - Other support packages

## Main Features

### User Authentication

- Registration with email and password validation
- Login with JWT token generation
- Password protection with bcrypt

### JWT Token Management

- Secure token generation
- Token validation
- Customizable configuration

### Security

- Input validation
- Protection against SQL injection
- Secure password management
- Soft delete for user records

## How to Use the System

### Prerequisites

- PHP 7.4 or higher
- Composer
- MySQL Database

### Configuration

1. Clone the repository
2. Install dependencies:

```bash
composer install
```

3. Create a `.env` file in the project root with the following variables:

```
DB_HOST=localhost
DB_USER=username
DB_PASSWORD=password
DB_NAME=database_name
SECRET=your_jwt_secret
ISSUER=your_issuer
AUDIENCE=your_audience
EXP=3600
HEAD=your_header
LENGTH=16
SALT=10
```

### API Endpoints

#### Registration
```
POST /auth.router.php?action=register
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "Password1!"
}
```

#### Login
```
POST /auth.router.php?action=login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "Password1!"
}
```

## Main Components

### AuthService
Manages the business logic for authentication:

- User registration
- Login
- User data updates
- User deletion

### JwtService
Manages JWT token creation and validation:

- Token generation with custom payload
- Token validation
- Token expiration management

### BcryptProvider
Manages password encryption:

- Secure hash generation
- Password verification
- Random salt generation

### ConnectionProvider
Manages database connection:

- Singleton connection
- Connection error handling
- Connection closing

## Password Security Requirements

Passwords must contain:

- At least 6 characters
- At least one letter
- At least one number
- At least one special character

## Educational Objectives

This system was designed to:

- Understand fundamental web authentication concepts
- Implement security best practices
- Apply design patterns in PHP
- Develop RESTful APIs
- Use external libraries through Composer

---

*This repository was created as part of the educational journey at ITS Steve Jobs Academy.*