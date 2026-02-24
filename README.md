# Tutorial Website – MEAN Stack DevOps Deployment Project


This project is a full-stack CRUD web application built using:

Frontend:Angular
Backend: Node.js + Express
Database: MongoDB
Containerization: Docker
CI/CD: GitHub Actions
Web Server: Nginx Reverse Proxy
Cloud:AWS EC2 (Ubuntu)

The goal is to containerize the application and automate deployment using CI/CD pipelines.
# Setup EC2 Server

1. Launch Ubuntu EC2 instance  
Open ports:
- 22 (SSH)
- 80 (HTTP)
- 3000 (Backend)
- 4200 (Angular - optional)

2. Connect to EC2
bash

# Download docker

ssh ubuntu@EC2_PUBLIC_IP
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker

# Clone the project
git clone https://github.com/YOUR_USERNAME/Tutorial-Website.git
cd Tutorial-Website

# Nginx reverse proxy
server {
    listen 80;

    location / {
        root /var/www/html;
        index index.html;
    }

    location /api/ {
        proxy_pass http://localhost:3000/;
    }
}
# CI/CD pipeline
.github/workflows/docker.yml

# This project demonstrates:
Full-stack MEAN application deployment
Docker containerization
Reverse proxy using Nginx
CI/CD automation with GitHub Actions
Cloud hosting on AWS EC2
sudo apt install docker-compose -ygit clone https://github.com/RithikaSugumar/Tutorial-Website.git
cd Tutorial-Website
