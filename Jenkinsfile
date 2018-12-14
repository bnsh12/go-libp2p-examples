pipeline {
  agent {
    docker {
      image 'golang'
      args '-v $HOME/goroot:/go -u root:root'
    }

  }
  stages {
    stage('Get Dependencies') {
      steps {
        sh 'go get -v -d ./...'
      }
    }
    stage('Build') {
      steps {
        sh 'go build'
      }
    }
  }
}