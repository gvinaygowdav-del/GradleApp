pipeline {
    agent any

    tools {
        jdk 'JDK11'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/gvinaygowdav-del/GradleApp.git'
            }
        }

        stage('Verify Gradle') {
            steps {
                sh './gradlew --version'
            }
        }

        stage('Clean Project') {
            steps {
                sh './gradlew clean'
            }
        }

        stage('Build Project') {
            steps {
                sh './gradlew build'
            }
        }

        stage('Run Tests') {
            steps {
                sh './gradlew test'
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
