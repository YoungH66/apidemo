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
                 withAWS(credentials: 'lion-user02') {
                    sh 'aws s3 cp build/libs/apidemo-0.0.1-SNAPSHOT.jar s3://yh6651-build-files2/'
                 }
                // deploy steps
            }
        }
    }
}