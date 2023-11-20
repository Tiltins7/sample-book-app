pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                echo "Building docker image..."
            }
        }
        stage('unit-test') {
            steps {
                echo "Runing unit tests for node application in docker container"
            }
        }
        stage('deploy-dev') {
            steps {
                echo "Deployment triggering on dev"
            }
        }
        stage('api-integration-tests-dev') {
            steps {
                echo "Deployment triggering on dev"
            }
        }
        stage('deploy-stg') {
            steps {
                echo "Deployment triggering on stg"
            }
        }
        stage('api-integration-tests-stg') {
            steps {
                echo "Deployment triggering on stg"
            }
        }
        stage('deploy-prod') {
            steps {
                echo "Deployment triggering on prod"
            }
        }
        stage('api-integration-tests-prod') {
            steps {
                echo "Deployment triggering on prod"
            }
        }
    }
}
