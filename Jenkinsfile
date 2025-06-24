pipeline {
    agent any

    tools {
        maven 'mvn3'  // Ensure this Maven tool is configured in Jenkins global tools
    }

    stages {
        stage('Clone the source code') {
            steps {
                echo 'Already configured'
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
