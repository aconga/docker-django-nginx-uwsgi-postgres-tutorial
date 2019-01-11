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
    }
}

node('test') {
    stage('Poll') {
        checkout scm
    }

    stage('Environment') {
        sh 'git --version'
        echo "Branch: ${env.BRANCH_NAME}"
        sh 'docker -v'
        sh 'printenv'
    }

    stage('Build') {
        sh 'ls -a'
        sh 'docker-compose build'
    }

    stage('Deploy') {
        sh 'docker-compose up -d'
        }
}