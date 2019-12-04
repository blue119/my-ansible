pipeline {
  agent {
    node { label 'hw-01' }
  }

  environment {
        ENV_CCC = "@#@"
    }

  stages {
    stage('Checkout') {
      steps {
        echo 'checkout kernel_user_space_interfaces_example'
        git (
          url: 'https://github.com/blue119/kernel_user_space_interfaces_example.git'
          poll: true,
          branch: 'master'
        )
      }
    }

    stage('Sleepy') {
      parallel {

        stage('Sleepy') {
          steps {
            sleep 5
          }
        }
        stage('CMD') {
          steps { sh 'echo "Hello"' }
        }

      } // parallel {
    } // stage('Sleepy') {

    stage('GGG') {
      steps { echo 'SHOW ME UP' }
    }

    stage('show env') {
      steps {
        echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
        // sh 'printenv'
      }
    }

  } // stages {
} //pipeline {
