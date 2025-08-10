pipeline {
  agent any

  stages {
    stage('Docker Inspect') {
      steps {
        sh 'docker inspect -f . maven:3.9.11-eclipse-temurin-21-alpine'
      }
    }

    stage('Build with Maven') {
      agent {
        docker {
          image 'maven:3.9.11-eclipse-temurin-21-alpine'
        }
      }
      steps {
        sh 'mvn clean install'
      }
    }
  }
}
