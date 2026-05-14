pipeline {
    agent any

    tools {
        jdk 'JDK23'
        gradle 'Gradle'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/gvinaygowdav-del/GradleApp.git'
            }
        }

        stage('Clean') {
            steps {
                bat 'gradle clean'
            }
        }

        stage('Build') {
            steps {
                bat 'gradle build'
            }
        }

        stage('Test') {
            steps {
                bat 'gradle test'
            }
        }

    }

    post {
        success {
            echo 'Build Successful!'
        }

        failure {
            echo 'Build Failed!'
        }
    }
}
