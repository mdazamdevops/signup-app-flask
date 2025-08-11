# Full-Stack Authentication App & DevOps Pipeline

### Introduction

Welcome to this comprehensive DevOps project. This repository documents the entire lifecycle of a modern web application, from initial source code to a fully automated CI/CD pipeline and infrastructure provisioned as code. It features a Python/Flask backend and a JavaScript frontend, is fully containerized with Docker, and demonstrates a professional Git workflow for version control.

---
## Our Git Workflow: From Feature to Release

This project follows a structured Git branching strategy to ensure code quality and a stable `main` branch. Here is the exact process used to develop and release features.

#### 1. Create a Feature Branch
All new development starts on a `feature` branch, which is created from the `dev` branch. This isolates new work from the stable and integration branches.

```bash
# Switch to the development branch
git checkout dev

# Create a new branch for the feature
git checkout -b feature/add-readme
```

#### 2. Commit Changes
Code changes are saved with clear, semantic commit messages that explain the purpose of the change.

```bash
# Stage the new files
git add README.md .gitignore

# Commit with a descriptive message
git commit -m "docs: Create project README and add gitignore"
```

#### 3. Push and Create a Pull Request
The feature branch is then pushed to the remote repository on GitHub. A Pull Request (PR) is opened to merge the new feature into the `dev` branch for testing and integration.

```bash
# Push the feature branch to the remote repository
git push -u origin feature/add-readme
```
*After this command, a Pull Request is created on GitHub from `feature/add-readme` into `dev`.*

#### 4. Prepare for Release
Once the `dev` branch is stable and has accumulated enough features, a new Pull Request is created to merge `dev` into `main`, preparing for an official release.

*A Pull Request is created on GitHub from `dev` into `main`.*

#### 5. Tag a New Version
After the release PR is merged into `main`, the commit is tagged with a version number to mark it as a stable release.

```bash
# Switch to the main branch and pull the latest changes
git checkout main
git pull origin main

# Create a version tag
git tag -a v1.0.0 -m "Version 1.0.0 - Initial stable release"

# Push the tag to the remote repository
git push origin v1.0.0
```

---
## Project Automation & Infrastructure

* **CI/CD Pipeline (GitHub Actions & Jenkins):** The project includes a fully automated pipeline (`.github/workflows/main.yml` and `Jenkinsfile`) that handles testing (linting), building Docker images, and pushing them to Docker Hub on every commit to the `main` branch.

* **Containerization (Docker):** Both the frontend and backend are containerized using `Dockerfile`s. A `docker-compose.yml` is provided for easy local development.

* **Infrastructure as Code (Terraform):** A `main.tf` file is included to provision the entire application stack (backend, frontend, network) on Docker with a single `terraform apply` command.

---
## How to Run Locally
1.  Clone this repository.
2.  Ensure Docker and Docker Compose are installed.
3.  Run the command: `docker-compose up --build`
4.  Access the application in your browser at `http://localhost:3000`.