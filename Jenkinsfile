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
        dir('kernel_user_space_interfaces_example') {
          git (poll: true, url: 'https://github.com/blue119/kernel_user_space_interfaces_example.git', branch: 'master')
        }
        dir('ansible-wordpress') {
          git (poll: true, url: 'https://github.com/blue119/ansible-wordpress.git', branch: 'master')
        }
        dir('trigger-ci') {
          git (poll: true, url: 'https://github.com/blue119/trigger-ci.git', branch: 'master')
        }

        //git (
        //  url: 'https://github.com/blue119/kernel_user_space_interfaces_example.git',
        //  poll: true,
        //  branch: 'master'
        //)
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
