pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/DeepthiPandilla/spring-petclinic.git'
                echo "Git repository cloned successfully"
            }
        }
        stage('Test') {
            steps {
                
                sh 'mvn compile' 
                echo "Maven compile executed successfully"
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage ('Initiate') {
            steps {
                sh 'cd jenkinsfile_springboot'
                sh 'java -jar target/*.jar &'
                sh 'sleep 30'
                echo "Starting Application"
            }
        }

    }

    post {
        success {
            echo 'Build and Deploy succeeded!'
        }
        failure {
            echo 'Build or Deploy failed!'
        }
    }
}
