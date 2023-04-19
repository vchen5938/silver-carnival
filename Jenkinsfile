pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
        sh 'pwd'
        sh 'ls'
      }
    }

    stage('Run') {
      steps {
        sh 'ansible-playbook -i /app/my-inventory.ini /app/my-playbook.yaml'
      }
    }

  }
}