# CyberGuard Flask Blog

CyberGuard Blog is a Flask-based blog project designed to provide a platform for users to create and share blog posts. This README provides instructions for setting up and running the project both locally and using Docker.

![img.png](app/static/readme1.jpg)
#
![img_1.png](app/static/readme2.jpg)
## 
![img_2.png](app/static/readme3.jpg)

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Python 3.x
- pip (Python package installer)
- Docker
- Docker Compose

## Environment Variables

The project uses environment variables for configuration. Set the following variables before running the project:

### Install Dependencies

Create a virtual environment and install the required Python packages:

```sh
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Apply Migrations

```sh
flask db migrate
flask db upgrade
```

### Run the Development Server

You can run the project either using `run.py` or via the Flask CLI.

#### Using run.py

```sh
python run.py
```

#### Using Flask CLI

```sh
flask run --port=8000
```

You should now be able to access the blog at `http://127.0.0.1:8000`.

## Docker Setup

### 1. Build and Run the Docker Containers

Make sure you have Docker and Docker Compose installed. Then, run the following commands:

```sh
docker-compose up --build
```

This command will build the Docker images and start the containers as defined in the `docker-compose.yml` file.

### 2. Import Data into MySQL Database

To import initial data, follow these steps:

1. Open your web browser and navigate to `http://localhost:8080`.
2. Log in to phpMyAdmin using the credentials specified in your `docker-compose.yml`.
3. Select the appropriate database.
4. Navigate to the `Import` tab.
5. Choose the SQL file from the [DB.sql](DB.sql) directory and start the import.

## Additional Notes

- Make sure to configure your `config.py` file according to your environment (e.g., database settings, secret key, etc.).
- Use the `.env` file to manage sensitive data and environment-specific configurations.