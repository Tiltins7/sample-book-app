pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                build_docker_image()
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
    sh 'docker run --rm --entrypoint=npm tiltins77/sample-book-app run test'
    echo "Pushing docker image to docker registry.."
    sh 'docker push tiltins77/sample-book-app:latest'
}

def deploy(String environment){
    echo "Deployment triggered on ${environment} environment.."
}

def run_api_tests(String environment){
    echo "API tests triggered on ${environment} environment.."
}
