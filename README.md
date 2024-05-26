# FastAPI CRUD Application

This is a simple CRUD (Create, Read, Update, Delete) application built with FastAPI and PostgreSQL. The project uses Docker and Docker Compose to manage containerization.

## Table of Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Running Migrations](#running-migrations)
- [Contributing](#contributing)
- [License](#license)

## Requirements

Before you begin, ensure you have the following installed on your machine:

- [Docker](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Git](https://git-scm.com/)

## Installation

1. **Clone the repository**:

    ```sh
    git clone https://github.com/progdog/fastapi_crud.git
    cd fastapi_crud
    ```

2. **Create the `.env` file**:

    Create a `.env` file in the root of the project directory using your own credentials based on the .env.example file:

    ```env
    POSTGRES_USER={your db username}
    POSTGRES_PASSWORD={your db password}
    POSTGRES_DB={your database name}
    ```

3. **Build and start the Docker containers**:

    ```sh
    docker-compose up --build
    ```

    This command will build the Docker images and start the containers for the FastAPI application, PostgreSQL database, and pgAdmin.

4. **Access the application**:

    - FastAPI application: [http://localhost:8000](http://localhost:8000)
    - FastAPI automatic docs (Swagger UI): [http://localhost:8000/docs](http://localhost:8000/docs)
    - FastAPI alternative docs (ReDoc): [http://localhost:8000/redoc](http://localhost:8000/redoc)
    - pgAdmin: [http://localhost:80](http://localhost:80)

## Usage

After setting up the project and starting the Docker containers, you can interact with the FastAPI application using HTTP requests. You can use tools like `curl`, Postman, or the built-in Swagger UI to test the endpoints.

## Running Migrations

This project uses Alembic for database migrations. To create and apply migrations, follow these steps:

1. **Create a new migration**:

    ```sh
    poetry run alembic revision --autogenerate -m "Migration message"
    ```

2. **Apply the migration**:

    ```sh
    poetry run alembic upgrade head
    ```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.

## License

This project is licensed under the Apache 2.0 License. See the [LICENSE](https://www.apache.org/licenses/LICENSE-2.0.txt) file for details.


