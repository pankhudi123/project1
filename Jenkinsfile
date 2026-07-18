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
                rm -rf /usr/local/apache2/htdocs/*
                cp -r ./* /usr/local/apache2/htdocs/
                ls -l /usr/local/apache2/htdocs/
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                sh '''
                ls -l /usr/local/apache2/htdocs/
                '''
            }
        }
    }
}