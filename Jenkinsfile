pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "https://github.com/Tina1409/Deakin-Unit-Page"
        TESTING_ENVIRONMENT = "Tina's TestingEnv"
        PRODUCTION_ENVIRONMENT = "Tina Verma"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven"
                echo "Compiling the code and generating necessary artifacts"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests with JUnit"
                echo "Running integration tests with Selenium"
            }
            post {
                success {
                    emailext subject: 'Unit and Integration Test Status - Success', 
                              body: 'Unit and Integration Tests have been completed successfully.', 
                              to: "tina4851.be22@chitkara.edu.in",
                              attachLog: true
                    emailext subject: 'Unit and Integration Test Status - Success', 
                              body: 'Unit and Integration Tests have been completed successfully.', 
                              to: "tinav1409@gmail.com",
                              attachLog: true
                }
                failure {
                    emailext subject: 'Unit and Integration Test Status - Failure', 
                              body: 'Unit and Integration Tests have failed.', 
                              to: "tina4851.be22@chitkara.edu.in",
                              attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Analyzing the code with SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Performing security scan on the code with OWASP ZAP"
            }
            post {
                success {
                    emailext subject: 'Security Scan Status - Success', 
                              body: 'Security Scan has been completed successfully.', 
                              to: "tina4851.be22@chitkara.edu.in",
                              attachLog: true
                }
                failure {
                    emailext subject: 'Security Scan Status - Failure', 
                              body: 'Security Scan has failed.', 
                              to: "tina4851.be22@chitkara.edu.in",
                              attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to AWS EC2 instance for staging"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to AWS EC2 instance for production"
            }
        }
    }
}
