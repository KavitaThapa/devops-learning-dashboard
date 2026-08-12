# Devops Learning Dashboard

A Flask-based web application created to demonstrate my learning and practical implementation of Devops concepts including Git, Jenkins, Docker, and AWS.

## Technologies Used

- Pyhon
- Flask
- Git
- Github
- Jenkins
- Docker
- AWS EC2
- Pytest 
- Linux

## Project Features

- Flask-based web application
- Three application pages: Home, About, and Skills
- Automated Tested using pytest
- Dockerized Flask application
- Jenkins CI/CD pipeline
- Automated Github webhook trigger
- Automated Docker image build
- Automated Docker container deployment
- Application health check after deployment
- Hosted on AWS EC2 

## Project Structure

```text
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
'''
'''

## CI/CD Pipeline

The project uses Jenkins to automate the CI/CD process.

### Pipeline Flow

```text
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
Running flask Application 

## Docker

The Flask application is containerized using Docker.

### Build the Docker Image

```bash
docker build -t devops-learning-dashboard .