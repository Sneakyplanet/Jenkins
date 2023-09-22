pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Use your preferred build automation tool (e.g., Maven)
                echo 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Use your preferred test automation tools
                echo 'run_unit_tests'
                echo 'run_integration_tests'
            }
        }
        stage('Code Analysis') {
            steps {
                // Integrate a code analysis tool (e.g., SonarQube)
                echo 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                // Integrate a security scanning tool (e.g., OWASP ZAP)
                echo 'owasp-zap-scan'
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Deploy to your staging environment (e.g., AWS EC2)
                echo 'deploy_to_staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging
                echo 'run_integration_tests_staging'
            }
        }
        stage('Deploy to Production') {
            steps {
                // Deploy to production environment (e.g., AWS EC2)
                echo 'deploy_to_production'
            }
        }
    }
            post {
                success {
                    emailext(attachLog: true, 
                    to: "sneakyplanet12@gmail.com", 
                    subject: 'Unit and Integration Tests - Success', 
                    body: "Testing body")      
                }
                failure {
                    emailext(attachLog: true, 
                    to: "sneakyplanet12@gmail.com", 
                    subject: 'Unit and Integration Tests - Failed', 
                    body: "Testing body")      
                }
            }
        }
