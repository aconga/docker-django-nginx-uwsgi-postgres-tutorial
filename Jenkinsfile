pipeline {
    agent any
    stages {
        stage('Checkout') { 
            steps {
                checkout scm
            }
        }
        stage('Environment') {
            steps {
                sh 'git --version'
                echo "Branch: ${env.BRANCH_NAME}"
                sh 'docker -v'
                sh 'printenv'
            }
        }

        stage('Build') {
            steps {
                sh 'pwd'
                sh '/usr/local/bin/docker-compose -f docker-compose.yml build'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}