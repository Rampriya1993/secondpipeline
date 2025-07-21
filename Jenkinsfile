pipeline {

    agent any

    environment {

        IMAGE_NAME = "jenkinslocalimage"

        CONTAINER_NAME = "jenkinslocalcontainer"

    }

    stages {

        stage('Clone Repository') {

            steps {

                git 'https://github.com/Rampriya1993/secondpipeline.git'

            }

        }

        stage('Build Docker Image') {

            steps {

                script {

                    sh "docker build -t ${IMAGE_NAME} ."

                }

            }

        }

        stage('Run Docker Container') {

            steps {

                script {

                    // Remove if already running

                    sh "docker rm -f ${CONTAINER_NAME} || true"

                    // Run container in background

                    sh "docker run -d --name ${CONTAINER_NAME} ${IMAGE_NAME}"

                }

            }

        }

    }

}
 
