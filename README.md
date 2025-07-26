## TOMATO - Food Ordering Website

This project is a complete, full-stack food delivery web application featuring a modern, automated DevOps workflow. The application is built with a React frontend, a Node.js backend, and is fully containerized with Docker, orchestrated with Kubernetes, and deployed via a CI/CD pipeline using GitHub Actions.

## Features

- Customer Frontend: Browse restaurants and menu items, add items to the cart, place orders, and view order history.

- Admin Panel: A separate interface to manage food items (add, list, remove) and view/update customer orders.

- Microservices Architecture: Decoupled frontend and backend services for independent development and scaling.

- Containerized Environment: Fully containerized for consistent development and production environments.

- Automated CI/CD: Automated builds and Docker image pushes to Docker Hub on every commit to the main branch.

- Scalable Deployment: Deployed on Kubernetes for high availability, self-healing, and scalability.

## Screenshots

![Hero](https://i.ibb.co/59cwY75/food-hero.png)
- Hero Section

![Products](https://i.ibb.co/JnNQPyQ/food-products.png)
- Products Section

![Cart](https://i.ibb.co/t2LrQ8p/food-cart.png)
- Cart Page

![Login](https://i.ibb.co/s6PgwkZ/food-login.png)
- Login Popup

## Run Locally

Clone the project

```bash
    git clone https://github.com/Grandhechaithu/Tomatoo_Delivery.git
```
Go to the project directory

```bash
    cd Food-Delivery
```
Install dependencies (frontend)

```bash
    cd frontend
    npm install
```
Install dependencies (admin)

```bash
    cd admin
    npm install
```
Install dependencies (backend)

```bash
    cd backend
    npm install
```
Setup Environment Vaiables

```Make .env file in "backend" folder and store environment Variables
  JWT_SECRET=YOUR_SECRET_TEXT
  SALT=YOUR_SALT_VALUE
  MONGO_URL=YOUR_DATABASE_URL
  STRIPE_SECRET_KEY=YOUR_KEY
 ```

Setup the Frontend and Backend URL
   - App.jsx in Admin folder
      const url = YOUR_BACKEND_URL
     
  - StoreContext.js in Frontend folder
      const url = YOUR_BACKEND_URL

  - orderController in Backend folder
      const frontend_url = YOUR_FRONTEND_URL 

Start the Backend server

```bash
    nodemon server.js
```

Start the Frontend server

```bash
    npm start
```

Start the Backend server

```bash
    npm start
```
## DevOps Tools Resource Links
- [Kubernetes (K8s)](https://kubernetes.io/docs/home/)
- [Docker](https://docs.docker.com/)
- [GitHub Actions](https://docs.github.com/en/actions)
- [CI/CD Concepts](https://roadmap.sh/devops)


## Contributing

Contributions are always welcome!
Just raise an issue, and we will discuss it.

## Feedback

If you have any feedback, please reach out to me [here](https://www.linkedin.com/in/chaithanya-grandhe/)

