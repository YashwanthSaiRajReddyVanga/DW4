pipeline {
    agent any
    
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    // Check if the 'DW4' directory already exists in the workspace
                    if (!fileExists('DW4')) {
                        // Clone the repository if it doesn't exist
                        bat 'git clone https://github.com/YashwanthSaiRajReddyVanga/DW4.git'
                    } else {
                        echo "Repository already cloned. Skipping clone step."
                    }
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
