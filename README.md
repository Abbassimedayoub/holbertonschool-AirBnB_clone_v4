# AirBnB Clone — v4 (Full Stack)

## Overview

Fourth and final iteration of the **AirBnB clone** project from the Holberton School curriculum: a complete full-stack web application. The front end (HTML5/CSS3 + jQuery) loads places dynamically from a **Flask REST API**, backed by **MySQL** through the **SQLAlchemy ORM**. The project also ships a command-line console to manage objects, unit tests, and deployment scripts.

This repository is my working copy of the project. The original codebase was developed by Holberton School students across the four project iterations (see `AUTHORS`).

## Architecture

| Component | Role |
|---|---|
| `console.py` | CLI to create, read, update and delete objects (dev tool) |
| `models/` | Business objects (User, Place, State, City, Amenity, Review) with two storage engines: FileStorage (JSON) and DBStorage (MySQL/SQLAlchemy) |
| `api/v1/` | Flask REST API exposing the objects (`app.py`, views) |
| `web_static/` | Static HTML/CSS prototypes |
| `web_flask/` | Server-side rendered pages (Flask + Jinja2) |
| `web_dynamic/` | Dynamic front end calling the API with jQuery/AJAX |
| `tests/` | Unit tests |
| `*-deploy_web_static.*` | Packaging and deployment scripts |

## Installation

```bash
sudo apt-get install libmysqlclient-dev
git clone https://github.com/Abbassimedayoub/holbertonschool-AirBnB_clone_v4.git
cd holbertonschool-AirBnB_clone_v4
pip install -r requirements.txt
```

Test fixtures are available in the SQL setup scripts (`setup_mysql_dev.sql`, `setup_mysql_test.sql`).

## Configuration

The application is configured through environment variables:

| Variable | Description |
|---|---|
| `HBNB_ENV` | Running environment (`dev` or `test`) |
| `HBNB_MYSQL_USER` / `HBNB_MYSQL_PWD` | MySQL credentials |
| `HBNB_MYSQL_HOST` / `HBNB_MYSQL_DB` | MySQL host and database |
| `HBNB_TYPE_STORAGE` | Storage engine: `file` or `db` |
| `HBNB_API_HOST` / `HBNB_API_PORT` | API host/port (default `0.0.0.0:5000`) |
| `HBNB_WEB_HOST` / `HBNB_WEB_PORT` | Web server host/port (default `0.0.0.0:5001`) |

## Usage

```bash
# Start the REST API
HBNB_MYSQL_USER=hbnb_dev HBNB_MYSQL_PWD=hbnb_dev_pwd HBNB_MYSQL_HOST=localhost \
HBNB_MYSQL_DB=hbnb_dev_db HBNB_TYPE_STORAGE=db python3 -m api.v1.app

# Start the dynamic web server (separate terminal)
HBNB_MYSQL_USER=hbnb_dev HBNB_MYSQL_PWD=hbnb_dev_pwd HBNB_MYSQL_HOST=localhost \
HBNB_MYSQL_DB=hbnb_dev_db HBNB_TYPE_STORAGE=db python3 -m web_dynamic.hbnb
```

## Tests

```bash
python3 -m unittest discover tests
```

## Skills Demonstrated

Full-stack architecture, REST API design with Flask, relational modeling with MySQL and the SQLAlchemy ORM, dual storage-engine abstraction, dynamic front-end integration (jQuery/AJAX), unit testing, and deployment scripting.

## Author

**Mohamed Ayoub Abbassi** — Holberton School Paris

- GitHub: [@Abbassimedayoub](https://github.com/Abbassimedayoub)
- LinkedIn: [mohamed-ayoub-abbassi](https://www.linkedin.com/in/mohamed-ayoub-abbassi)

Original project authors are listed in [`AUTHORS`](AUTHORS).

## License

This project is released under the [Unlicense](LICENSE).
