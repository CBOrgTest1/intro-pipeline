pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Testing') {
      failFast true
      parallel {
        stage('Java 8') {
          agent {
            label 'jdk8'
          }
          steps {
            sh 'java -version'
            sleep(time: 10, unit: 'SECONDS')
          }
        }
        stage('Java 9') {
          agent {
            label 'jdk9'
          }
          steps {
            sh 'java -version'
            sleep(time: 20, unit: 'SECONDS')
          }
        }
      }
    }
  }
  environment {
    MY_NAME = 'Vartika'
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}