pipeline {
    agent any // Runs the pipeline on any available executor
    
    stages {
        stage('Checkout') {
            steps {
                // Checks out the source code from Git repository
                git 'https://github.com/HtetAungiCe/WPF_Jenkins_GIT.git'
            }
        }
        
        stage('Restore') {
            steps {
                // Restores dependencies using dotnet restore
                bat 'dotnet restore WPF_Jenkins_GIT.sln'
            }
        }
        
        stage('Build') {
            steps {
                // Builds the .NET Core solution in Release configuration
                bat 'dotnet build WPF_Jenkins_GIT.sln --configuration Release'
            }
        }
        
        stage('Publish') {
            steps {
                // Publishes the .NET Core application to a specified directory
                bat 'dotnet publish WPF_Jenkins_GIT.sln --configuration Release --output "C:\\Users\\Lenovo\\Desktop\\publish"'
            }
        }
    }
    
    post {
        success {
            // Actions to perform if the pipeline succeeds
            echo 'Pipeline executed successfully!'
        }
        failure {
            // Actions to perform if the pipeline fails
            echo 'Pipeline execution failed!'
        }
    }
}
