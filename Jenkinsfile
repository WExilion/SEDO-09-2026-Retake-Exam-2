pipeline {

    agent any

    environment {
        DOTNET_ROLL_FORWARD = 'Major'
    }

    stages {
        stage('Restore dependencies') {
            when { branch 'main' }
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {
            when { branch 'main' }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run tests') {
            when { branch 'main' }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}