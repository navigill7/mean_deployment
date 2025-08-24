🚀 Full-Stack Application with CI/CD, Docker, and Nginx

This repository contains a full-stack application (Frontend + Backend + Database) containerized with Docker, deployed via Docker Compose, and automated with GitHub Actions CI/CD.

📦 Project Structure

├── frontend/           
│   └── Dockerfile
├── backend/            
│   └── Dockerfile
├── nginx/
│   └── nginx.conf      
├── docker-compose.yml  
├── .github/workflows/
│   └── build_push.yml
└── README.md


⚙️ Setup Instructions
1️⃣ Clone the repository

```bash
git clone https://github.com/navigill7/mean_deployment.git
cd mean_deployment
```

2️⃣ Configure environment variables

Create a .env file in the backend folder with:

```bash
MONGO_URI=mongodb://mongo:27017/mydb
PORT=8080
```

3️⃣ Build and run using Docker Compose

```bash
docker-compose up --build -d
```

4️⃣ Access the application

Frontend → http://13.218.174.183/

Backend API → http://13.218.174.183/api

MongoDB → internal container (mongo)


🐳 Docker & Images
Build images locally

```bash
docker build -t gillnavi/frontend ./frontend
docker build -t gillnavi/backend ./backend
```
Push to Docker Hub

```bash
docker push gillnavi/frontend
docker push gillnavi/backend
```


🔄 CI/CD Workflow

We use GitHub Actions to:

Run tests & lint checks

Build Docker images

Push images to Docker Hub

Deploy to EC2 using SSH

Workflow file: .github/workflows/build_push.yml

Example Workflow Steps

Checkout repo

Build & push Docker images

SSH into EC2

Pull latest images

Restart containers with Docker Compose



📸 Screenshots
✅ CI/CD Workflow Execution

![alt text](image.png)

🐳 Docker Images Pushed to Hub

![alt text](image-1.png)



🌍 Application UI

![alt text](image-2.png)

⚙️ Nginx & Infra Setup

![alt text](image-3.png)


![alt text](image-4.png)


🛠️ Tech Stack

Frontend: React / Next.js

Backend: Node.js + Express

Database: MongoDB

Reverse Proxy: Nginx

CI/CD: GitHub Actions

Containerization: Docker + Docker Compose

Hosting: AWS EC2


🚀 Deliverables Checklist

 Dockerfiles for frontend & backend

 Docker Compose file for multi-service setup

 CI/CD workflow file (.github/workflows/ci-cd.yml)

 Nginx config for reverse proxy

 README with setup, screenshots, and infra details


 👨‍💻 Author

Your Name

GitHub: @navigill7