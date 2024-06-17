pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/YoungH66/apidemo.git', credentialsId: 'YoungH66_github_id'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'chmod 755 ./gradlew'
                sh './gradlew build'
                // build steps
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // test steps
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // deploy steps
            }
        }
    }
}