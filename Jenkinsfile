// =====================================================================
// SIT223/SIT753 - 7.1C - Part 1, Task 1: Mock 7-Stage CI/CD Pipeline
// This is a MOCK pipeline: it only PRINTS the task each stage performs
// and the tool that would be used - it does not run a real build/deploy.
// =====================================================================
pipeline {
    agent any

    // No webhook required - Jenkins polls the GitHub repo for new commits.
    // "H/1 * * * *" = check for changes roughly every minute.
    triggers {
        pollSCM('H/1 * * * *')
    }

    stages {

        stage('Build') {
            steps {
                echo '--- Stage 1: Build ---'
                echo 'Tool: Maven'
                echo 'Task: Compiling the application source code and packaging it into a deployable artifact (e.g., a .jar/.war file).'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo '--- Stage 2: Unit and Integration Tests ---'
                echo 'Tool: JUnit (unit tests) + Postman/Newman (integration tests)'
                echo 'Task: Running unit tests on individual components and integration tests to confirm the different components of the application work together correctly.'
            }
        }

        stage('Code Analysis') {
            steps {
                echo '--- Stage 3: Code Analysis ---'
                echo 'Tool: SonarQube / SonarCloud'
                echo 'Task: Performing static code analysis to check the codebase against industry coding standards, detect code smells, and measure maintainability.'
            }
        }

        stage('Security Scan') {
            steps {
                echo '--- Stage 4: Security Scan ---'
                echo 'Tool: OWASP Dependency-Check'
                echo 'Task: Scanning application dependencies and source code for known security vulnerabilities (CVEs).'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo '--- Stage 5: Deploy to Staging ---'
                echo 'Tool: AWS CLI / Ansible'
                echo 'Task: Deploying the packaged build artifact to a staging server (e.g., an AWS EC2 instance) for pre-production validation.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo '--- Stage 6: Integration Tests on Staging ---'
                echo 'Tool: Postman/Newman'
                echo 'Task: Running integration tests against the live staging environment to confirm the application behaves correctly in a production-like setting.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo '--- Stage 7: Deploy to Production ---'
                echo 'Tool: AWS CLI / Ansible'
                echo 'Task: Deploying the validated build artifact to the production server (e.g., an AWS EC2 instance), making it available to end users.'
            }
        }
    }

    post {
        success {
            echo 'Mock pipeline completed successfully - all 7 stages executed.'
        }
    }
}
