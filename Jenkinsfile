pipeline {
  agent any
  stages {
    stage("Stop old Container") {
      steps {
        bat "docker rm -f company-1website || exit 0"
      }
    }
    stage("Checkout code") {
      steps {
        echo "Pulling code from Github"
        checkout scm
      }
    }
    stage("Build Docker Image") {
      steps {
        echo "Build Docker Image"
        bat "docker build -t company-1website ."
      }
    }
    stage("Run docker container") {
      steps {
        echo "Running docker container"
        bat "docker run -d -p 8070:80 company-1website"
      }
    }
  }
}
