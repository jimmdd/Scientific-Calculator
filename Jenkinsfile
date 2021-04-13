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
        withSonarQubeEnv(credentialsId: 'a87315d7db082c7e7a08c737c3d9342ef6977d0e', installationName: 'My SonarQube Server') { // You can override the credential to be used
          sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
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
