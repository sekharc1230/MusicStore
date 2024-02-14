pipeline {
    agent { label 'dotnet8' }
    triggers { pollSCM('* * * * *') }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main',
                url: 'https://github.com/sekharc1230/MusicStore.git'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet restore ./MusicStore/MusicStore.csproj && dotnet build ./MusicStore/MusicStore.csproj'
            }
        }
        stage('test') {
            steps {
                sh 'dotnet test ./MusicStoreTest/MusicStoreTest.csproj'
            }
        }
    }
}