# GCP DevOps Project

This repository hosts a simple Python Flask application designed for a GCP DevOps pipeline project. It includes a Dockerfile for containerization.

## Project Structure

- `app.py`: The main Flask application.
- `Dockerfile`: Instructions to build the Docker image.
- `requirements.txt`: Python dependencies.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine.

## Getting Started

### Build the Docker Image

To build the Docker image, run the following command in the project root:

```bash
docker build -t gcp-project .
```

### Run the Container

Run the container using the built image:

```bash
docker run -p 8080:8080 gcp-project
```

The application will be accessible at `http://localhost:8080`.

## API Endpoints

- `/`: Returns "Hello World!" or a custom target if the `TARGET` environment variable is set.
