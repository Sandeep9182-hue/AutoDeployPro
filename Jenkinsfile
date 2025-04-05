pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/YOUR_USERNAME/AutoDeployPro.git'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest test_app.py'
            }
        }
        stage('Build Image') {
            steps {
                sh 'docker build -t yourdockerhub/auto-deploy-pro .' 
            }
        }
        stage('Push Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                    sh 'docker push yourdockerhub/auto-deploy-pro'
                }
            }
        }
        stage('Deploy to K8s') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
        stage('Notify Slack') {
            steps {
                slackSend (channel: '#deployments', message: 'Deployment Complete!', color: 'good')
            }
        }
    }
}
