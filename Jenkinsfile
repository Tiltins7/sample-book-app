pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                scripts {
                    build_docker_image()
                }
            }
        }
        stage('unit-test') {
            steps {
                scripts {
                    run_unit_tests()
                }
            }
        }
        stage('deploy-dev') {
            steps {
                scripts {
                    deploy("Dev")
                }
            }
        }
        stage('api-integration-tests-dev') {
            steps {
                scripts {
                    deploy("Dev")
                }
            }
        }
        stage('deploy-stg') {
            steps {
                scripts {
                    deploy("STG")
                }
            }
        }
        stage('api-integration-tests-stg') {
            steps {
                scripts {
                    run_api_tests("STG")
                }
            }
        }
        stage('deploy-prod') {
            steps {
                scripts {
                    deploy("prod")
                }
            }
        }
        stage('api-integration-tests-prod') {
            steps {
                scripts {
                    run_api_tests("PROD")
                }
            }
        }
    }
}

def build_docker_image(){
    echo "Building docker image"
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
