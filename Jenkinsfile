pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'             
            }
            post {
                success {
                    emailext (
                        attachLog : true,
                        to: 'ruvinyaye@gmail.com',
                         subject: "Build Stage Succeeded",
                         body: "The Build stage has completed successfully."
                        )
                }
                failure {
                    mail to: 'ruvinyaye@gmail.com',
                         subject: "Build Stage Failed",
                         body: "The Build stage has failed."
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'           
            }
            post {
                success {
                    emailext (
                        attachLog :true,
                        to: 'ruvinyaye@gmail.com',
                         subject: "Testing Stage Succeeded",
                         body: "Unit and Integration Tests stage completed successfully."
                        )
                }
                failure {
                    mail to: 'ruvinyaye@gmail.com',
                         subject: "Testing Stage Failed",
                         body: "Unit and Integration Tests stage has failed."
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing Code Analysis...'              
            }
            post {
                success {
                    emailext (
                        attachLog :true,
                         mail to: 'ruvinyaye@gmail.com',
                         subject: "Code Analysis Stage Succeeded",
                         body: "The Code Analysis stage has completed successfully.")
                }
                failure {
                    mail to: 'ruvinyaye@gmail.com',
                         subject: "Code Analysis Stage Failed",
                         body: "The Code Analysis stage has failed."
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing Security Scan...'
            }
            post {
                success {
                   emailext (
                        attachLog :true,
                         mail to: 'ruvinyaye@gmail.com',
                         subject: "Security Scan Stage Succeeded",
                         body: "The Security Scan stage has completed successfully.")
                }
                failure {
                    mail to: 'ruvinyaye@gmail.com',
                         subject: "Security Scan Stage Failed",
                         body: "The Security Scan stage has failed."
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
            }
            post {
                success {
                   emailext (
                        attachLog :true, 
                       mail to: 'ruvinyaye@gmail.com',
                         subject: "Deploy to Staging Succeeded",
                         body: "Deployment to Staging has completed successfully.")
                }
                failure {
                    mail to: 'ruvinyaye@gmail.com',
                         subject: "Deploy to Staging Failed",
                         body: "Deployment to Staging has failed."
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
            
            }
            post {
                success {
                    emailext (
                        attachLog :true,
                        mail to: 'ruvinyaye@gmail.com',
                         subject: "Staging Tests Succeeded",
                         body: "Integration Tests on Staging have completed successfully.")
                }
                failure {
                    mail to: 'ruvinyaye@gmail.com',
                         subject: "Staging Tests Failed",
                         body: "Integration Tests on Staging have failed."
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
            }
            post {
                success {
                   emailext (
                        attachLog :true, 
                       mail to: 'ruvinyaye@gmail.com',
                         subject: "Production Deployment Succeeded",
                         body: "Deployment to Production has completed successfully.")
                }
                failure {
                    mail to: 'ruvinyaye@gmail.com',
                         subject: "Production Deployment Failed",
                         body: "Deployment to Production has failed."
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
