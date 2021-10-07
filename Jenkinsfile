pipeline {

  environment {
    PROJECT_DIR = "/app"
    REGISTRY = "oabuoun/secure_rest_api"
    DOCKER_CREDENTIALS = "docker_auth"
    DOCKER_IMAGE = ""
  }

  agent any

  options {
    skipStagesAfterUnstable()
  }

  stages {

    stage('Cloning The Code from GIT') {
      steps {
        git url: 'https://github.com/oabuoun/secure_rest_api_server.git'
      }
    }

    stage('Build-Image'){
      steps {
        script {
          DOCKER_IMAGE = docker.build REGISTRY
        }
      }
    }
  }

}
