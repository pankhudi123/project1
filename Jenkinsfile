pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/pankhudi123/project1.git'
            }
        }

        stage('Verify Workspace') {
            steps {
                sh '''
                pwd
                ls -la
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                whoami
                id
                pwd
                ls -l /var/run/docker.sock
                docker --version
                docker ps
                docker cp . apache:/usr/local/apache2/htdocs/
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                sh '''
                docker exec apache ls -l /usr/local/apache2/htdocs/
                '''
            }
        }
    }
}