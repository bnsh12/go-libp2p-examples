pipeline {
  agent {
    docker {
      image 'golang'
      args '-v $HOME/goroot:/go -u root:root'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'go get -v -d ./...'
      }
    }
  }
}