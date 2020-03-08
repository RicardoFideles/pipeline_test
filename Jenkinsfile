#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node'
            args '-u root'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployng...'
                sh '''
                    ssh root@157.245.250.114
                    cd /var/www/html/construcao_api/
                    ls -lah
                    touch teste.html
                '''
            }
        }
    }
}