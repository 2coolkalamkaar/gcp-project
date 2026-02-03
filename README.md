# GCP DevOps Project

This repository hosts a simple Python Flask application designed for a GCP DevOps pipeline project. It includes a Dockerfile for containerization.

## Project Structure

- `app.py`: The main Flask application.
- `Dockerfile`: Instructions to build the Docker image.
- `requirements.txt`: Python dependencies.
- `cloudbuild.yaml`: Google Cloud Build configuration file.
- `gke.yaml`: Kubernetes Deployment manifest.
- `service.yaml`: Kubernetes Service manifest.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine.
- Google Cloud Platform (GCP) account.

## GCP Environment Setup

To ensure the CI/CD pipeline runs smoothly on Google Cloud Platform, please ensure the following:

1.  **Enable APIs**:
    - Enable the **Cloud Build API**.

2.  **Service Account Permissions**:
    Ensure the Cloud Build Service Account (or the service account used for the build) has the following IAM roles:
    - `roles/container.developer` (Kubernetes Engine Developer)
    - `roles/storage.admin` (Storage Admin)
    - `roles/logging.logWriter` (Logs Writer)

3.  **Integrations**:
    - Connect your **GitHub repository** with **Cloud Build** via the GCP Console triggers page.

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
