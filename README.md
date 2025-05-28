# Flask API Application

A RESTful API built with Flask, SQLAlchemy, and JWT authentication, designed to run in Docker.

## Project Overview

This application provides a robust backend API with:
- User authentication using JWT tokens
- Database integration with SQLAlchemy
- API documentation with Swagger UI
- Containerization with Docker

## Getting Started

### Prerequisites

- Python 3.11+
- Docker and Docker Compose (for containerized deployment)
- Git

### Local Development Setup

1. Clone the repository
```bash
git clone <repository-url>
cd <project-directory>
```

2. Create and activate a virtual environment
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies
```bash
pip install -r requirements.txt
```

4. Set up environment variables
```bash
# The .flaskenv file contains basic Flask configuration
# You may need to create a .env file for sensitive information
```

5. Run the application
```bash
flask run
```

### Docker Deployment

#### Basic Docker Commands

1. Build the Docker image:
```bash
docker build -t flask-api .
```

2. Run the container:
```bash
docker run -p 5005:5000 flask-api
```

3. Run in background (daemon mode):
```bash
docker run -dp 5005:5000 flask-api
```

4. Run with live code syncing:
```bash
docker run -dp 5005:5000 -w /app -v "$(pwd):/app" flask-api
```

#### Using Docker Compose

1. Start the application:
```bash
docker compose up
```

2. Rebuild and restart:
```bash
docker compose up --build --force-recreate --no-deps python-app
```

## Debugging

For debugging with VS Code:
```bash
docker compose -f docker-compose.yml -f docker-compose.debug.yml up
```

The debugger will be available on port 5678. Use the "Python Debugger: Remote Attach" configuration in VS Code.

## API Documentation

Swagger UI is available at:
```
http://localhost:5005/swagger-ui
```

## Project Structure

- `app.py`: Main application entry point
- `db.py`: Database configuration
- `models/`: Database models
- `resources/`: API endpoints
- `schemas.py`: Serialization schemas
- `migrations/`: Database migrations
- `blocklist.py`: JWT token blocklist

## Database Migrations

This project uses Flask-Migrate for database migrations:

```bash
# Initialize migrations
flask db init

# Create a migration
flask db migrate -m "Initial migration"

# Apply migrations
flask db upgrade
```

## git
```bash
echo "# python-flask-rest-api" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/javedansari81/python-flask-rest-api.git
git push -u origin main
```