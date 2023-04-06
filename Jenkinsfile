pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('SonarQube') {
      steps {
        withSonarQubeEnv('My SonarQube Server') {
          sh 'mvn sonar:sonar -Dsonar.login=$SONAR_TOKEN'
        }

      }
    }

    stage('Run') {
      steps {
        sh 'java -jar target/*.jar --server.port=80 '
      }
    }

  }
}