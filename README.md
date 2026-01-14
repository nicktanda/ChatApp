# Chat App

A Rails 8 application with PostgreSQL and simple session-based authentication.

## Requirements

- Ruby 3.3.4
- PostgreSQL
- Node.js (for asset compilation)

## Setup

1. Install dependencies:
   ```bash
   bundle install
   ```

2. Create and migrate the database:
   ```bash
   bin/rails db:create
   bin/rails db:migrate
   ```

3. Start the server:
   ```bash
   bin/rails server
   ```

4. Visit `http://localhost:3000`

## Features

### Authentication

The app includes a simple session-based authentication system:

- **Sign up** (`/signup`) - Create a new account with email and password
- **Log in** (`/login`) - Authenticate with existing credentials
- **Log out** (`/logout`) - End the current session

### Helper Methods

Available in controllers and views:

- `current_user` - Returns the logged-in user or `nil`
- `logged_in?` - Returns `true` if a user is logged in
- `require_login` - Before action to restrict access to authenticated users

## Database

PostgreSQL is used for all environments. Database configuration is in `config/database.yml`.

| Environment | Database Name |
|-------------|---------------|
| Development | chat_app_development |
| Test | chat_app_test |
| Production | chat_app_production |

For production, set these environment variables:
- `DATABASE_USERNAME`
- `DATABASE_PASSWORD`
- `DATABASE_HOST` (defaults to localhost)

## Testing

```bash
bin/rails test
```

## Linting

```bash
bin/rubocop
```
