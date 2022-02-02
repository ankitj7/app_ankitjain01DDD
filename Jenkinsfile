pipeline {
  agent any

  tools {
    maven 'Maven3'
  }
  
  environment {
    scannerHome = 'sonar_scanner_dotnet'
  }

  options {
    timestamps()
    
    timeout(time: 1, unit: 'HOURS')
  }

  stages {

    stage("Build") {
      steps {
        echo "Build step started"
        sh 'mvn clean install'
      }
    }
    
    stage("Test case execution") {
      when {
        branch "master"
      }
      steps {
        echo "Test case step started"
        sh 'mvn test'
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
        echo env.BRANCH_NAME
      }
    }
    
  }
}
