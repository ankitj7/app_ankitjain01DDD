pipeline {
  agent any

  environment {
    scannerHome = 'sonar_scanner_dotnet'
  }

  options {
    timestamps()
  }

  stages {

    stage("Build") {
      steps {
        echo "Build step started"
      }
    }
    
    stage("Test case execution") {
      when {
        branch "master"
      }
      steps {
        echo "Test case step started"
      }
    }
    
    stage("Sonarqube Analysis") {
      when {
        branch "develop"
      }
      steps {
        echo "Sonarqube Analysis step started"
      }
    }
    
    stage("Kubernets Deployment") {
      steps {
        echo "Kubernets Deployment step started"
      }
    }
    
  }
}
