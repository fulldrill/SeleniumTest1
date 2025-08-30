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
                bat 'dotnet build '
            }
        }

        stage('Run Selenium Tests') {
            steps {
                bat 'dotnet test'
            }
        }

        }
    }