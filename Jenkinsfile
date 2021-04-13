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
        sh 'mvn sonar:sonar \
  -Dsonar.projectKey=calculator \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=jenkins'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }

  }
}
