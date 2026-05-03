pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'git@github.com:Aishu110-tech/python-devops-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f python-container || true
                docker run -d -p 5000:5000 --name python-container python-app
                '''
            }
        }
    }
}
