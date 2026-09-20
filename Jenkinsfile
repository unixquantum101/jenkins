pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'I want to build a Docker image'
                sudo -u dudu docker build -t unixquantum/my-jen-html:1.0.${BUILD_NUMBER} .
            }
        }
    }
    stages {
        stage('Push images') {
            steps {
                echo 'I want to push the Docker image'
                docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                    docker.image('unixquantum/my-jen-html:1.0.${BUILD_NUMBER}').push()
                }
            }unixquantum
        }
    }
    stages {
        stage('Deploy') {
            steps {
                echo 'I want to deploy the Docker image'
                sh 'docker run -d -p 8088:80 unixquantum/my-jen-html:1.0.${BUILD_NUMBER}'
            }
        }unixquantum
    }
}
