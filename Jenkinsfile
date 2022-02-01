pipeline {
    agent any
    stages {
        stage('Restore packages'){
           steps{
               dotnet restore WebApplication.sln
            }
         }        
        stage('Clean'){
           steps{
               dotnet clean WebApplication.sln --configuration Release
            }
         }
        stage('Build'){
           steps{
               dotnet build WebApplication.sln --configuration Release --no-restore
            }
         }
        stage('Test: Unit Test'){
           steps {
                dotnet test XUnitTestProject/XUnitTestProject.csproj --configuration Release --no-restore
             }
          }
        stage('Publish'){
             steps{
               dotnet publish WebApplication/WebApplication.csproj --configuration Release --no-restore
             }
        }
             
    }
}
