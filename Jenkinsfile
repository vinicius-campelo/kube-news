pipeline {
    agent any

    stages {

       /* stage ('Build Docker Image') {

            steps {
                script {
                  def customImage = docker.build("autanbr/kube-news:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }*/


        stage ('Push Docker Image') {

            steps {
                script {
                    def customImage = docker.build("autanbr/kube-news:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                    customImage.withRegistry("https://registry.hub.docker.com", 'dockerhub')
                    customImage.push()
                        //customImage.push('latest')
                        //customImage.push("${env.BUILD_ID}")
                }
            }
        }
    }
}