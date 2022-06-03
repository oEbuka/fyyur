# Fyyur

Fyyur is a musical venue and artist booking site that facilitates the discovery and bookings of shows between local performing artists and venues. This site lets you list new artists and venues, discover them, and list shows with artists as a venue owner.

## Overview

### Tech Stack

Tech stack includes:

- **SQLAlchemy ORM** to be my ORM library of choice.
- **PostgreSQL** as my database of choice.
- **Python3** and **Flask** as my server-side language and server-side framework.
- **Flask-Migrate** for creating and running schema migrations.
- **HTML**, **CSS**, and **Javascript** with [Bootstrap 3](https://getbootstrap.com/docs/3.4/customize/) for the website's frontend.

### Main Files: Project Structure

```sh
├── README.md
├── app.py ***  Main driver of the app. Includes SQLAlchemy models.
├── config.py *** Database URLs, CSRF generation, etc
├── error.log
├── forms.py *** Web forms
├── requirements.txt *** Project dependencies.
├── static *** Website Frontend files.
│   ├── css
│   ├── font
│   ├── ico
│   ├── img
│   └── js
└── templates
    ├── errors
    ├── forms
    ├── layouts
    └── pages
```

## Getting Started

### Installation

Make sure to be in the root directory of the project and that you have Python 3.6 or above installed.

#### Create Virtual Environment

Run the following to create a virtual environment:

```bash
python3 -m venv env
```

Activate your newly created virtual environment by running:

```bash
source env/bin/activate
```

#### Installing Dependencies

To install all project's dependencies, simply run:

```bash
pip install -r requirements.txt
```

### Database Configuration

Make sure to have PostgreSQL installed, if it is not, execute:

```bash
sudo apt-get -y install postgresql
```

#### Create Database

First, start your PostgreSQL database server by running:

```bash
sudo service postgresql start
```

Then, create your project's database by running:

```bash
createdb <database_name>
```

Lastly, add your database connection string as an environment variable by executing:

```bash
export DB_CONN_STR=<db_connection_string> # e.g. postgresql://username:password@localhost:5432/database
```

#### Apply Database Schema

Using migrations, apply the database schema and relationships by executing:
```psql
~psql
db.create_all()
```
```bash
flask db migrate
flask db upgrade
```

### Running the Server

Prepare the development environment by executing:

```bash
set FLASK_APP=app
set FLASK_ENV=development
```

To run the server at any time, use:

```bash
flask run
```

This will run the server on [http://localhost:5000](http://localhost:5000) in development mode.
