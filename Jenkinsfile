pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source downloaded'
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                rsync -av --delete ./ root@192.168.15.136:/var/lib/docker/volumes/apachevol/_data/
                '''
            }
        }
        stage('Verify Deployment') {
            steps {
                sh '''
                curl -f http://192.168.15.136:8080
                '''
            }
        }
    }
}