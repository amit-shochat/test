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
    stage('Clean'){
           steps{
               bat 'dotnet clean WebApplication.sln --configuration Release'
            }
         }
        stage('Build'){
           steps{
               bat 'dotnet build WebApplication.sln --configuration Release --no-restore'
            }
         }
        stage('Test: Unit Test'){
           steps {
                bat 'dotnet test XUnitTestProject/XUnitTestProject.csproj --configuration Release --no-restore '
             }
          }
        stage('Publish'){
             steps{
               bat 'dotnet publish WebApplication/WebApplication.csproj --configuration Release --no-restore'
             }
        }

  }
}
