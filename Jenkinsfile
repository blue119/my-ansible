pipeline {
  agent {
    node {
      label 'hw-01'
    }

  }
  stages {
    stage('Sleepy') {
      parallel {
        stage('Sleepy') {
          steps {
            sleep 5
          }
        }
        stage('CMD') {
          steps {
            sh 'echo "Hello"'
          }
        }
      }
    }
    stage('SHOW') {
      steps {
        sh 'echo "World"'
      }
    }
    stage('GGG') {
      steps {
        echo 'SHOW ME UP'
      }
    }
  }
}