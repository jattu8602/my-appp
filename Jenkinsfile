pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/your-username/my-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nextjs-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop nextjs-app || true
                docker rm nextjs-app || true
                docker run -d -p 80:3000 --name nextjs-app nextjs-app
                '''
            }
        }
    }
}
