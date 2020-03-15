pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Deploy') {
      steps {
        git(url: 'https://github.com/ys-lin/spring-petclinic', branch: 'gh-pages', changelog: true, credentialsId: 'ys-lin')
      }
    }

  }
}