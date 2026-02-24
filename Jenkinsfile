pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Code cloned from GitHub"
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-ci-demo:${BUILD_NUMBER} .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5001:5000 jenkins-ci-demo:${BUILD_NUMBER}'
            }
        }
    }
}