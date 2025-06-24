pipeline {
    agent any

    tools {
        maven 'mvn3' // This must match Maven tool name in Jenkins global config
    }

    stages {
        stage('Clone the source code') {
            steps {
                // Corrected git URL syntax
                git url: 'https://github.com/Saijoe112/docker-cicd-students-demo.git', branch: 'main'
            }
        }

        stage('Build the source code using Maven') {
            steps {
                echo 'Build the source code using Maven'
                sh 'mvn clean package'
            }
        }

        stage('Create the Docker image') {
            steps {
                echo 'Create the Docker image'
                sh 'docker build -t saikiran64264/myimg2:v3 .'
            }
        }

        stage('Push the image to the Docker registry') {
            steps {
                echo 'Push the image to the Docker registry'
                sh 'docker push saikiran64264/myimg2:v3'
            }
        }

        stage('Create the container') {
            steps {
                echo 'Create the container'
                sh 'docker run -d --name mycontainer saikiran64264/myimg2:v3'
            }
        }
    }
}
