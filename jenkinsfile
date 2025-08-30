pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/fulldrill/SeleniumTest1.git'
            }
        }

        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --configuration Release'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                bat 'dotnet test --configuration Release --logger "trx;LogFileName=test_results.trx"'
            }
        }

        stage('Publish Test Results') {
            steps {
                junit '**/TestResults/*.xml'  // Works if you install NUnit or XUnit plugin
            }
        }
    }
}
