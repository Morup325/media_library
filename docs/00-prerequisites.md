# Prerequisites & Tools

To work on the **Media Library** project, you need the following tools installed on your local machine. They are divided into three logical categories: Infrastructure, Local Development, and DevOps.

## 1. Core Infrastructure
These tools are the absolute minimum required to clone the repository and run the containerized application.

* **[Git](https://git-scm.com/)**: Version control system used to manage the code.
* **[Docker Engine](https://docs.docker.com/engine/) & [Docker Compose](https://docs.docker.com/compose/)**: Used to run our database (MySQL), cache (Redis), and the backend application in isolated containers via Laravel Sail.

## 2. Local Development (Backend & Frontend)
While the backend can run entirely inside Docker, having these tools installed locally provides a better developer experience (IDE auto-completion, linting, and fast frontend compilation).

* **[PHP 8.2+](https://www.php.net/)**: Required locally for IDE intelligence (e.g., VS Code Intelephense).
* **[Composer](https://getcomposer.org/)**: PHP dependency manager.
* **[Node.js (v20+)](https://nodejs.org/) & NPM**: Required to compile frontend assets using Vite (`npm run dev`).

## 3. DevOps & Kubernetes
These tools are required when testing the deployment architecture and CI/CD pipelines locally.

* **[Minikube](https://minikube.sigs.k8s.io/)**: Spins up a local Kubernetes cluster to test deployments before pushing to production.
* **[kubectl](https://kubernetes.io/docs/tasks/tools/)**: The command-line tool for interacting with the Kubernetes cluster.
* **[GitHub CLI (`gh`)](https://cli.github.com/)** *(Optional)*: Useful for interacting with GitHub Actions and managing repositories directly from the terminal.