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
        withSonarQubeEnv('My SonarQube Server') {
          sh 'mvn clean package sonar:sonar'
        }
      }
    }
    
    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }

  }
}
