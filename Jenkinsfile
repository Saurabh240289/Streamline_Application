pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Saurabh240289/Streamline_Application.git'
                
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t skulkarni24/sk-streamlit-app .'
            }
        }
        stage('Push Docker Image') {
            steps {
                sh 'docker login -u skulkarni24 -p Saurabh@240289!'
                sh 'docker push skulkarni24/sk-streamlit-app'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f sk-streamlit-container || true'
                sh 'docker run -d --name sk-streamlit-container -p 8501:8501 skulkarni24/sk-streamlit-app'
            }
        }
    }
}
