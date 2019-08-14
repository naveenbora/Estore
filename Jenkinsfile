pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'dotnet build EStore.sln -p:configuration=release -v:n'   
            }
        }
        stage('Test'){
          steps  {
                sh 'dotnet test'
          }
       }
       stage('Publish'){
          steps  {
                sh 'dotnet publish'
          }
          
       }
      
    }
     post{
                always{
                    archiveArtifacts '**'
                
                }
       }
}