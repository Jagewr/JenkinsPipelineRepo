pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Stage 1: Build - Building the code using Maven to compile and package the application."
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Stage 2: Unit and Integration Tests - Running unit tests with JUnit and integration tests with TestNG."
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Stage 3: Code Analysis - Analyzing the code using SonarQube to ensure it meets industry standards."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Stage 4: Security Scan - Performing a security scan using OWASP Dependency-Check to identify vulnerabilities."
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Stage 5: Deploy to Staging - Deploying the application to a staging server, such as an AWS EC2 instance."
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Stage 6: Integration Tests on Staging - Running integration tests on the staging environment to ensure the application functions as expected."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Stage 7: Deploy to Production - Deploying the application to a production server, such as an AWS EC2 instance."
            }
        }
    }

    post {
        success {
            echo "Sending success notification email to hd7137478@gmail.com with logs attached."
            emailext(
                to: "hd7137478@gmail.com",
                subject: "Jenkins Pipeline Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """<p>The Jenkins pipeline job <b>${env.JOB_NAME}</b> has completed successfully.</p>
                         <p>Build Number: ${env.BUILD_NUMBER}</p>
                         <p>View the build details <a href="${env.BUILD_URL}">here</a>.</p>""",
                attachLog: true // Attach the build log to the email
            )
        }

        failure {
            echo "Sending failure notification email to hd7137478@gmail.com with logs attached."
            emailext(
                to: "hd7137478@gmail.com",
                subject: "Jenkins Pipeline Failure: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """<p>The Jenkins pipeline job <b>${env.JOB_NAME}</b> has failed.</p>
                         <p>Build Number: ${env.BUILD_NUMBER}</p>
                         <p>View the build details <a href="${env.BUILD_URL}">here</a>.</p>""",
                attachLog: true // Attach the build log to the email
            )
        }
    }
}
