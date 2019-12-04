pipeline {
  agent {
    node {
      label 'hw-01'
    }
  }
  
  environment { 
        ENV_CCC = "@#@"
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
        
      } // parallel {
    } // stage('Sleepy') {
    
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
    
    stage('show env') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh 'printenv'
            }
        }
    
    
    
  } // stages {
} //pipeline {
