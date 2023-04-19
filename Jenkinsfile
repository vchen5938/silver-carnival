pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
        sh 'pwd'
        sh 'ls'
        sh 'cp target/spring-petclinic-3.0.0-SNAPSHOT.jar /app'
      }
    }

    stage('Run') {
      steps {
        sh 'pwd'
        sh 'ls'
        sh 'ansible-playbook -i /app/my-inventory.ini /app/my-playbook.yaml'
      }
    }

  }
}