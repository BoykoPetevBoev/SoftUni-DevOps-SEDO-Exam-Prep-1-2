pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                echo 'dotnet restore'
            }
        }
        stage('Build the project') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                echo 'dotnet build --no-restore'
            }
        }
        stage('Run tests') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                echo 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
