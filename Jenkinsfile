pipeline {
    stage('Checkout') {
        checkout scm
    }

    stage('Environment') {
        sh 'git --version'
        echo "Branch: ${env.BRANCH_NAME}"
        sh 'docker -v'
        sh 'printenv'
    }
}

node('production') {
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