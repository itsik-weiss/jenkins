# Jenkins with Docker and Kubernetes Support

This configuration sets up a Jenkins container with Docker and Kubernetes (kubectl) support.

## Prerequisites

- Docker installed on the host machine
- Docker Compose installed on the host machine

## Features

- Jenkins LTS version
- Docker-in-Docker support
- kubectl for Kubernetes interaction
- Persistent volume for Jenkins data

## Usage

1. Build and start the container:
   ```bash
   docker-compose up -d
   ```

2. Get the initial admin password:
   ```bash
   docker-compose exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
   ```

3. Access Jenkins at http://localhost:8080

## Security Notes

- The container runs in privileged mode to support Docker-in-Docker
- Make sure to configure proper security settings in Jenkins
- Update the jenkins_home volume permissions if needed

## Configuration

- Jenkins is exposed on port 8080
- Jenkins agent port is exposed on 50000
- Jenkins data is persisted in a Docker volume named jenkins_home
- Docker socket is mounted to allow Docker commands inside Jenkins
