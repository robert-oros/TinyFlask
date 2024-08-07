# TinyFlask

TinyFlask is a lightweight, Flask-inspired web framework for Python. It provides a simple way to create web applications with routing capabilities and support for different server configurations.

> Note: The original repository for this project was hosted on a private Bitbucket account within an organization, but access was lost. Consequently, a new repository has been established to continue development and maintain the application.

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)

## Features

- Simple routing decorator syntax
- Support for GET, POST, PUT, DELETE, and PATCH HTTP methods
- URL parameter handling
- Configurable server options (single-threaded or multi-threaded)
- Command-line argument parsing for server configuration

## Project Structure

The project consists of three main files:

1. `tinyflask.py`: Contains the core functionality of the TinyFlask framework
2. `config.py`: Handles server configuration and command-line argument parsing
3. `server.py`: An example server implementation using TinyFlask

## Installation

Clone the repository and navigate to the project directory:
```bash
git clone https://github.com/yourusername/tinyflask.git
cd tinyflask
```

## Usage

1. Create a new Python file (e.g., `app.py`) and import TinyFlask:

    ```python
    from tinyflask import TinyFlask, Identificator
    app = TinyFlask(__name__)
    ```

2. Define your routes using the `@app.route` decorator:

    ```python
    @app.route("/hello", method="GET")
    def hello(self):
        print("Hello, World!")

    @app.route("/user/<id>", method="GET")
    def user(self):
        identificator = Identificator()
        user_id = identificator.get_value_of("id")
        print(f"User ID: {user_id}")
    ```

3. Run your application:
    ```python
    app.run()
    ```

4. Start the server by running your Python file:
    ```bash
    python app.py
    ```

## Configuration

You can configure the server using command-line arguments:

- `-t` or `--type`: Specify server type (ONE_THREAD or MULTI_THREADED)
- `-p` or `--port`: Specify the port number
- `-host` or `--host`: Specify the host address

Example:
```bash
python app.py -t MULTI_THREADED -p 8080 -host 0.0.0.0
```