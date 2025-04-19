# Secrets App with Google OAuth and Local Authentication

This project is a web application that allows users to securely register, log in, and view secrets. It uses **Google OAuth 2.0** for third-party authentication and **local authentication** with hashed passwords for user accounts.

## Features

- **User Registration**: Users can register with an email and password.
- **Local Authentication**: Passwords are securely hashed using `bcrypt`.
- **Google OAuth 2.0**: Users can log in using their Google accounts.
- **Session Management**: User sessions are managed using `express-session`.
- **Secrets Page**: Authenticated users can view a protected secrets page.
- **Logout Functionality**: Users can log out securely.

## Technologies Used

- **Backend**: Node.js, Express.js
- **Authentication**: Passport.js, Google OAuth 2.0
- **Database**: PostgreSQL
- **Templating Engine**: EJS
- **CSS Framework**: Custom CSS
- **Environment Variables**: `dotenv`

## Project Structure
   ```bash
    ├── .env                     # Environment variables
    ├── .gitignore               # Files ignored by Git
    ├── index.js                 # Main server file
    ├── package.json             # Project dependencies
    ├── public/                  # Static files (CSS, images, etc.)
    │   └── css/
    │       └── styles.css       # Custom CSS
    ├── views/                   # EJS templates
    │   ├── home.ejs             # Home page
    │   ├── login.ejs            # Login page
    │   ├── register.ejs         # Registration page
    │   ├── secrets.ejs          # Protected secrets page
    │   └── partials/            # Reusable components
    │       ├── header.ejs       # Header template
    │       └── footer.ejs       # Footer template
    └── README.md                # Project documentation
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/secrets-app.git
   cd secrets-app
2. Install dependencies:
   ```bash
   npm install
3. Set up the .env file: Create a .env file in the root directory and add the following:
   ```bash
   GOOGLE_CLIENT_ID=your-google-client-id
   GOOGLE_CLIENT_SECRET=your-google-client-secret
   SESSION_SECRET=your-session-secret
   PG_USER=your-postgres-username
   PG_HOST=localhost
   PG_DATABASE=your-database-name
   PG_PASSWORD=your-database-password
   PG_PORT=5432
4. Set up the database:
- Create a PostgreSQL database.
- Add a users table with the following schema
   ```bash
   CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
   );
5. Start the server:
   ```bash
   nodemon
6. Open the app in your browser
   ```bash
   http://localhost:3000

## Usage
- Register: Create an account using your email and password.
- Login: Log in using your credentials or Google account.
- Secrets: Access the protected secrets page after logging in.
- Logout: Log out to end your session.

## Environment Variables

The app uses the following environment variables:
| Variable               | Description                      |
|------------------------|----------------------------------|
| `GOOGLE_CLIENT_ID`     | Google OAuth Client ID           |
| `GOOGLE_CLIENT_SECRET` | Google OAuth Client Secret       |
| `SESSION_SECRET`       | Secret for session management    |
| `PG_USER`              | PostgreSQL username              |
| `PG_HOST`              | PostgreSQL Host Server           |
| `PG_DATABASE`          | PostgreSQL database name         |
| `PG_PASSWORD`          | PostgreSQL password              |
| `PG_PORT`              | PostgreSQL port (default: `5432`)|

## Dependencies
* bcrypt: For hashing passwords.
* body-parser: To parse incoming request bodies.
* dotenv: To manage environment variables.
* ejs: For rendering dynamic HTML templates.
* express: Web framework for Node.js.
* express-session: For session management.
* passport: Authentication middleware.
* passport-google-oauth20: Google OAuth 2.0 strategy for Passport.
* passport-local: Local authentication strategy for Passport.
* pg: PostgreSQL client for Node.js.

## Acknowledgments
* This project is part of the Udemy Course on session cookies and OAuth.
* Special thanks to the course instructor for guidance.