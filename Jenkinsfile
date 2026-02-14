pipeline {
    agent any
    triggers {
        cron('H/2 * * * *')          
        pollSCM('H/1 * * * *')  
    }

    stages {

        stage('Clone Repository') {
            steps {
              git 'https://github.com/AbhijitChoudhury2003/git-advanced-practical.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean site'
            }
        }

        stage('Echo Build Status') {
            steps {
                echo "Build Successful!"
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
