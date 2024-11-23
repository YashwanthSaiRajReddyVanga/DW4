pipeline {
    agent any
    
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    // Checkout the Git repository
                    bat 'git clone https://github.com/YashwanthSaiRajReddyVanga/DW4.git'
                }
            }
        }
        
        stage('Build') {
            steps {
                script {
                    // Navigate to the repository folder and compile Java using Maven
                    dir('DW4') {
                        bat 'mvn clean compile'
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Navigate to the repository folder and run tests using Maven
                    dir('DW4') {
                        bat 'mvn test'
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    // Placeholder for deployment logic
                    echo 'Deployment steps go here (e.g., copying files, etc.)'
                }
            }
        }
    }
    
    post {
        always {
            // Clean up workspace after the pipeline run
            cleanWs()
        }
    }
}
