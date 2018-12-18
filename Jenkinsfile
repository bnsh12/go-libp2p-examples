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
    stage('Build ') {
      parallel {
        stage('Build Chat P2P') {
          steps {
            sh '''cd chat-with-rendezvous
go build'''
          }
        }
        stage('chat') {
          steps {
            sh '''cd chat
go build'''
          }
        }
        stage('echo') {
          steps {
            sh '''cd echo
go build'''
          }
        }
      }
    }
    stage('done') {
      steps {
        echo 'Yeah done!!'
      }
    }
  }
}