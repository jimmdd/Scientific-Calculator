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
        echo 'Junit testing'
        sh 'cd Calculator && mvn test'
        echo 'Static testing'
        sh 'SONAR_MAVEN_GOAL'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }

  }
}