pipeline {
  agent {
    node {
      label 'jdk8'
    }

  }
  stages {
    stage('build') {
      steps {
        echo "app is being built by ${params.Name}!"
        echo "${SONAR_USR}"
        echo "${SONAR_PSW}"
        sh 'java -version'
      }
    }
    stage('Test') {
      parallel {
        stage('Chrome') {
          steps {
            echo 'Testing on Chrome'
          }
        }
        stage('Safari') {
          steps {
            echo 'Testing on Safari....'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying.....'
      }
    }
  }
  environment {
    MY_NAME = 'adrian'
    SONAR = credentials('test-user')
  }
}