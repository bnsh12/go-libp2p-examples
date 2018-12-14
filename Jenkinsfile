pipeline {
  agent {
    docker {
      image 'golang'
      args '-v $HOME/goroot:/go'
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