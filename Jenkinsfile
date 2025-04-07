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
                echo "Created Jar file for execution"
            }
        }

   

    }

    post {
        success {
            echo 'Build is successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
