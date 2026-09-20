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
                sh 'docker push unixquantum/jen-html:1.0.${BUILD_NUMBER}'
            }
        }
        stage('Deploy') {
            steps {
                echo 'I want to deploy the Docker image'
                sh 'docker run -d -p 8088:80 unixquantum/jen-html:1.0.${BUILD_NUMBER}'
            }
        }
    }

}
