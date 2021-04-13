pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        sh 'cd Calculator && mvn install'
      }
    }

    stage('Test') {
      steps {
        echo 'testing'
        sh 'cd Calculator && mvn test'
      }
    }

    stage('Static analysis') {
      steps {
        echo 'Static testing'
        sh 'cd Calculator && mvn sonar:sonar 
        echo 'pwd'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy'
        sh 'cd Calculator && mvn package'
      }
    }

  }
}