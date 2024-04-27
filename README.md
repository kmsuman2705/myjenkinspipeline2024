# Jenkins Pipeline for Building and Deploying a Java Web Application with Docker

This Jenkins pipeline is designed to automate the build, Docker image creation, and deployment process for a Java web application.

## Pipeline Overview

The pipeline consists of the following stages:

1. **SCM (Source Code Management)**:
   - Clone the repository containing the Java web application source code from GitHub.

2. **Build by Maven Package**:
   - Use Maven to clean and package the Java web application.

3. **Build Docker Own image**:
   - Build a Docker image for the Java web application using the Dockerfile provided in the repository.
   - Tag the Docker image with the build tag.

4. **Push Image to Docker HUB**:
   - Log in to Docker Hub using the provided credentials.
   - Tag the Docker image with the build number.
   - Push the tagged Docker image to Docker Hub.

5. **Deploy webAPP in DEV Env**:
   - Remove any existing Docker container named `myjavaapp`.
   - Run a new Docker container from the built Docker image on port 8080, named `myjavaapp`.

6. **Deploy webAPP in QA/Test Env**:
   - Remove any existing Docker container named `myjavaapp` on the QA/Test environment.
   - Run a new Docker container from the built Docker image on port 8080, named `myjavaapp` on the QA/Test environment.

## Prerequisites

- Jenkins server configured with necessary plugins for Docker, SSH, Git, and Maven.
- Docker installed on the Jenkins server.
- Docker Hub account for pushing Docker images.
- SSH access to the QA/Test environment for deployment.

## Usage

1. Configure the Jenkins pipeline with the provided script.
2. Replace placeholders such as `linuxlabelnode`, GitHub repository URL, Docker Hub credentials, and SSH credentials with actual values.
3. Ensure that the Dockerfile in the repository is properly configured to build the Java web application image.
4. Run the Jenkins pipeline to trigger the build, Docker image creation, and deployment process.
5. Monitor the pipeline execution for any errors or issues.

## Notes

- Ensure that Docker is properly configured on the Jenkins server and has permissions to run Docker commands.
- Verify the Dockerfile and Docker image creation process to ensure compatibility with the Java web application.
- Adjust the deployment steps for different environments as per requirements.
- Monitor the Jenkins pipeline execution logs for debugging and troubleshooting.
