Food Delivery - Full-Stack Application with DevOps Pipeline
This project is a complete, full-stack food delivery web application featuring a modern, automated DevOps workflow. The application is built with a React frontend, a Node.js backend, and is fully containerized with Docker, orchestrated with Kubernetes, and deployed via a CI/CD pipeline using GitHub Actions.

🚀 Features
Customer Frontend: Browse restaurants and menu items, add items to the cart, place orders, and view order history.

Admin Panel: A separate interface to manage food items (add, list, remove) and view/update customer orders.

Microservices Architecture: Decoupled frontend and backend services for independent development and scaling.

Containerized Environment: Fully containerized for consistent development and production environments.

Automated CI/CD: Automated builds and Docker image pushes to Docker Hub on every commit to the main branch.

Scalable Deployment: Deployed on Kubernetes for high availability, self-healing, and scalability.

🛠️ Tech Stack
Frontend: React.js

Backend: Node.js, Express.js

Database: MongoDB

Containerization: Docker, Docker Compose

Orchestration: Kubernetes (K8s)

CI/CD: GitHub Actions

Web Server (Frontend): Nginx

📂 Project Structure
.
├── .github/workflows/   # GitHub Actions CI/CD pipeline
│   └── ci.yaml
├── admin/               # React source code for the admin panel
├── backend/             # Node.js/Express.js source code for the API
│   └── Dockerfile
├── frontend/            # React source code for the customer-facing app
│   └── Dockerfile
├── kubernetes/          # Kubernetes manifest files (.yaml)
│   ├── frontend-deployment.yaml
│   ├── backend-deployment.yaml
│   ├── mongo-deployment.yaml
│   └── ... (service files)
└── compose.yaml         # Docker Compose for local development

🏁 Getting Started
Prerequisites
Docker installed and running.

Kubernetes enabled (e.g., via Docker Desktop).

kubectl command-line tool installed.

A Docker Hub account.

🏡 Local Development (Using Docker Compose)
This is the easiest way to run the entire application stack on your local machine.

Clone the repository:

git clone (https://github.com/Grandhechaithu/tomatoo.git)
cd <repository-directory>

Start the application:

docker-compose up

Access the services:

Frontend Application: http://localhost

Admin Panel: http://localhost:5174 (or as configured)

Backend API: http://localhost:4000

Mongo Express (Database GUI): http://localhost:8081

🚢 Kubernetes Deployment
To deploy the application to a Kubernetes cluster (like the one in Docker Desktop):

Build and Push Docker Images:

Log in to Docker Hub:

docker login

Build, tag, and push the backend image. Replace your-dockerhub-username with your actual username.

docker build -t your-dockerhub-username/food-delivery-backend:latest ./backend
docker push your-dockerhub-username/food-delivery-backend:latest

Build, tag, and push the frontend image:

docker build -t your-dockerhub-username/food-delivery-frontend:latest ./frontend
docker push your-dockerhub-username/food-delivery-frontend:latest

Update Kubernetes Manifests:

In kubernetes/backend-deployment.yaml and kubernetes/frontend-deployment.yaml, make sure the image: key points to the images you just pushed to your Docker Hub repository.

Apply the Kubernetes Configuration:
Navigate to the kubernetes directory and apply all manifest files:

cd kubernetes
kubectl apply -f .

Access the Application:

The services will take a minute to start. Check their status with kubectl get all.

Use port-forward to access the frontend service from your browser:

kubectl port-forward service/frontend-service 8080:80

Open http://localhost:8080 in your web browser.

⚙️ CI/CD Pipeline with GitHub Actions
This project is configured with a GitHub Actions workflow that automatically builds and pushes the frontend and backend Docker images to Docker Hub.

Workflow File: .github/workflows/ci.yaml

Trigger: The workflow runs on every push to the main branch.

Configuration
To enable this workflow in your own fork of the repository, you must configure the following secrets in your GitHub repository's settings:

Go to Settings > Secrets and variables > Actions.

Add the following repository secrets:

DOCKERHUB_USERNAME: Your Docker Hub username.

DOCKERHUB_TOKEN: A Docker Hub personal access token with read/write permissions.