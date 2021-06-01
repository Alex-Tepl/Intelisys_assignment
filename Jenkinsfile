pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'ubuntu'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''docker stop $(docker ps -q --filter "ancestor=lab11botcarrier")
docker rm -f $(docker ps -q --filter "ancestor=lab11botcarrier" --filter "status=exited")
docker build -f ./Dockerfile .
docker run -d lab11botcarrier'''
      }
    }

  }
}