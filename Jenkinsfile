pipeline{
    agent{ label 'Dotnet06' }
    
    stages{
        stage('vcs'){
            steps{
                git url:'git@github.com:saisatyateja/dotnetprojet.git' ,
                    branch:'main'
            }
        }
        stage('build'){
            steps{
                sh 'dotnet build dotnetcoresample.csproj'
                sh 'dotnet publish dotnetcoresample.csproj'
                sh 'zip -r **/net6.0/dotnetcore-docs-hello-world-1.0.0.zip **/net6.0/publish'
            }
        }
        stage('Artifacts'){
                archiveArtifacts artifacts: '**/net6.0/dotnetcore-docs-hello-world-1.0.0.zip'
        }
    }
}