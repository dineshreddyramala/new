pipeline {
  agent any

  stages {
    stage('Clone-Repo') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Run Tests') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Package as WAR') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Deployment') {
      steps {
       sh 'sshpass -p ramala123 scp target/gamutkart.war dinesh@172.31.39.126:/home/dinesh/apache-tomcat-9.0.85/webapps'

      }
    }
  }
}
