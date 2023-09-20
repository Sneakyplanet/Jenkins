pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'https://github.com/Sneakyplanet/Jenkins'
            }
        }

        stage('Build') {
            steps {
                // Replace with your build command
                echo 'mvn clean install'
            }
        }

        stage('Unit Test') {
            steps {
                // Replace with your unit test command
                echo 'mvn test'
            }
        }

        stage('Integration Test') {
            steps {
                // Replace with your integration test command
                echo 'mvn verify'
            }
        }

        stage('Deploy to Staging') {
            steps {
                // Replace with your deployment command
                echo 'kubectl apply -f deployment.yaml'
            }
        }

        stage('Staging Verification') {
            steps {
                // Replace with your verification command
                echo 'curl http://your-staging-url.com'
            }
        }

        stage('Deploy to Production') {
            steps {
                // Replace with your deployment command
                echo 'kubectl apply -f deployment.yaml'
            }
        }
    }

        post {
            always {
                emailext (
                    to: 'pepsomo@gmail.com',
                    subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
                    body: """<p>See attached log for details</p>""",
                    attachLog: true
                )
            }
        }

}
