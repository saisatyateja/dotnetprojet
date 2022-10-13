pipeline{
    agent{ label 'Dotnet06' }
    
    stages{
        stage('vcs'){
            steps{
                git url:'https://github.com/saisatyateja/dotnetprojet.git' ,
                    branch:'main'
            }
        }
        stage('build'){
            steps{
                sh 'dotnet build dotnetcoresample.csproj'
                sh 'dotnet publish dotnetcoresample.csproj'
                sh 'zip -r /home/centos/remote_root/workspace/DotNet6/bin/Debug/net6.0/dotnetcore-docs-hello-world-1.0.0.zip /home/centos/remote_root/workspace/DotNet6/bin/Debug/net6.0/publish/'
            }
        }
        stage('Artifacts'){
            steps{
                archiveArtifacts artifacts: '/home/centos/remote_root/workspace/DotNet6/bin/Debug/net6.0/dotnetcore-docs-hello-world-1.0.0.zip'
            }
        }
    }
}