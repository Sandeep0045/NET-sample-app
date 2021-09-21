pipeline {
    agent any
     triggers {
        githubPush()
      }
    stages {
        stage('Restore packages'){
           steps{
               sh 'dotnet restore ViewEnvironment.sln'
            }
         }        
        stage('Clean'){
           steps{
               sh 'dotnet clean ViewEnvironment.sln --configuration Release'
            }
         }
        stage('Build'){
           steps{
               sh 'dotnet build ViewEnvironment.sln --configuration Release --no-restore'
            }
         }
        stage('Publish'){
           steps{
               sh 'dotnet publish ViewEnvironment/ViewEnvironment.csproj --configuration Release --no-restore'
             }
        }
         
     
    }
}
