pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                build_docker_image()
            }
        }
        stage('unit-test') {
            steps {
                run_unit_tests()
            }
        }
        stage('deploy-dev') {
            steps {
                deploy("Dev")
            }
        }
        stage('api-integration-tests-dev') {
            steps {
                deploy("Dev")
            }
        }
        stage('deploy-stg') {
            steps {
                deploy("STG")
            }
        }
        stage('api-integration-tests-stg') {
            steps {
                run_api_tests("STG")
            }
        }
        stage('deploy-prod') {
            steps {
                deploy("prod")
            }
        }
        stage('api-integration-tests-prod') {
            steps {
                run_api_tests("PROD")
            }
        }
    }
}

def build_docker_image(){
    echo "Building docker image"
    echo "Building docker image.."
    sh 'docker build --no-cache -t tiltins77/sample-book-app:latest .'

    echo "Pushing docker image to docker registry.."
    sh 'docker push tiltins77/sample-book-app:latest'
}

def run_unit_tests(){
    echo "Runing unit tests for node application in docker container"
}

def deploy(String environment){
    echo "Deployment triggered on ${environment} environment.."
}

def run_api_tests(String environment){
    echo "API tests triggered on ${environment} environment.."
}
