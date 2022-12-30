pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/daniyalj/jenkins-docker.git'
            }
        }
        stage('Build image') {
            steps {
                sh 'docker build -t myimage:latest .'
            }
        }
        stage('Push image') {
            steps {
                withDockerRegistry([credentialsId: 'my-registry-credentials', url: 'https://registry.example.com']) {
                    sh 'docker push myimage:latest'
                }
            }
        }
    }
}
