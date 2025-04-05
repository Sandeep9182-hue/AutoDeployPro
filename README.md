# 🚀 AutoDeployPro

AutoDeployPro is a complete real-time CI/CD pipeline project built with Jenkins, Docker, Kubernetes, Prometheus, Grafana, and Slack integration. It automates everything from code commit to deployment and monitoring, following modern DevOps best practices.

---

## 👤 Author

- **Name**: Madela Saisandeep  
- **Email**: maddelasaisandeep950@gmail.com  

---

## 🛠️ Tech Stack

- Python + Flask
- Jenkins
- Docker
- Kubernetes
- Prometheus + Grafana
- Slack (Notification Integration)
- GitHub
- Horizontal Pod Autoscaler (HPA)

---

---

## 📦 Project Structure



AutoDeployPro/ │ ├── app.py ├── test_app.py ├── requirements.txt ├── Dockerfile ├── Jenkinsfile │ └── k8s/ ├── deployment.yaml ├── service.yaml ├── hpa.yaml ├── prometheus/ │ ├── prometheus-config.yaml │ ├── prometheus-deployment.yaml │ └── prometheus-service.yaml └── grafana/ ├── grafana-deployment.yaml └── grafana-service.yaml



---

## ⚙️ Jenkins CI/CD Pipeline Stages

1. Clone repository from GitHub
2. Run unit tests using Pytest
3. Build Docker image
4. Push image to DockerHub
5. Deploy app to Kubernetes
6. Setup monitoring using Prometheus + Grafana
7. Trigger Slack notifications on success/failure
8. Use HPA to auto-scale pods

---

## 📥 How to Use

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/AutoDeployPro.git
cd AutoDeployPro


 2. Build & Run Locally (optional)

pip install -r requirements.txt
python app.py


3. Docker Build

docker build -t yourdockerhub/auto-deploy-pro .


4. Push Docker Image

docker push yourdockerhub/auto-deploy-pro


5. Deploy to Kubernetes

kubectl apply -f k8s/


📊 Monitoring Dashboard
Prometheus: http://<your-node-ip>:9090

Grafana: http://<your-node-ip>:3000 (default login: admin / admin)


🔔 Slack Notifications
Integrate Slack via Webhook into Jenkins:

Go to your Slack workspace → Apps → Incoming Webhooks

Add the webhook URL in Jenkins Slack plugin



🧪 Testing


pytest test_app.py



📄 License
MIT License © 2025 Madela Saisandeep



