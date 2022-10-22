pipeline {
    agent any

    stages {

        stage ('Build Docker Image') {

            steps {
                script {
                  def customImage = docker.build("autanbr/kube-news:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }
    }
}