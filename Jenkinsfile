pipeline {
    agent any

    tools {
        jdk 'JDK11'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/gvinaygowdav-del/GradleApp.git'
            }
        }

        stage('Verify Gradle') {
            steps {
                bat 'gradlew --version'
            }
        }

        stage('Clean Project') {
            steps {
                bat 'gradlew clean'
            }
        }

        stage('Build Project') {
            steps {
                bat 'gradlew build'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'gradlew test'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
    }

    post {

        success {
            echo 'Gradle project build successful!'
        }

        failure {
            echo 'Build failed!'
        }

        always {
            echo 'Pipeline execution completed.'
        }
    }
}
