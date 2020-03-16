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
      when {
        branch 'master'
      }
      steps {
        sh './mvnw deploy'
      }
    }

  }
  post {
    success {
      mail(to: 'yunshi.lin8@gmail.com', subject: "Sucess: ${currentBuild.fullDisplayName}", body: "The pipeline ${currentBuild.fullDisplayName} completed successfully.")
    }

  }
}