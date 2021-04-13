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
        sh 'cd Calculator && mvn sonar:sonar \
  -Dsonar.projectKey=calculator \
  -Dsonar.host.url=http://192.168.86.219:9000 \
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
