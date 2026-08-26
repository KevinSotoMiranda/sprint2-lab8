pipeline {
    agent any
    {
        stages {
            stage('Checkout') {
                steps {
                    checkout scm
                }
            }

            stage('Build') {
                steps {
                    sh 'echo "Building the project..."'
                    sh 'docker build -t team-skeleton:${BUILD_NUMBER} .'
                    sh 'docker images'
                    sh 'echo "Build completed."'
                }
            }

            stage('Test') {
                steps {
                    sh 'echo "Running tests..."'
                    sh 'mvn -B test'
                    sh 'echo "Tests completed."'
                }
            }

        }
    }
}