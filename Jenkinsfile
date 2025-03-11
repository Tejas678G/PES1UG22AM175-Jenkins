pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ hello.cpp -o hello.out'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './invalid.out' // Intentional Error
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage executed successfully!'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
