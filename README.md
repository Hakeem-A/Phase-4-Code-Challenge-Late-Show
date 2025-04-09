# Late Show API

A Flask REST API for managing late show episodes, guests, and their appearances.

## Project Description

This API manages data for a late-night show, tracking episodes, guests, and their appearances. It provides endpoints for creating, reading, updating, and deleting records for episodes, guests, and their appearances on the show.

## Features

- CRUD operations for Episodes, Guests, and Appearances
- RESTful API endpoints
- SQLite database with SQLAlchemy ORM
- Data serialization
- Rating system for guest appearances

## Technologies Used

- Flask
- Flask-RESTful
- Flask-SQLAlchemy
- Flask-Migrate
- SQLAlchemy-Serializer
- Faker (for seeding data)

## Installation

1. Clone the repository:
```bash
cd Phase-4-Code-Challenge-Late-Show
```

2. Install dependencies using Pipenv:
```bash
pipenv install
pipenv shell
```

3. Initialize the database:
```bash
flask db init
flask db migrate
flask db upgrade
```

4. Seed the database:
```bash
python seed.py
```

5. Run the application:
```bash
python run.py
```

## API Endpoints

### Episodes
- GET /episodes - List all episodes
- GET /episodes/<id> - Get specific episode
- POST /episodes - Create new episode
- PUT /episodes/<id> - Update episode
- PATCH /episodes/<id> - Partially update episode
- DELETE /episodes/<id> - Delete episode

### Guests
- GET /guests - List all guests
- GET /guests/<id> - Get specific guest
- POST /guests - Create new guest
- PUT /guests/<id> - Update guest
- PATCH /guests/<id> - Partially update guest
- DELETE /guests/<id> - Delete guest

### Appearances
- GET /appearances - List all appearances
- GET /appearances/<id> - Get specific appearance
- POST /appearances - Create new appearance
- PUT /appearances/<id> - Update appearance
- PATCH /appearances/<id> - Partially update appearance
- DELETE /appearances/<id> - Delete appearance

## Models

### Episode
- id: Integer (Primary Key)
- date: String
- number: Integer
- appearances: Relationship with Appearance

### Guest
- id: Integer (Primary Key)
- name: String
- occupation: String
- appearances: Relationship with Appearance

### Appearance
- id: Integer (Primary Key)
- rating: Integer (1-5)
- episode_id: Foreign Key (Episode)
- guest_id: Foreign Key (Guest)
