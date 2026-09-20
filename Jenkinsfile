pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
               script {
                    echo 'I want to build the Docker image'
                    sh 'docker build -t unixquantum/jen-html:1.0.${BUILD_NUMBER} .'
                }
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
