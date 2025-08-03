# Helm Chart: Flask App with Nginx Reverse Proxy

A Helm chart project that deploys a Flask-based Docker image, served through an Nginx reverse proxy.

---

## Overview

Here you'll find a custom Helm chart to deploy the Flask containerized application using Nginx as a reverse proxy.

---

## Features

-  Custom Helm chart for Kubernetes
-  Custom Flask Docker image
-  Python automation script to deploy new projects
-  Docker Compose mini lab for local testing outside a Kubernetes cluster

---

##  Prerequisites

Ensure you have the following installed:

-  Initialized **Kubernetes cluster**
- **Helm**
- *(Optional)*  **Docker** & **Docker Compose** (for local lab)

---

##  How-To Guide

### Clone the Repository

```bash
git clone https://github.com/TheBlueDrara/Helm_Lab_Practice.git
cd Helm_Lab_Practice/helm_chart
```

### Install the Helm Chart

```bash
helm install <your-release-name> .
```

> **Note:** It might take a few moments for pods to initialize — the Docker image is relatively large.

### Check Pod Status

```bash
kubectl get pods
```

### Access the Application

```bash
curl http://<NodeIP>:80
```

> You should see the static HTML page of the web interface.
> If you want to run the local docker compose lab please continueo the guide

## Local Lab Only!

Run the lab locally

```
cd docker
docker compose up -d
curl localhost:80
```

Done!
---

##  What If I Don’t Have Kubernetes Installed?

No problem! You can visit my **Kubernetes offline installer project** for a fully automated way to deploy a working cluster:

 [Offline_Vanilla_k8s_Installer](https://github.com/TheBlueDrara/Offline_Vanilla_k8s_Installer.git)

---

##  Task

The full task description can be found [here](TASK.md)

---

##  Contributors

Check out the awesome people who contributed to this project [here](CONTRIBUTORS.md)

---

## Project Tree

<pre>
.
├── automation
│   └── deploy.py
├── config
│   ├── gunicorn_conf.py
│   └── nginx.conf
├── CONTRIBUTORS.md
├── docker
│   ├── docker-compose.yaml
│   └── Dockerfile
├── helm_chart
│   ├── Chart.yaml
│   ├── templates
│   │   ├── configmap.yaml
│   │   ├── details-app-deployment.yaml
│   │   ├── nginx-deployment.yaml
│   │   └── service.yaml
│   └── values.yaml
├── poetry.lock
├── pyproject.toml
├── README.md
├── src
│   └── my_app
│       ├── details_app.py
│       ├── __init__.py
│       ├── libs
│       │   └── __init__.py
│       ├── static
│       │   ├── assets
│       │   │   ├── favicon.ico
│       │   │   └── img
│       │   │       ├── bg-masthead.jpg
│       │   │       ├── bg-signup.jpg
│       │   │       ├── demo-image-01.jpg
│       │   │       ├── demo-image-02.jpg
│       │   │       └── ipad.png
│       │   ├── css
│       │   │   └── styles.css
│       │   └── js
│       │       └── scripts.js
│       └── templates
│           └── index.html
└── TASK.md
</pre>

---

## Daily WarHammer Quote

```
“I murdered thousands for the Emperor and he gave me nothing except his damning silence.
Now his lapdogs yap for every life I take, while the gods promise me the galaxy.”

— Svane Vulfbad, Renegade Wolf Lord of the Blood Wolves 
```