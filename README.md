# Flask + Redis + Docker + GitHub Actions CI/CD

This project is a simple Flask app that uses Redis as a fast and efficient data store. Everything is containerized with Docker, so it’s easy to build, run, and deploy anywhere.

---

## What’s included in this project?

- **Flask app** inside the `app/` folder — the backend code.  
- **Redis** — a caching service to speed up the app and handle data efficiently.  
- **Dockerfile** — instructions for building the Flask app’s Docker image.  
- **docker-compose.yml** — lets you run Flask and Redis containers together locally.  
- **GitHub Actions workflow (`docker.yml`)** — automates building and pushing the Docker image on every code push.

---

## What is CI/CD and why use it?

CI/CD stands for **Continuous Integration and Continuous Delivery**. It means:

- **Continuous Integration (CI):** Every time you push code, it automatically builds and tests your app.  
- **Continuous Delivery (CD):** Your app is automatically built and deployed, making new versions available quickly and reliably.

Using CI/CD with GitHub Actions means:

- You don’t have to manually build or push Docker images — it happens automatically.  
- Your Docker images are always up-to-date with the latest code.  
- It reduces human error and speeds up your development workflow.

---

## How the GitHub Actions CI/CD workflow works

When you push code to GitHub:

1. **Checkout code** — the workflow fetches your latest files.  
2. **Set up Docker Buildx** — prepares for efficient Docker builds.  
3. **Log in to Docker Hub** — securely authenticates using GitHub Secrets.  
4. **Build and push the Docker image** — your Flask app image is built and pushed to Docker Hub with a tag like `abdikarim98/my-name:myimage`.

This pipeline runs automatically every push, so your image is always ready to deploy.

---

## Why use Docker Compose?

Managing Flask and Redis manually can be complex. Docker Compose helps by:

- Defining both services in one file.  
- Creating a network so Flask can communicate with Redis by service name.  
- Letting you start both containers together with:

```bash
docker-compose up --build
