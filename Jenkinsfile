pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Tool: Maven'
                echo 'Task: Compiling source code and packaging the application into a JAR/WAR artifact using Maven (mvn clean package).'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Tools: JUnit (unit tests), TestNG (integration tests)'
                echo 'Task: Running unit tests to validate individual components, then running integration tests to verify that components interact correctly.'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Tool: SonarQube (via SonarScanner for Jenkins)'
                echo 'Task: Performing static code analysis to detect code smells, bugs, and maintainability issues. Ensuring code meets industry quality standards.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Tool: OWASP Dependency-Check'
                echo 'Task: Scanning project dependencies for known CVEs and security vulnerabilities. Failing the build if critical vulnerabilities are found.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Tool: AWS CLI / SSH deploy script'
                echo 'Task: Deploying the packaged application to an AWS EC2 staging instance for pre-production validation.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Tool: Selenium / Postman (Newman CLI)'
                echo 'Task: Running end-to-end and API integration tests against the staging environment to confirm the app behaves as expected in a production-like setting.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Tool: AWS CLI / SSH deploy script'
                echo 'Task: Deploying the validated application to the production AWS EC2 instance, making it live for end users.'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed. Check the logs above.'
        }
    }
}
