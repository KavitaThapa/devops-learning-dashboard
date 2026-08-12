# DevOps Learning Dashboard

A Flask-based web application created to demonstrate my learning and practical implementation of DevOps concepts including Git, GitHub, Jenkins, Docker, and AWS.

## Technologies Used

- Python
- Flask
- Git & GitHub
- Jenkins
- Docker
- AWS EC2
- Pytest
- Linux

## Project Features

- Flask-based web application
- Three application pages: Home, About, and Skills
- Automated testing using Pytest
- Dockerized Flask application
- Jenkins CI/CD pipeline
- GitHub webhook for automatic pipeline triggering
- Automated Docker image build
- Automated Docker container deployment
- Application health check after deployment
- Hosted on AWS EC2

## Project Structure

```
devops-learning-dashboard/
│
├── app.py
├── Dockerfile
├── Jenkinsfile
├── requirements.txt
├── README.md
├── Tests/
│   └── test_app.py
├── templates/
│   ├── index.html
│   ├── about.html
│   └── skills.html
├── static/
│   └── style.css
├── .gitignore
└── .dockerignore
```
## CI/CD Pipeline

The project uses Jenkins to automate the CI/CD process.

### Pipeline Flow

```
Developer
    |
    | git push
    v
GitHub
    |
    | Webhook
    v
Jenkins
    |
    +--> Checkout
    |
    +--> Build
    |
    +--> Test
    |
    +--> Docker Build
    |
    +--> Docker Run
    |
    +--> Health Check
    |
    v
Running Flask Application
```
### Pipeline Stages
1. Checkout - Jenkins gets the latest source code from GitHub.
2. Build - Creates a Python virtual environment and installs dependencies.
3. Test - Runs automated tests using Pytest.
4. Docker Build - Builds the Docker image.
5. Docker Run - Stops the previous container and starts the new container.
6. Health Check - Verifies that the Flask application is running successfully.

## Testing

Automated tests are written using Pytest.

Tests are stored in the `Tests/` directory.

The Jenkins pipeline automatically runs the tests during every build.

Current test result: **3 tests passed**.

### Run Tests Locally

```
venv/bin/pytest
```

## Docker

The Flask application is containerized using Docker.

### Build and Run Docker Container

```
docker build -t devops-learning-dashboard .
docker run -d --name devops-learning-dashboard -p 5001:5001 devops-learning-dashboard:latest
```

The application runs on port `5001`.

## Application Routes

| Route | Description |
|---|---|
| `/` | Home page |
| `/about` | About page |
| `/skills` | Skills page |

## Deployment

The application is deployed on an AWS EC2 instance using Docker and Jenkins.

### Deployment Workflow

```
GitHub
   |
   | Git Push
   v
Jenkins
   |
   +--> Build
   +--> Test with Pytest
   +--> Build Docker Image
   +--> Run Docker Container
   +--> Health Check
   |
   v
AWS EC2
   |
   v
Flask Application
```
### Docker

- Application containerized using Docker.
- Docker image is built automatically by Jenkins.
- Previous container is stopped and removed before deployment.
- New Docker container is started on port `5001`.

### Jenkins

- Jenkins pipeline is triggered automatically through a GitHub webhook.
- Pipeline performs source code checkout, application build, automated testing, Docker image build, container deployment, and health check.
- Deployment is considered successful only after the application health check passes.

### AWS EC2

- Application is deployed on an AWS EC2 worker node.
- Docker container runs on the EC2 instance.
- Port `5001` is configured in the EC2 Security Group for external access.
- The deployed Flask application can be accessed through the EC2 public IP address.

### Deployment Result

The application is successfully deployed and accessible through a web browser after the Jenkins pipeline completes successfully.