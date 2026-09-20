pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'I want to build a Docker image'
                docker build -t unixquantum/my-jen-html:1.0.${BUILD_NUMBER} .
            }
        }
        stage('Push images') {
            steps {
                echo 'I want to push the Docker image'
            }
        }
        stage('Deploy') {
            steps {
                echo 'I want to deploy the Docker image'
            }
        }
    }

}
