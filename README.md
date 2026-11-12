# Nginx Proxy Manager (Docker Compose Setup)

Project-Link: https://github.com/NginxProxyManager/nginx-proxy-manager

A production-ready Docker Compose configuration for **Nginx Proxy Manager (NPM)** using a **PostgreSQL 17** database backend. This repository is structured to be instantly ready for deployment after cloning.

## 📋 Prerequisites

Before starting the stack, ensure your system meets the following requirements:
* **Docker** and the **Docker Compose** plugin are installed.
* Your system user belongs to the `docker` group (crucial for correct volume permissions) and has `sudo` privileges.

---

## 🚀 Quickstart

Follow these simple steps to get your stack up and running:

### 1. Clone the Repository
Clone this repository to your server or local machine:
```bash
git clone https://github.com/hubertnubert/docker_npm.git
cd docker_npm
```

### 2. Configure Environment Variables
Create a `.env` file from the provided template:
```bash
cp .env.example .env
```
Open the newly created `.env` file with your preferred text editor (e.g., `nano .env`) and set a **strong, secure password** for the database.

### 3. Start the Containers
Launch the stack in the background (detached mode):
```bash
docker compose up -d
```

---

## 🌐 Accessing the Web Interface

Once the containers are up and running, you can access the admin interface via your browser:

* **URL:** `http://<YOUR-SERVER-IP>:81`

*⚠️ **Important:** You will be prompted to change your email address and the default password immediately on your first login. Please update these configuration details straight away.*

---

## 🛠️ Directory Structure

The project directories are pre-created and include `.gitkeep` files to ensure the empty folder structure is tracked by Git. When the containers boot up, Docker will write persistent data directly into them:

* `data/` – Nginx Proxy Manager configuration and user data.
* `letsencrypt/` – Let's Encrypt SSL certificates.
* `postgres_data/` – Persistent data storage for the PostgreSQL database.
