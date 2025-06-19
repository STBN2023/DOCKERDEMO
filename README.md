# Simple Dockerized Web App

This is a minimal Flask web application designed to run in a Docker container.

## Prerequisites

*   Docker installed and running on your system.

## Building the Docker Image

1.  Navigate to the directory containing the `Dockerfile` and application files.
2.  Run the following command to build the Docker image:
    ```bash
    docker build -t my-test-app .
    ```

## Running the Docker Container

1.  Once the image is built, run the container using the following command:
    ```bash
    docker run -p 5000:5000 my-test-app
    ```
    This command maps port 5000 of your host machine to port 5000 of the container.

2.  Open your web browser and navigate to `http://localhost:5000` (or `http://<your-docker-host-ip>:5000` if Docker is running on a remote machine or VM). You should see "Hello, Dockerized World!".

## Application Details

*   **`app.py`**: Contains the Flask application code. It serves a simple "Hello, Dockerized World!" message at the root URL (`/`).
*   **`requirements.txt`**: Lists the Python dependencies (Flask).
*   **`Dockerfile`**: Contains instructions to build the Docker image.
    *   It uses a slim Python 3.9 base image.
    *   Copies the application files into the `/app` directory in the image.
    *   Installs dependencies from `requirements.txt`.
    *   Exposes port 5000.
    *   Sets `FLASK_APP` and `FLASK_RUN_HOST` environment variables.
    *   Runs the Flask development server using `flask run`.
