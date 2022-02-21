@Library('slack') _

pipeline {
  agent any

  environment {
    deploymentName = "devsecops"
    containerName = "devsecops-container"
    serviceName = "devsecops-svc"
    imageName = "rajualakuntla/numeric-app:${GIT_COMMIT}"
    applicationURL = "http://devsecops-demo123.eastus.cloudapp.azure.com"
    applicationURI = "/increment/99"
  }

  stages {

    stage('Testing Slack') {
      steps {
        sh 'exit 1'
      }
    }


  }

  post {
    always {
      // Use sendNotifications.groovy from shared library and provide current build result as parameter    
      sendNotification currentBuild.result
    }

    // success {

    // }

    // failure {

    // }
  }

}