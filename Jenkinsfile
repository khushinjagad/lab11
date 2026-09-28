pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'YOUR_GITHUB_REPOSITORY_URL'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the project...'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t devops-project .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker stop devops-container || exit 0'
                sh 'docker rm devops-container || exit 0'
                sh 'docker run -d -p 8080:80 --name devops-container devops-project'
            }
        }
    }
}