pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo 'Testing app...'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t app-mieayam .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop container-mieayam || true'
                sh 'docker rm container-mieayam || true'
                sh 'docker run -d -p 5000:5000 --name container-mieayam app-mieayam'
            }
        }
    }
}
