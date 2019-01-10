pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                echo 'Building'
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
    }

    stage('Test') {
        echo 'Testing..'
        }

    stage('Deploy') {
        echo 'Deploying'
        }
}