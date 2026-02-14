pipeline {
    agent any

    tools {
        maven 'Maven-3'
    }

    triggers {
        cron('H/5 * * * *')  
        pollSCM('H/2 * * * *')      
    }

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean site'
            }
        }

        stage('Echo Build Status') {
            steps {
                echo "Build completed successfully!"
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
