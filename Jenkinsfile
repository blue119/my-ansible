pipeline {
  //agent {
  //  node {
  //    label 'hw-01'
  //  }
  //}
  agent none
  
  environment { 
        ENV_CCC = "@#@"
    }
  
  stages {
    stage('Sleepy') {
      parallel {
        
        stage('Sleepy') {
          agent any
          steps {
            sleep 5
          }
        }
        stage('CMD') {
          agent {
            node {
              label 'hw-01'
            }
          }
          steps {
            sh 'echo "Hello"'
          }
        }
        
      } // parallel {
    } // stage('Sleepy') {
    
    stage('SHOW') {
      agent any
      steps {
        sh 'echo "World"'
      }
    }
    
    stage('GGG') {
      agent {
        node {
          label 'dapv1-01'
        }
      }
      steps {
        echo 'SHOW ME UP'
      }
    }
    
    stage('show env') {
      agent any
      steps {
        echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
        sh 'printenv'
      }
    }
    
    stage('Sleepy ALL') {
      parallel {
        
        stage('@ dapv1-01') {
          agent {
            node {
              label 'dapv1-01'
            }
          }
          steps {
            sleep 5
          }
        }
        stage('@ dapv1-02') {
          agent {
            node {
              label 'dapv1-02'
            }
          }
          steps {
            sleep 8
          }
        }
        stage('@ dapv1-03') {
          agent {
            node {
              label 'dapv1-03'
            }
          }
          steps {
            sleep 3
          }
        }
      } // parallel {
    } // stage('Sleepy') {
    
  } // stages {
} //pipeline {
