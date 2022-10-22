pipeline {
    agent any

    stages {

        stage ('Build Docker Image') {

            steps {
                script {
                    customImage = docker.build("autanbr/docker-test:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }


        stage ('Push Docker Image') {

            steps {
                script {
                    docker.withRegistry("https://registry.hub.docker.com", "dockerhub")
                    customImage.push('latest')
                    customImage.push("${env.BUILD_ID}")
                }
            }
        }
    }
}