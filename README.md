# AWS-ECS-deployment

## Step 1: Prepare the Flask Application

1. **Dockerize the Flask Application:**
    - Create a `Dockerfile` in your Flask application repository.

2. **Build and Push Docker Image:**
    - Build the Docker image locally and push it to Amazon ECR (Elastic Container Registry).

    ```sh
    # Authenticate Docker to your Amazon ECR registry
    aws ecr get-login-password --region your-region | docker login --username AWS --password-stdin your-account-id.dkr.ecr.your-region.amazonaws.com

    # Build your Docker image
    docker build -t flask-app .

    # Tag the Docker image
    docker tag flask-app:latest your-account-id.dkr.ecr.your-region.amazonaws.com/flask-app:latest

    # Push the Docker image to Amazon ECR
    docker push your-account-id.dkr.ecr.your-region.amazonaws.com/flask-app:latest
    ```
