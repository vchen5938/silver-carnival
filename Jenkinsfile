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
          sh 'mvn sonar:sonar -Dsonar.token=$SONAR_TOKEN'
        }

      }
    }

    stage('Deploy') {
      steps {
        sh 'cp target/spring-petclinic-3.0.0-SNAPSHOT.jar /app'
        sh 'ansible-playbook -i /app/my-inventory.ini /app/my-playbook.yaml'
      }
    }

  }
}