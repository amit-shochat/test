pipeline {
  agent any
  
  environment {
    dotnet = 'C:\\Program Files (x86)\\dotnet\\'
  }
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/amit-shochat/test', branch: 'master')
      }
    }

    stage('Restore packages') {
      steps {
        bat 'dotnet restore WebApplication.sln'
      }
    }

  }
}
