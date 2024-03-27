# data-api-template

## Purpose

The objective of this project is to provide a standard template for creating a data API. 


It includes:

- The procedure for building a SQL database (SQLite).
- The procedure for importing data.
- An API (FastAPI) with token-based authentication.
- Endpoints for performing CRUD operations on the customers table.
- Testing of the endpoints related to CRUD operations and authentication.

## Setup

1. Create virtual environement and install requierements with Poetry:


```bash

pip install poetry

poetry config virtualenvs.in-project true
```

To generate the pyproject.toml file, you can use the following command:

```bash

poetry init 

```
Instead of adding manually the dependencies, you can use the requirements.txt that already exists in the project. Run the flollowing command:

```bash

poetry add $(cat requirements.txt)

```

To create the virtual environment and install the dependancies, run the following command:

```bash
poetry install
```

The file poetry.lock is generated, and the virtual environment is created in the .venv folder.

2. To create the Olist database, execute these two commands:

```bash
sqlite3 olist.db < database_building/create_table.sql

sqlite3 olist.db < database_building/import_table.sql 2>/dev/null
```

3. Creatre environment variables;

In the api folder, create a .env file with a SECRET_KEY variable

4. You can execute tests to make sure the setup is good:

```bash
pytest
```

5. Launch the API from the api folder:

```bash
python3 api/main.py
```

6. Use the API:

- check that the api is running from root /
- Go to /docs to use the api
- Use the "get cutomers" endpoint to test unprotected endpoint
- Create a User with a password and a username
- Authorize with the created user
- You can now use the protected endpoints

## Ressources:

- https://fastapi.tiangolo.com/tutorial/security/
- https://github.com/ArjanCodes/examples/tree/main/2023/fastapi-router
- https://github.com/ArjanCodes/examples/tree/main/2023/apitesting
