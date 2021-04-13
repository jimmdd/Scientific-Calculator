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
       sh 'cd Calculator && mvn sonar:sonar \
        -Dsonar.projectKey=io.michaelcane:bestcalculator \
         -Dsonar.host.url=http://192.168.86.219:9000 \
          -Dsonar.login=be4f8636dabc8cd1c118d3f1716e47a1f7b71927'
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
