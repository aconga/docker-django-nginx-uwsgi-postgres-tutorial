pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'docker-compose build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
}

node('production') {
    stage('Poll') {
        checkout scm
    }

    stage('Build') {
        sh 'ls -a'
        sh 'docker-compose build'
    }

    stage('Test') {
        echo 'Testing..'
        }

    stage('Deploy') {
        sh 'docker-compose up -d'
        }
}