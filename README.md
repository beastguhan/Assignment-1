# Assignment-1
# 🚀 Jenkins CI/CD Pipeline with Docker (Python App)

This project demonstrates a **complete local CI/CD pipeline** using **Jenkins and Docker** for a **Python (Flask) application**, without relying on any cloud services.

The pipeline automates:
- Source code checkout from GitHub
- Python dependency installation
- Unit testing using Pytest
- Docker image build
- Local container deployment

---

## 🛠 Tech Stack

- Jenkins (Docker-based)
- Docker
- Python 3
- Flask
- Pytest
- GitHub

---

## 📁 Project Structure

├── app.py
├── test_app.py
├── requirements.txt
├── Dockerfile
└── Jenkinsfile


---

## ⚙️ Jenkins Setup (Local)

Jenkins is run locally using Docker:

```bash
docker run -d \
  -p 8080:8080 -p 50000:50000 \
  --name jenkins \
  -v jenkins_home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  jenkins/jenkins:lts



